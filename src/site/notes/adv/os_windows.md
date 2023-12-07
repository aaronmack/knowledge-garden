---
{"dg-publish":true,"permalink":"/adv/os-windows/","title":"OS - Windows","noteIcon":""}
---


这里打算长久更新这篇，去记录与OS-Windows相关的东西

## Windows激活

发现一个非常方便的Windows激活工具，但可能需要科学上网才行~

[https://github.com/massgravel/Microsoft-Activation-Scripts](https://github.com/massgravel/Microsoft-Activation-Scripts)
https://github.com/TGSAN/CMWTAT_Digital_Edition/releases/tag/2.6.4.0

## Windows优化

这个工具下载下来后可以直接运行，里面有非常多的选项，比如开启关闭Windows更新，禁用一些缓存等等~

[https://github.com/hellzerg/optimizer](https://github.com/hellzerg/optimizer)

## Windows 禁用Defender

忘记了是用哪一个去关闭的Windows的Defender，感觉其实只要不下载来路不明的app一般都不需要这个，或者除非黑客盯上你了，就是要攻击你~

[https://github.com/ionuttbara/windows-defender-remover](https://github.com/ionuttbara/windows-defender-remover)

[https://github.com/swagkarna/Defeat-Defender-V1.2.0](https://github.com/swagkarna/Defeat-Defender-V1.2.0)

https://github.com/qtkite/defender-control

> [!WARNING] 在移除时一定要选择Safe的选项，这样可以Rollback。
## Windows 磁盘映射

有时候你有个WebDAV或者OneDrive，但是Windows自带的磁盘映射似乎很容易卡死，在查找对应的替代方案是，找到了RaiDrive，可以映射很多很多种服务~

[https://www.raidrive.com/](https://www.raidrive.com/)

## Windows 磁盘检测工具

**SpaceSniffer** 可以分析磁盘上的文件大小占用空间情况~

**CrystalDiskMark** 磁盘读写速度测试~

**CrystalDiskInfo** 查看磁盘健康情况~


## Windows下的sudo与服务管理

今天在测试alist的windows本地部署时，发现了nssm这个工具（在alist的官方文档中提到的[Manual installation | AList Docs](https://alist.nn.ci/guide/install/manual.html#get-alist)），我使用的是scoop去管理win上面的程序安装和卸载

scoop install nssm
scoop install sudo

还有一个gsudo，不知这两个有何区别。

## Windows下的工具

开发人员的瑞士军刀 [GitHub - veler/DevToys: A Swiss Army knife for developers.](https://github.com/veler/DevToys)

scoop install devtoys-np

## Windows 美化Shell

oh-my-posh是适用于任何外壳的提示主题引擎。

1.安装clink 使用 `scoop install clink` 执行`clink autorun install`,这样默认启动cmd就是clink的界面了。

2.执行clink info, 找到scripts目录，进入目录后新建一个`oh-my-posh.lua`文件,内容如下

```lua
load(io.popen('oh-my-posh init cmd'):read("*a"))()
```
3.administrator打开cmd，执行`oh-my-posh font install`下载字体,需要开启代理。

4.安装方式 `scoop install https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/oh-my-posh.json`

## Windows 空间清理

[GitHub - SFYYH/cPanClear: C盘清理教程](https://github.com/SFYYH/cPanClear) 这个仓库中的README介绍了如何清理Windows的C盘去释放空间，这里面提到了Dism++这个软件，用它可以清理到一些更深层次的不需要的文件。

## Windows 关闭更新

[GitHub - WereDev/Wu10Man: Enable/Disable Windows 10 Automatic Updates](https://github.com/WereDev/Wu10Man)

这个项目的作者已经不维护了。┭┮﹏┭┮

## Visual Studio Extension - Viasfora

<img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/e/image.6j7x5r3wq840.png" alt="image" width="500"  />

一个非常好看的Code Style，比起之前只是一片蓝色要好很多。

## Windows文件搜索

Everything - [voidtools](https://www.voidtools.com/)
Listary - [Listary – File Search & App Launcher](https://www.listary.com/)

自带的资源管理器中的资源搜索比较慢。可以使用everything。

## Windows 下文件解锁

有时候想要删除某个文件发现被占用，无法删除掉，这时候可以使用IObit Unlocker去解锁文件，这个软件安装完成后是个右键菜单。

[IObit Unlocker, Solution for "undelete files or folders" Problems on Windows 8, 7, Vista, XP, 10 - IObit](https://www.iobit.com/en/iobit-unlocker.php)


## Windows下的代理

Proxifier - https://www.proxifier.com/download/

## Windows 鼠标键盘共享

1.可以以某台电脑为Server，其它电脑为Client，一套鼠标键盘控制多台电脑 barrier - [GitHub - debauchee/barrier: Open-source KVM software](https://github.com/debauchee/barrier)测试之后发现鼠标对不准，会在另外一边屏幕消失。Github上的也有提Issue。

2.Mouse without Borders
 下载网址  https://www.microsoft.com/en-us/download/details.aspx?id=35460 
 参考视频：[同时操控 2 台电脑，只需一个鼠标和键盘！完全免费，由微软官方提供 | 零度解说 - YouTube](https://www.youtube.com/watch?v=bcsZzhdrccs)

## Windows 开机启动

只需要把快捷方式放到 `%appdata%\Microsoft\Windows\Start Menu\Programs\Startup` 这个目录下，即可。