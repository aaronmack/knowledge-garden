---
{"dg-publish":true,"permalink":"/adv/os-windows/","noteIcon":""}
---


这里打算长久更新这篇，去记录与OS-Windows相关的东西

**1. Windows激活**

发现一个非常方便的Windows激活工具，但可能需要科学上网才行~

[https://github.com/massgravel/Microsoft-Activation-Scripts](https://github.com/massgravel/Microsoft-Activation-Scripts)
https://github.com/TGSAN/CMWTAT_Digital_Edition/releases/tag/2.6.4.0

**2. Windows优化**

这个工具下载下来后可以直接运行，里面有非常多的选项，比如开启关闭Windows更新，禁用一些缓存等等~

[https://github.com/hellzerg/optimizer](https://github.com/hellzerg/optimizer)

**3. 禁用Defender**

忘记了是用哪一个去关闭的Windows的Defender，感觉其实只要不下载来路不明的app一般都不需要这个，或者除非黑客盯上你了，就是要攻击你~

[https://github.com/ionuttbara/windows-defender-remover](https://github.com/ionuttbara/windows-defender-remover)

[https://github.com/swagkarna/Defeat-Defender-V1.2.0](https://github.com/swagkarna/Defeat-Defender-V1.2.0)



**4. 磁盘映射**

有时候你有个WebDAV或者OneDrive，但是Windows自带的磁盘映射似乎很容易卡死，在查找对应的替代方案是，找到了RaiDrive，可以映射很多很多种服务~

[https://www.raidrive.com/](https://www.raidrive.com/)

**5. 磁盘检测工具**

**SpaceSniffer** 可以分析磁盘上的文件大小占用空间情况~

**CrystalDiskMark** 磁盘读写速度测试~

**CrystalDiskInfo** 查看磁盘健康情况~


**6. Windows下的sudo与服务管理**

今天在测试alist的windows本地部署时，发现了nssm这个工具（在alist的官方文档中提到的[Manual installation | AList Docs](https://alist.nn.ci/guide/install/manual.html#get-alist)），我使用的是scoop去管理win上面的程序安装和卸载

scoop install nssm
scoop install sudo

**7. Windows 空间清理**

[GitHub - SFYYH/cPanClear: C盘清理教程](https://github.com/SFYYH/cPanClear) 这个仓库中的README介绍了如何清理Windows的C盘去释放空间，这里面提到了Dism++这个软件，用它可以清理到一些更深层次的不需要的文件。