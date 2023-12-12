---
{"dg-publish":true,"permalink":"/adv/my-develop/","title":"Development","noteIcon":""}
---

<img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/e/image.1fo75js2vjj4.webp" alt="image" width=600/>

# Openpype

[GitHub - ynput/OpenPype: Main OpenPype repository and AYON openpype addon codebase](https://github.com/ynput/OpenPype)

```bash
# python version 3.9.13
$Env:http_proxy = "http://localhost:10809"
$Env:https_proxy = "http://localhost:10809"
.\tools\create_env.ps1
.\tools\fetch_thirdparty_libs.ps1
.\tools\build.ps1
```

# ArmorPaint

[GitHub - armory3d/armortools: 3D Content Creation Tools](https://github.com/armory3d/armortools)


```bash
# 解压 `..\armorcore\v8\libraries\win32\release\v8_monolithz` using 7-Zip - Extract Here (exceeds 100MB)

# 生成工程
cd c:/src/armortools/armorpaint
..\armorcore\Kinc\make --from ..\armorcore -g direct3d11

# 在"build\ArmorPaint.sln"中打开生成的 Visual Studio 项目针对 x64 和Release进行构建和运行

# Copy build\x64\Release\ArmorPaint.exe to build\krom to run ArmorPaint.exe directly
```

# OpenUSD

**构建**

```bash
# python version 3.10.11
# run `x64 Native Tools Command Prompt for VS 2022`
# for download usd-src
set http_proxy=http://localhost:10809
set https_proxy=http://localhost:10809
# venv
python -m pip install virtualenv
python -m virtualenv C:/src/OpenUSD/venv
call C:/src/OpenUSD/venv/Scripts/activate
# for usdview
pip install PyOpenGL
pip install PySide6
pip install opencolorio
pip install numpy
# for usdSchemaGen
pip install jinja2
# build dry run, to build remove -n option
python .\build_scripts\build_usd.py --materialx --draco --alembic --hdf5 --openimageio --opencolorio --embree --openvdb --ptex --prman --test --build-variant=relwithdebuginfo --src=c:\data\build\usd-src --build-args=USD,"-DPXR_ENABLE_VULKAN_SUPPORT=FALSE -DRENDERMAN_LOCATION=C:/data/plugins/RenderManProServer-25.2" c:\data\build\usd-build –n
```

**Schema**

```
usdGenSchema [schemaPath] [codeGenPath]
```


# Stable-diffusion

**ui**

```bash
# python version 3.10.11
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git

.\webui-user.bat
```

# Ye

## ub

python开发环境

```bash
python310 -m virtualenv C:\src\Ye\src\ub\venv
# pip install dependenties with requirements.txt
```

# Blender

[Blender Developer Wiki](https://wiki.blender.org/wiki/Main_Page)

```bash
git clone https://projects.blender.org/blender/blender.git
cd C:\src\blender-git\blender
make update
make full nobuild
```

# QuiltiX

[GitHub - PrismPipeline/QuiltiX: QuiltiX is a graphical node editor to edit, and author MaterialX based materials of 3D assets](https://github.com/PrismPipeline/QuiltiX)

python version 3.9.13

```bash
# via pypi (install)
pip install QuiltiX
pip install git+https://github.com/PrismPipeline/OpenUSD_build.git@23.11-win-mtlx-1.38.8

# run
python -m QuiltiX
```

# gatling


[GitHub - pablode/gatling: Hydra-enabled GPU path tracer that supports MaterialX and MDL](https://github.com/pablode/gatling)

```bash
cmake -B build -Wno-dev -DUSD_ROOT=%E_USD_LOCATION% -DMDL_ROOT=%E_MDLSDK_DIR% -DCMAKE_INSTALL_PREFIX=C:/data/build/gatling -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release --target INSTALL -- /M:8
```

# pyside-setup

# vcpkg

```bash
# download & install
git clone https://github.com/microsoft/vcpkg
.\vcpkg\bootstrap-vcpkg.bat

# qt6
...
```

# (Python)

## pyenv 

> [!ERROR] Till the 2023-12-08，Using scoop install pyenv causing error `core` compoment install error.  So we use this command `Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"` from [Installing and setting up Python - Everything I Know](https://jonathansoma.com/everything/setup/install-python/#__tabbed_3_2)

在这之后，需要执行 pyenv update 去更新仓库。

> [!WARNING] Building Ye and blender warning. say python not found.
## pipx

[GitHub - pypa/pipx: Install and Run Python Applications in Isolated Environments](https://github.com/pypa/pipx)

```bash
# python version 3.10.11
python -m pip install --user pipx

# add executable to environment path
python -m pipx ensurepath

pipx install pycowsay

```

## poetry

[GitHub - python-poetry/poetry: Python packaging and dependency management made easy](https://github.com/python-poetry/poetry)

Install and Upgrade

```bash
python -m pipx install poetry
python -m pipx upgrade poetry
```

# (Version Control)

1. git
2. SnowFS

---

1. TortoiseSVN

```bash
# 重置当前仓库
svn revert --recursive .
# 忽略文件(项目级)
图形界面 TortoiseSVN -> Properties -> New -> Other -> svn:global-ignores
# 忽略文件(目录级)
选中一个文件/目录 -> TortoiseSVN -> Properties -> New -> Other -> svn:ignore
```

2. VisualSVN Server

> [!INFO]
> SVN -> Import 可以将当前目录的所有文件上传项到SVNServer的版本库。
> SVN -> Checkout 输入仓库地址与路径可以检出。

> [!ERROR]
> 1.SVN连接不到VisualSVN服务，检查是不是开启了代理。`%appdata%\Subversion\servers` 编辑这个文件，注释掉下方两行。

```config
#http-proxy-host = 127.0.0.1
#http-proxy-port = 10809
```

> [!ERROR] 2.SVN图标在Winodws11下不显示。原因是SVN的图标在注册表中靠后了。（Windows按照空格来排），(Explorer空白处右键 ) -> TortoiseSVN -> Settings -> Icon Overlays -> Overlay Handles -> Start registry Editor进行编辑，增加多几个空格使其排名靠前。

# (Database Connection)

Mongosh - https://www.mongodb.com/try/download/compass
Mysqlsh - https://dev.mysql.com/downloads/shell/

# (AI)

**有哪些概念**

* pytorch: [Start Locally | PyTorch](https://pytorch.org/get-started/locally/)
* tensorflow: [GitHub - tensorflow/tensorflow: An Open Source Machine Learning Framework for Everyone](https://github.com/tensorflow/tensorflow)
* ONNX：Open Neural Network Exchange（开放式神经网络交换）[ONNX | Home](https://onnx.ai/)
* One-hot: `[0,1,0,0,...]`
* Embedding
	* Word2vec

**有哪些结构**

* Gradient descent 梯度下降
	* derivate - 求导，learning rate
	* sgd，Adam
	* partial derivate 偏微分
	* gradient 梯度 - 所有的偏微分的向量 e.g. $\nabla f=\left({\frac{\partial f}{\partial x_{1}}};{\frac{\partial f}{\partial x_{2}}};\cdot\cdot;{\frac{\partial f}{\partial x_{n}}}\right)$
* Linear Regression 线性回归 $wx+b$
* Logistic Regression 逻辑回归 - 线性回归的基础上加了一个激活函数（压缩函数）
* Classification 分类问题

* RNN  - (Hard to parallel)
	- LSTM - (Long Short-Term Memory) 长短时记忆
* CNN  - Using CNN to replace RNN (CNN Can parallel)
* Self-Attention Layer - Transformer
	- q:query (to match other)
	- k:key (to be matched)
	- v:information to be extracted
	- -
	- Positional Encoding ($e^i$)
* Multi-head Self-Attention
	- Norm (Layer Norm, Batch Norm)
* Transformer

<img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/e/1702297659308.webp" alt="1702297659308" width=500/>
这是一个seq2seq的model，左半部是Encoder，右半部是Decoder。
* Universal Transformer - (横轴Positions使用Transformer，纵轴Depth使用RNN)
* Self-attention GAN - 用于影像处理的Transformer，一个pixel考虑全部pixel信息。

**有哪些模型**

MiDaS - 通过单张图像计算相对深度。

BERT
GPT
ELMO

Next-ViT - [[2207.05501] Next-ViT: Next Generation Vision Transformer for Efficient Deployment in Realistic Industrial Scenarios](https://arxiv.org/abs/2207.05501)
OpenVINO - 

**有哪些数据集**

* MNIST - 手写数字

## 资料

[Google Research Blog](https://blog.research.google/)
李宏毅
吴恩达