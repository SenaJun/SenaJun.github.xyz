---
layout:     post
title:      Chrome OS 安装笔记
subtitle:   安装过程及资源分享
date:       2019-05-19
author:     SenaJun
header-img: img/Chrome_OS_Install_Note/Fyde_OS_Lock.png
catalog: true
tags:
    - Chrome OS
    - 安装笔记
    - 资源分享
---

# Chrome 安装笔记 - 安装过程及资源分享

## 前言

本来的打算是先写这一篇的，但是发现因为图片、素材和一些其他准备好像有点少，就先写了 [**OS 对比及个人看法**](https://senajun.github.io/2019/05/13/Chrome-OS-Install-Note-1/ "**OS 对比及个人看法**") <br>
但是相信看完了 **OS 对比和个人看法** 之后再来看这一篇的各位，已经对 **Chrome OS** 有了一定程度的认识以及一些看法， <br>
同时也会有人找不到资源，或者没有经验，而在制作 **U盘介质** 和 **启动安装** 这个过程中踩到一些坑。

肯定也会有跟我一样的**英语废**，借助机翻都难以看懂那一大批一大批的英文站点 <br>
所以，希望这篇文章能够帮助到想要体验或使用 Chrome OS 的各位。

## 注意事项

#### 数据备份

数据备份这点肯定不需要多说了，大家都懂。 <br>
但是这里要做一个补充说明，在体验 Chrome OS 的时候，我推荐大家要有两台电脑。

你在体验 Chrome OS 的时候，我推荐是最好使用**两台电脑** <br>
因为在安装 Chrome OS 的过程中，如果你不是选择**双系统安装**，而是直接**覆盖原系统**进行硬盘安装 <br>
如果你只有一台电脑，那此时你就要慎重操作了，因为该操作**可能**会**直接 Clean 你的整个硬盘，并整合为一个盘符进行安装** <br>
简单的讲，就是你的主启动硬盘的数据整个 **么得了** 

此时多一台不使用的备用/老旧设备，就可以增加你的**容错率**，**以免操作失误导致整个硬盘数据丢失**

#### 关于 U盘 刻录及引导

这里针对 **Chrome OS 的 U盘刻录** 说一下注意事项

这里推荐 **U盘介质** 烧录，若你有一个较为优质的 **USB3.0** 低容量 U盘，我建议你将他利用起来，**将 Chrome OS 烧录到 U盘 中**

U盘 刻录的过程，跟我们平时制作 Windows 启动盘是一样的，但是需要注意的一点是 <br>
Chrome OS 在刻录完成之后，**会将 U盘 跟我们的 C盘，也就是系统盘一样，进行分区**  <br>
**如：EFI 系统分区、System 分区、Recovery 分区** <br>
有些电脑应该会在 U盘 刻录完成之后，弹出数个 **请格式化磁盘** ，无视即可，千万不要去点击格式化，不然又要重新刻录了。

#### 关于鼠标 & 触摸板

这一项，若你是用台式机进行体验 Chrome OS，可以 Pass 掉，直接看下一项

Chrome OS 对笔记本电脑的触摸板兼容性有一定的要求，这里需要你去 **Bios** 中找到 **TouchPad** 选项进行设置 <br>
以我的宏碁笔记本为例，我的 TouchPad 设置中，有两项：**Basic、Advanced** <br>
这里我设置为 **Basic** 之后，Chrome OS 才会**识别**到我的触摸板 <br>

触摸板可能会根据你笔记本的年代而无法兼容触摸板驱动， <br>
这点只能通过大家实际测试才能知道结果了

![Bios TouchPad 触摸板设置](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Bios_ToochPad.jpg "Bios TouchPad 触摸板设置")

## 前期准备

#### 必要工具

> 1. 最少一台电脑
> 2. 一个最少 8G 的 U盘
> 3. 一个备用鼠标
> 4. Chrome OS 镜像文件
> 5. BalenaEtcher 刻录工具
> 6. 一台已 Root Android 设备 or 一台可以配置 SSR 的路由器，**若你要安装 Fyde OS 请无视**

#### 下载镜像文件

我所测试的 OS 一共有3个：[Chromium OS Biuld](https://chromium.arnoldthebat.co.uk/index.php "Chromium OS Biuld")、[CloudReady OS](https://www.neverware.com/freedownload "CloudReady OS")、[Fyde OS](https://fydeos.com/download "Fyde OS")

这里三个镜像的**下载方法**我都会说明，但是后面会以 **Fyde OS** 为主进行说明

**Fyde OS：** [Fyde OS 下载页](https://fydeos.com/download "Fyde OS 的下载页")，选择下载 **Fyde OS For PC**，镜像大小约为 **1.6GB**，下载完成后**无需解压**。

![Fyde OS 下载页](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Download.jpg "Fyde OS 下载页")

**CloudReady OS：** [CloudReady OS 下载页](https://www.neverware.com/freedownload "CloudReady OS 的下载页")，下拉至 `Build your CloudReady installer` 找到 `If you're using a Mac or a Chromebook` 直接点击 **DOWNLOAD 64-BIT** 进行下载，镜像大小约为 **1GB**，下载完成后**无需解压**。

![CloudReady OS 下载页](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/CloudReady_OS_Download.jpg "CloudReady OS 下载页")

**Chromium OS Build：** [Chromium OS Build 下载页](https://chromium.arnoldthebat.co.uk/index.php?dir=./ "Chromium OS Build 下载页")，进入下载页 <br>
会有三个选项：**Daily、Special、Weekly（日更版、特别版、周更版）** <br>
这里按照需求选择，我选择的是 **Weekly 周更版** <br>
进入分支文件夹后，你可能会看到一堆文件，我们**看开头的代号**即可。<br>
一共有三个版本：**Camd64OS（64位镜像）、CARMOS（ARM版镜像）、Cx86OS（32位版镜像）**<br>
我们直接找最新的下载 **Camd64OS 64位镜像** 即可，因为是 **.7z** 文件，我们需要将 **.img** 文件给**解压出来**

若需要了解更多，可以查看该连接：https://www.atmarkit.co.jp/ait/articles/1408/27/news046.html <br>
注意，该网页，页面为全**日文**

![Chromium OS Build 下载页](https://github.com/SenaJun/SenaJun.github.io/blob/master/img/Chrome_OS_Install_Note/Chromium_OS_Download.jpg?raw=true "Chromium OS Build 下载页")
![Chromium OS Biuld 版本](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Chromium_OS_Version.jpg "Chromium OS Biuld 版本")

#### 关于 U盘 格式化

这里关于 U盘 格式化特别说明一下，在刻录镜像之前，建议使用 `CMD` 调出 `Diskpart` 对指定硬盘进行 `Clean` 清除。

当然，使用简单的快速格式化也是可以的，但是在特定情况下，快速格式化并不能将**被隐藏的分区**进行格式化，导致后续刻录工作出现 **Bug**

**方法：**
快捷键 `Win+R` 启动运行，输入 `CMD` 开启命令行 <br>
在命令行中输入 `diskpart` 启动分区管理 <br>
在分区管理中输入 `list disk` 显示磁盘摘要 <br>
输入 `select disk[=n]` 选择你的**外置存储工具**，假设我的 **U盘** 为 **磁盘 2**，则输入 `select disk 2` 即可选择 U盘 <br>
这时输入 `clean` 即可清除你选中的**外置存储设备**  <br>
清除完成后，输入 `Create partition primary` 系统会自动给你的磁盘创建一个主分区 <br>
使用 `assign letter = d（你指定的卷标）` 为分区分配驱动器号或装载点 <br>
最后执行 `format quick` 进行快速格式化，便可以使用 **BalenaEtcher** 进行刻录了

    DISKPART> list disk
    
      磁盘 ###  状态           大小     可用     Dyn  Gpt
      --------  -------------  -------  -------  ---  ---
      磁盘 0    联机             1863 GB  1024 KB
      磁盘 1    联机              232 GB  2048 KB
    * 磁盘 2    联机              465 GB      0 B
    
    DISKPART> select disk 2
    
    磁盘 2 现在是所选磁盘。
    
    DISKPART> clean
    
    DiskPart 成功地清除了磁盘。
    
    DISKPART> create partition primary
    
    DiskPart 成功地创建了指定分区。
    
    DISKPART> assign letter = d
    
    DiskPart 成功地分配了驱动器号或装载点。
    
    DISKPART> format quick
    
      100 百分比已完成
    
    DiskPart 成功格式化该卷。
    
    DISKPART>

**注意：** 使用完后，必须使用该方法对磁盘进行清除并分区设置卷标，否则设备会无法使用

#### 下载并使用刻录工具

我一共使用了 3 种镜像刻录工具：[BalenaEtcher](https://www.balena.io/etcher/ "BalenaEtcher")、[Win32 Desk Imager](https://sourceforge.net/projects/win32diskimager/ "Win32 Desk Imager")、[Rufus](https://rufus.ie/ "Rufus")

其中功能最齐全的是 **Rufus** ，而 Win32 Desk Imager 就像是 Rufus 的简化版 <br>
但是这里最推荐使用的是 **BalenaEtcher** ，简单明了一步到位，但是需要安装

安装好我们的 BelenaEtcher 后，直接打开
点击 `Select image` 选择我们下载好的镜像，点击 `Select drive` 选择我们作为介质的 U盘，点击 `Flash！` 开始刻录。 <br>
静候片刻，等待出现了 `Flash Complete！` 即刻录完成。

**注意：** Fyde OS 及 CleadReady OS 的镜像无需解压直接刻录即可

![Etcher 刻录](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Etcher_Device_Flash.png "Etcher 刻录")

#### 设置 Bios

这里我们需要设置 U盘介质的引导项，我们首先需要将 **Bios** 中的 **F12 Boot** 打开

Chrome OS 的 U盘 介质引导启动，与我们的 Windows 引导启动有些不同 <br>
Chrome OS 需要将 `Bios` 中的 `Secure Boot` 设置为 `关闭（Disabled）`后才能顺利引导启动

**注意：**这里每个品牌主板的设置都不同，请参照自己的**主板品牌**并在 **Bios** 中找到对应的设置！

> 设置完这一步，我们就可以开始启动我们的 Chrome OS 系统了

![Bios Secure Boot 设置](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Bios_Secure_Boot.jpg "Bios Secure Boot 设置")

## 进入系统

#### 初步进入系统

先将刻录好的 U盘 介质插入电脑后，开机 <br>
在进入主板自检画面按 `F12` 进入我们的 **Boot 开机启动项**（也就是我们常说的开机第一屏，主板 Logo 画面）

找到你的 Chrome OS 启动盘 （一般为你的外置存储设备的型号 + 识别码）后选择启动

启动后会看到一个选择画面，Fyde OS 的为 `GNU GRUB version 2.02`，这里的选择需要根据你的 **CPU芯片** 进行选择，一般情况下**选择第一个即可**，随后就会看到 Chrome OS 的 Logo

![UEFI Boot](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/UEFI_BOOT.jpg "UEFI Boot")

#### 进入系统引导设置页面

**这一步我就不给截图了**

这一步非常简单，就跟新手机 & 刷机后，第一次进入系统的设置引导一样，连接网络，**登录 Google 账号**，即可进入系统

但是这里需要注意的是，除了 **Fyde OS** 直接注册一个 **Fyde 账号**登录就完成了之外，**CR OS & CM OSB** 都需要**登录谷歌账号才可以进入系统**！

这里我们大陆玩家，理所当然的就需要黑科技了：**一台可以配置 Shadowsocks 的路由器、一台已 Root 的 Android 设备**，二选一即可

路由器不用多说，直接在路由器管理页面配置 Shadowsocks 节点，然后电脑连上 Wifi 后，直接使用即可

若你**只有一台 Android 设备**，则你需要确保你的手机可以 Root 并已经成功 Root <br>
这时候，你需要去下载一个 HTTP注射器，给予该有的权限即可按照以下步骤进行操作 <br>
> 确保手机已经连接上 **Shadowsocks** 或其他代理，打开手机**移动热点** <br>
> **打开 HTTP注射器 → 工具 → Tethering Tools → 中继连接** <br>

最后让你的电脑连接热点 Wifi，即可正常登录 Google 账号

**到这里，先恭喜你，我们已经完成了 80% 了，你已经可以直接使用 Chrome OS 了** <br>
**若不需要将系统安装到硬盘，可以无视后面的所有步骤了，但不妨看看再走**

## 安装至硬盘

#### Chrome OS 命令行终端安装

**该操作，在系统设置引导页也可以执行** <br>
**此方法 3 个 OS 通用**

顾名思义，覆盖你的原系统，安装一个全新的系统 <br>
该操作**可能**会**直接 Clean 你的整个硬盘，并整合为一个盘符进行安装**

首先我们使用 `Ctrl + Alt + F2` 进入终端命令行，某些电脑需要加个 `Fn` <br>
会看到 `Localhost login` 直接输入默认用户名密码 `Chronos` 进入开发者模式 <br>
输入 `lsblk` 获得目前装载的物理磁盘列表。通常情况下，您PC里的物理硬盘将以sdX的形式显示。 <br>
根据提示的**磁盘空间大小和已分区的数量**，请您判断需要安装 Chrome OS 的**物理磁盘盘符**，比如 `sda`

**输入命令运行安装脚本**

> sudo /usr/sbin/chromeos-install --dst /dev/sda

输入后，出现 3 条提示以及一条 `Are you sure (y/n)?` 输入 `y` 即开始执行安装脚本

>  respect the privacy of others <br>
>  think before you type <br>
>  with great power comes great responsibility

什么意思自行理解了ww

到这里，你只需静静等待，直到最后出现以下提示，即表示安装完成，我们可以关机，拔下 U盘 介质，开始使用你的 **ChromeBook** 了

> Installation to '/dev/sda' complete. <br>
> Please shutdown, remove the USB device, cross your fingers, and reboot.

#### 安装器双系统安装

**关于双系统安装，似乎使用 命令行终端安装 也是可行的，但是因为我没有尝试，也就不写出来了** <br>
**等有空尝试了之后，会写出来供大家参考的**

关于安装器安装，Fyde OS 支持通过 **GUI 安装器**（当前处于测试阶段）来实现**全盘安装**或者**多重引导安装（即双系统）** <br>
**CloudReady OS** 以及 **Chromium OS Build** 任然只能通过 **U盘刻录** 进入系统之后才能通过 **Chrome OS 内的 应用程序 进行 Install** <br>

但是安装方法会比命令行终端安装**更简单明了**，大家可以尝试使用这种方式进行安装

## 结束语

到这里，**Chrome OS 安装笔记** 的两篇 Blog 就结束了，我已经尽量将我所知道的内容在这两篇文章说出来了， <br>
如果后续得到了 **补充情报或出现错字和内容错误** 我会及时进行修改。

第一次做了 Blog ，就写了这么长的文章，连自己都没有想到。 <br>
但是花了这么多精力写下这两篇文章肯定是值得的，毕竟这样我自己肯定就不会忘记了。 <br>
而且在写这篇文章的同时，我又学到了不少的东西，例如使用 **diskpart 管理磁盘**。

这样两篇文章便告一段落了，新的文章我自己也不知道什么时候会写出来，毕竟要上班，也没什么时间去玩新玩意了。 <br>
而且最近沉迷 **明日方舟** 无法自拔 ~~（不要打我）~~

非常感谢大家阅读完了这两篇文章，如果这两篇文章能为大家提供一些帮助，我会很开心。

~~最后说一句，德克萨斯天下第一！！~~
