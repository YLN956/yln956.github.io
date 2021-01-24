---
title: vm装mac10.15
tags:
  - 虚拟机
  - 好东西
categories: vm装mac10.15
abbrlink: 45943
date: 2021-01-22 11:33:41
---

Windows系统使用VMware安装MacOS Catalina 10.15系统（黑苹果）的教程，提供MacOS 10.15系统镜像，虚拟机软件VMware Workstation Pro15.5，unlocker3.02和11.5版本package的darwin.iso下载。

<!-- more -->

# 【安装准备】

1 系统镜像：macOS.Catalina.10.15.0.cdr，已经修改来支持在 VMware Workstation Pro 中运行

2 虚拟机软件：VMware Workstation Pro，版本号不低于 15.5，激活方法自行寻找。

3 unlocker：解锁VMware的MacOS支持，版本号不低于 3.0.2

4 darwin.iso：VMware Tools For Mac，用于解决 安装后，MacOS分辨率太小（1024*768像素），版本号不低于11.5 （注意，官方11.5已经不提供下载，您需要从本页面下载darwin.iso，低版本无法在新的MacOS系统中安装）

链接：https://pan.baidu.com/s/1Afwkar7JbBNNWMtIAmlGZQ 
提取码：gje2 
复制这段内容后打开百度网盘手机App，操作更方便哦

提取码：grq1 



# 【安装步骤】

## 1 安装虚拟机软件：



![VMware Workstation Pro 15.5安装程序启动界面](vm%E8%A3%85mac10-15/201910221518567681_c_w_600.png)

首先，安装 VMware Workstation Pro 15.5，如果你的版本是15.0，不要使用官方的在线升级功能，因为你可能会陷入重启，重新安装的循环。只需要下载最新的安装包，会自动覆盖升级，原来的激活信息会保留。其他版本，从重新安装15.5，再重新激活。

安装虚拟机就不详细说了，请自行百度

## 2 安装unlocker：

**首先，任务管理器把所有关于VM的任务都关掉**

进入unlocker的目录，如果你是从Git上找到的unlocker，建议直接下载源码，不要下载 Releases 版本。进入源码根目录，右键，以**管理员权限运行** win-install.cmd，等待命令执行完毕，解锁 VMware Workstation Pro 安装 MacOS的功能。

## 3 新建虚拟机：

本文以典型为例

![image-20210122124653035](vm%E8%A3%85mac10-15/image-20210122124653035.png)

![image-20210122124756348](vm%E8%A3%85mac10-15/image-20210122124756348.png)

选择10.15

![image-20210122124826085](vm%E8%A3%85mac10-15/image-20210122124826085.png)

再选择放虚拟机的位置

![image-20210122124853188](vm%E8%A3%85mac10-15/image-20210122124853188.png)

这里选择硬盘大小，如果只是看看玩玩，40就够了，想用的建议大点，系统装完之后大概占用20G左右空间

![image-20210122124913372](vm%E8%A3%85mac10-15/image-20210122124913372.png)

![image-20210122125012741](vm%E8%A3%85mac10-15/image-20210122125012741.png)

![image-20210122125050551](vm%E8%A3%85mac10-15/image-20210122125050551.png)

![image-20210122125121826](vm%E8%A3%85mac10-15/image-20210122125121826.png)

这里全勾了

![image-20210122125148734](vm%E8%A3%85mac10-15/image-20210122125148734.png)



打开虚拟机目录编辑vmx文件，记事本就可以打开，在smc.present = "TRUE"下面一行添加smc.version = "0"

![image-20210122125537308](vm%E8%A3%85mac10-15/image-20210122125537308.png)

然后打开虚拟机

![image-20210122125301662](vm%E8%A3%85mac10-15/image-20210122125301662.png)



## 4 安装MacOS:

选择语言

![image-20210122130201051](vm%E8%A3%85mac10-15/image-20210122130201051.png)

选择磁盘工具格式化磁盘

![image-20210122130246531](vm%E8%A3%85mac10-15/image-20210122130246531.png)

![image-20210122130404576](vm%E8%A3%85mac10-15/image-20210122130404576.png)

然后返回选择安装，点继续，同意，然后等待安装完成

![image-20210122130457887](vm%E8%A3%85mac10-15/image-20210122130457887.png)

选择地区，然后一路继续

![image-20210122133101211](vm%E8%A3%85mac10-15/image-20210122133101211.png)

![image-20210122133654266](vm%E8%A3%85mac10-15/image-20210122133654266.png)![image-20210122133654903](vm%E8%A3%85mac10-15/image-20210122133654903.png)

## 5 安装VMware Tools：

正常情况下，在第2步，安装 unlocker 时，会自动下载 darwin.iso，并复制到 VMware Tools 的根目录，但是由于官方源的失效，需要我们手动安装。先关闭MacOS，编辑虚拟机设置，在CDROM里，挂载 darwin.iso

![image-20210122133816635](vm%E8%A3%85mac10-15/image-20210122133816635.png)

然后再次启动MacOS，可以在桌面看到 VMware Tools 的盘符，双击，安装 VMware Tools 后即可

注意，这里要选择信任（先点击左下角的图标解锁），允许 系统 安装 VMware Tools。

![image-20210122134232974](vm%E8%A3%85mac10-15/image-20210122134232974.png)

安装成功后，会自动重启电脑，你就可以看到熟悉的MacOS系统，赶紧全屏，体验一下新系统操作的感觉吧！


