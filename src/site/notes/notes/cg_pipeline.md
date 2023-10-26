---
{"dg-publish":true,"permalink":"/notes/cg-pipeline/","noteIcon":"","created":"","updated":""}
---



# OpenPype

# 题记

在捣鼓Pipeline时，从Github上发现了OpenPype这款DCC管道工具和CgWire开源的流程管理软件。
OpenPype就像是Publisher和Loader，交接棒一样进行流程中数据的管理，并且支持和CgWire的互动，满足一般工作室的需求。
目前Pype的官方提供了云支持，但代码是开源的你可以自己搭建数据库和Pype。

# 准备

> 系统 Windows+Docker
> Bash 其中在生成CA的部分，是使用的cgywin

1. 数据库使用的mongodb，我们为了安全，使用ca证书进行authorization，测试的时候发现ca证书和数据库如果换了电脑，就需要重新生成。

生成CA证书和公私钥 (下方的命令)

```bash
Ref: https://github.com/bitnami/containers/blob/main/bitnami/mongodb/README.md

cd  /cygdrive/c/data/db/.mongodb/ca_local

openssl genrsa -out mongoCA.key 2048

openssl req -x509 -new \
    -subj "/C=US/ST=NY/L=New York/O=Example Corp/OU=IT Department/CN=mongoCA" \
    -key mongoCA.key -out mongoCA.crt

export NODE_NAME=mongodb
openssl req -new -nodes \
    -subj "/C=US/ST=NY/L=New York/O=Example Corp/OU=IT Department/CN=${NODE_NAME}" \
    -keyout ${NODE_NAME}.key -out ${NODE_NAME}.csr


openssl x509 \
    -req -days 365 -in ${NODE_NAME}.csr -out ${NODE_NAME}.crt \
    -CA mongoCA.crt -CAkey mongoCA.key -CAcreateserial -extensions req

cat ${NODE_NAME}.key ${NODE_NAME}.crt > ${NODE_NAME}.pem


rm ${NODE_NAME}.csr


# 在docker-desktop的mongodb中的exec中执行下方命令，生成pfx格式的密钥
cd /certificates
openssl pkcs12 -inkey mongodb.key -in mongodb.crt -export -out mongodb.pfx （passwd: a1234）
openssl pkcs12 -inkey mongoCA.key -in mongoCA.crt -export -out mongoCA.pfx （passwd: a1234）
```

使用compose.yaml配置文件和.env配置文件通过使用docker-desktop搭建mongodb数据库

2. 创建好这两个文件

.env

```env
### MongoDB configuration

MONGODB_VERSION=7.0.2
MONGODB_DATA=C:/data/db/.mongodb/mongodb_local
MONGODB_CA=C:/data/db/.mongodb/ca_local
MONGODB_CONF=C:/data/db/.mongodb/local_config
ALLOW_EMPTY_PASSWORD=no
MONGODB_ROOT_PASSWORD=tC0jsi16gEqx
MONGODB_REPLICA_SET_KEY=mL7sArv24C4o
```

compose.yaml

```yaml

volumes:
  mongodb_data: { driver: local }

services:
  mongodb:
    image: docker.io/bitnami/mongodb:${MONGODB_VERSION:-6.0}
    restart: always
    volumes:
      - "${MONGODB_DATA}:/bitnami/mongodb"
      - "${MONGODB_CA}:/certificates"
      - "${MONGODB_CONF}:/bitnami/mongodb/conf"
    environment:
      MONGODB_REPLICA_SET_MODE: primary
      MONGODB_REPLICA_SET_NAME: ${MONGODB_REPLICA_SET_NAME:-rs0}
      MONGODB_PORT_NUMBER: ${MONGODB_PORT_NUMBER:-27018}
      MONGODB_INITIAL_PRIMARY_HOST: ${MONGODB_INITIAL_PRIMARY_HOST:-mongodb}
      MONGODB_INITIAL_PRIMARY_PORT_NUMBER: ${MONGODB_INITIAL_PRIMARY_PORT_NUMBER:-27018}
      MONGODB_ADVERTISED_HOSTNAME: ${MONGODB_ADVERTISED_HOSTNAME:-mongodb}
      MONGODB_ENABLE_JOURNAL: ${MONGODB_ENABLE_JOURNAL:-true}
      ALLOW_EMPTY_PASSWORD: ${ALLOW_EMPTY_PASSWORD:-yes}
      MONGODB_ROOT_PASSWORD: ${MONGODB_ROOT_PASSWORD:-password123}
      MONGODB_REPLICA_SET_KEY: ${MONGODB_REPLICA_SET_KEY:-replicasetkey123}
      MONGODB_EXTRA_FLAGS: --tlsMode=preferTLS --tlsCertificateKeyFile=/certificates/mongodb.pem --tlsClusterFile=/certificates/mongodb.pem --tlsCAFile=/certificates/mongoCA.crt
    expose:
      - ${MONGODB_PORT:-27018}
    ports:
      - "${MONGODB_BIND_IP:-0.0.0.0}:${MONGODB_HOST_PORT:-27018}:${MONGODB_PORT:-27018}"
```

3. cd到这两个文件的文件夹中，调用`docker compose up -d`命令，执行成功后如果没有报错就可以使用一些工具来测试数据库是否创建成功了。

> mongosh来连接数据库并创建用户

```bash
# 连接
"C:\data\port\mongosh-1.10.6-win32-x64\bin\mongosh" --port 27018 -u root -p tC0jsi16gEqx --authenticationDatabase admin

# 使用admin数据库
use admin

# 创建用户 (测试的时候发现Pype并没有自己的用户管理，是通过数据库用户来进行权限管理的，真的牛)
db.createUser( { user: "aaron", pwd: "secretpassword", roles: [ { role: "userAdminAnyDatabase", db: "admin" } ] } ) 

db.createUser( { user: "Mohan", pwd: "password", roles:[{ role: "read" , db:"openpype"}, role: "readWrite" , db:"avalon"} }] } ) 

db.grantRolesToUser( "ll", [{role:"read", db:"openpype"}, {role:"readWrite", db:"avalon"}] ) 

# 改变用户的密码
db.changeUserPassword("root", "secretpassword") 
# 删除用户
db.dropUser("siteUserAdmin") 
# 列出所有用户
db.system.users.find() 
# 改变用户的权限
db.grantRolesToUser('aaron', ['readWriteAnyDatabase']);

```

# Cgwire

[Installation | Kitsu Documentation](https://kitsu.cg-wire.com/installation/)

虽然Pype中也有Project Manage，但是我们可以扩展使用Cgwire去进行项目的管理与创建。

执行 `docker run -d -p 25061:80 --name cgwire cgwire/cgwire:0.17.37` 去开启cgwire服务，这里设置的是为防止污染80端口而改为25061端口，版本为截至现在最新的0.17.37，这里可以改为latest选择最新版本

成功后在浏览器打开localhost:25061，初次登录用户名与密码是

```
- login: admin@example.com
- password: mysecretpassword
```

进去之后就可以创建用户，创建部门，资产类型等等，这里我创建了一个名为Discover的项目。

<img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/e/image.5q4k52oe0q80.webp" alt="image" />
# OpenPype


## 从源码编译

> 截至至3.17.3版本，使用Python3.9

从 https://github.com/ynput/OpenPype 仓库的Readme中参考

1. 首先Clone原仓库使用`git clone --recurse-submodules git@github.com:ynput/OpenPype.git`

2. 然后打开一个PowerShell，进入到仓库的文件夹里，执行`.\tools\create_env.ps1` 创建虚拟venv环境

<img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/e/image.2lyughc8ikm0.webp" alt="image" />

3. 再执行`.\tools\fetch_thirdparty_libs.ps1`下载第三方依赖库
4. 执行`.\tools\build.ps1`去构建Pype，执行成功后在build文件中就会有`openpype_gui.exe`和`openpype_console.exe`这两个程序


## 配置Pype

可以使用root账号，登录Mongodb数据库，然后执行

```
# 创建一个管理员账号
db.createUser( { user: "aaron", pwd: "secretpassword", roles: [ { role: "userAdminAnyDatabase", db: "admin" } ] } )

# 创建一个普通账号
db.grantRolesToUser( "ll", [{role:"read", db:"openpype"}, {role:"readWrite", db:"avalon"}] )
```

## 从仓库下载

e.g. OpenPype · GitHub https://github.com/ynput/OpenPype/releases/tag/3.17.3