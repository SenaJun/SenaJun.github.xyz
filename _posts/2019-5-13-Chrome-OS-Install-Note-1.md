---
layout:     post
title:      Chrome OS 安装笔记
subtitle:   OS 对比及个人看法
date:       2019-05-13
author:     SenaJun
header-img: img/Chrome_OS_Install_Note/Fyde_OS_Lock.png
catalog: true
tags:
    - Chrome OS
    - 安装笔记
    - 个人看法
---

# Chrome OS 安装笔记 - OS 对比及个人看法

![Fyde OS 锁屏画面](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Lock.png "Fyde OS 锁屏画面")

### 前言

了解到 **Chrome OS** 的原因，是去年看到了 **Google Pixel Slate** 设备为契机，第一次接触到了 **Chrome OS** 系统，也对其相当的感兴趣。但当时因为没有多余的设备，也找不到官方的**镜像文件（固件）**而放弃了。

直到前几天，因为双十二组装了电脑，公司也分配了工作用的笔记本，有了多余的设备可以拿来 ~~搞事情~~。在前段时间，在刷**IT之家**的时候，无意中刷到了一篇关于国内二次开发的 **Chrome OS** 的文章，同时也不想浪费前段时间才买的 **860 EVO**，便又再次燃起了兴趣。

> **关于图片：** 因为在安装过程中，没有拍摄过多的照片，也没有找到在安装过程中截屏的方法，因此只能使用手机拍摄的一些照片来做示意，还请见谅。

------

### 关于 U盘刻录 & 硬盘安装

这一项我会在另外一篇 **Chrome OS 安装笔记 - 安装过程** 中详细说明，这里只做简单的阐述

> Chrome OS 有三种安装方式：**U盘刻录、硬盘安装、双系统硬盘安装**

后两者大家肯定都很清楚了，这里稍微说明一下 <br>
**Chrome OS 的 U盘刻录**与我们平时安装 **Windows10** 时所制作的**（PE）启动盘** 有很大的不同 <br>
在这里的 **U盘刻录** 是将整个系统直接安装在了 **U盘** 内，你可以直接在电脑插入 **U盘** 并**直接启动系统**，这点玩过 Linux 的人应该大部分都会知道这个~~（我才不会说我不知道，因为我没怎么玩过 Linux）~~

若只是想简单体验 Chrome OS 的朋友，这种方式是最为便捷，最为简单的，你只需要一个 U盘，一台电脑，甚至不会对电脑内的数据照成任何影响。

但若你想要将系统从 **U盘 安装到 硬盘**，此时安装到 U盘 的 OS 内的一个 **Install** 功能就起作用了 <br>
它可以帮助你直接将 U盘 内的 OS 安装到硬盘中

**注意： 这会格式化你的硬盘并整合成一个盘符！**

------

### 首先先介绍一下我了解到的三个版本的 Chrome OS

> - [Chromium OS Build](http://dev.chromium.org/chromium-os "Chromium OS Build")
> - [CloudReady OS](https://www.neverware.com/freedownload "CloudReady OS")
> - [Fyde OS](https://fydeos.com/ "Fyde OS")

####  Chromium OS Build

这是 **Google** 放出的一个 **Chrome OS** 的 **Build 版本**，即为 **Chromium OS Build（下称 CM OSB）** <br>
据我的了解和使用后的体验，这只是一个只能使用 **Android** 基础功能的，带有 **Chromium（Chrome）浏览器** 的，固件体积只有 **500MB** 左右，刻录在 U盘 后大概是 **4.5GB** 左右的的一个开发以及体验~~（老设备续命）~~用 OS 

内置的 Chromium 浏览器 功能齐全，登录 Google 账号后，会自动同步账号数据以及浏览器插件（APPs），完全可以当作我们日常使用的 Chrome 来使用。

其次需要注意的一点是，CM OSB **无法使用 Google Play Store** 同样的，只能使用 Chrome 中的扩展插件以及 Chrome 网上应用商店内的应用，同时也不能在浏览器中下载应用进行安装，打开应用程序 APK 时，会提示：

> **不支持此文件类型。请访问 Chrome 网上应用店，找到能打开此文件类型的应用**

------

#### CloudReady OS（下称 CR OS，此为官方缩写）

这是国外经过 **二次开发** 的 Chrome OS 系统，UI 在 CM OSB 的基础上有一定的修改~~（算不算美化呢，感觉没太大区别）~~ <br>
CR OS 在使用体验上发现了一个问题，其实就是 CM OSB 上增加了一小部分功能而已，在使用上两者没有太大~~（几乎）~~的区别。 <br>

但我在官网上发现了 CR OS 有三个面向客户群：

> - 面向个人以及学生使用
> - 面向教育机构的教育版
> - 面向企业机构的企业版

除开**个人免费版**之外，另两个是**收费使用**的 <br>
使用收费版本，似乎会获得 **Chrome 管与 Google 管理控制台之间的完全兼容** <br>
关于**收费版**的进阶功能，或者其收费版是否能够支持 Play Store 或者安装其他 APK 这点并不清楚 <br>
但是根据推油 **某推友（此处匿名，如有需要我会写出是谁）** 所提供的情报所知，CR OS 是并不能够支持 Play Store 的 <br>
这似乎是由于 Chrome OS 某些地方没有开源共享的原因

如需了解更多，请点击下方链接了解详情： <br>
https://neverware.zendesk.com/hc/en-us/articles/221303948-Does-CloudReady-support-the-Google-Play-Store-Android-Apps-

**值得注意的是：**  <br>
CR OS 在设置中有一项，有一项 **Linux（测试版）** 的设置，该设置是一个安装项目 <br>
**安装后，可在你的 Chrome OS 设备上运行 Linux 工具、编辑器和 IDE** <br>
![Chrome OS Linux 工具](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Linux_Tools.jpg "Chrome OS Linux 工具")

安装后，即会在你的设备中添加 Linux 终端，并单独为 Linux 做了一个分区

![Linux 终端](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Linux_Terminal.png "Linux 终端")

**这在一定程度上，增加了该 OS 的可用性以及实用性**

------

#### Fyde OS

最后关于 Fyde OS，与 CR OS 相同，这是一个经过**国内二次开发**的 OS  <br>
但 Fyde OS，出乎意料的让我简单的体验到了一个**严格意义上很不完整的**，但是比起前两款 OS 更有使用体验的 Chrome OS

为什么说它严格意义上不完整呢 ？

有一个决定性的因素，因为他是国内二次开发的 Chrome OS，理所当然的，也缺少了 **Google 套件**，但关于这点，稍后还有补充说明**~~（调侃官方）~~** <br>
正因为它缺少了 **Google 套件**，在第一次进入系统的时候，也就缺少了 **Google 账号登录认证**，相信知道 Chrome OS，以及玩过 Android 刷机的朋友们，都知道这个，就不过多阐述。

但这并不能说它不完整，反而没有 **Google 账号登录认证**，对于大部分用户来说是个好处。

它的 Chromium 浏览器，是经过 **Fyde OS 特别定制**的 Chromium 浏览器。相信看到**特别定制**这四个字的人应该猜到了。 <br>
是的，这个经过特别定制的 Chromium，**无法登录 Google 账号**，为什么？**因为它把这个功能完美的砍掉了**，只保留了浏览器除了账号同步外，的完整功能。

![Fyde OS Chromium 版本](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Chromium.png "Fyde OS Chromium 版本")

这一点让我很是难过，但它的其他特点和优点，弥补了它这一不足。

大家在我的截图下方任务栏可以看见，我已经使用上了** Play Store**，甚至安装上了** Telegram**。 <br>
没错，Fyde OS 是**支持 Play Store** 的，**这意味着 Fyde OS 可以正常安装 APK 应用程序 ！** <br>
我甚至在其应用抽屉中看到了 **安卓设置**，当我进入关于设备中查看的同时，我很是惊讶。 <br>
Fyde OS 使用的是 **Android Pie**，也就是我们的 **Android 9.0 系统 ！** <br>
我们甚至可以打开 Pie 所内置的 **Android 彩蛋**

![Fyde OS 安卓版本](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Android_Pie.png "Fyde OS 安卓版本")

但是应用的兼容性似乎并不怎么样 <br>
我利用 **Play Store** 以及 **酷安**，安装了一部分应用，甚至游戏 <br>
兼容性方面还有待我去慢慢测试，有兴趣的朋友可以看我后续 **安装笔记 - 安装过程**，自行安装 Chrome OS 后使用体验

**值得注意的是：** <br>
**Fyde OS 与 CR OS 相同，拥有 Linux（测试版）设置，可以在你的 Fyde OS 中安装 Linux 终端使用。** <br>
当然，这可用性以及实用性远比 CM OSB 以及 CR OS 要高得多。

------

### 关于 Chrome OS 的交互体验

当然，我一开始就是冲着在桌面平台运行桌面版 Android 的目的来的 <br>
当初看到 **Google Pixel Slate** 的桌面 UI 的时候，就被吸引住了

但关于 **Chrome OS 的交互设计体验**，是不是每个人都喜欢这并不好说，但至少我是很喜欢的 <br>
但是论交互动画之类的一些东西，肯定是 Mac OS 做的更好，但因为我并没有使用过 MacBook，这里也不拿出来做对比了ww <br>
我可以很直白的说，Chrome OS 的 UI 以及交互动画方面，是我喜欢的类型。

因为 Android 系统也是 Linux 系统，**Chrome OS 若加上 Fyde OS 和 CR OS 的 Linux 终端** <br>
实用性或许不比图形界面的 Ubuntu 之类的 Linux 系统差。

但就目前来说，我觉得肯定还是比不上的，而这就全看后续大家的使用对比后的体验了。

![Fyde OS 功能按钮 & 通知栏](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Notification_Panel.png "Fyde OS 功能按钮 & 通知栏")

------

### 调侃一下 Fyde OS 的官方

按照 Fyde OS 官方的说法，Fyde OS 内是无法使用也不提供 Google 服务的，并很清楚的指出法律，说是违法行为来着ww <br>
在使用中，你也无法在应用抽屉以及设置中找到 Google 服务框架、Play Store 一系列应用

当然，Chromium 浏览器也直接砍掉了 Google 账号同步，我称其为经过 Fyde OS 定制的 Chromium 浏览器

**划重点：目前 Fyde OS 没有任何携带 Google Play Store 的企图**，这是官方给出的说法

但你不妨下载一个 **酷安** 并搜索 **Google Play Store** 之后你会发现，Play Store 后并不是 **安装** 按钮，而是 **打开** 按钮

**我们直接点击打开，就可以正常使用 Play Store 了，我甚至发现，其内置的 Google 服务套件，都快比我的美版 Samsung Galaxy S8+ 还齐全了...**

![Fyde OS 官方对于 Google 服务的说法](https://raw.githubusercontent.com/SenaJun/SenaJun.github.io/master/img/Chrome_OS_Install_Note/Fyde_OS_Google.png "Fyde OS 官方对于 Google 服务的说法")

------

### 最后

从可用性和实用性的角度出发，我个人认为 Fyde OS 是远比 另两款 OS 要强的多的 <br>
但是需要注意的是，Fyde OS 的 Chromium **无法登录 Google 账号同步**，以及文件管理器中并**没有内置 Google Drive**，这一点可能会让你有点头大， <br> Google Drive 还好，安装 APK 便完事了，但 Chromium 的 Google 账号同步可能就比较麻烦了。

CR OS 以及 CM OSB，并**不推荐用来当作主系统使用**，除非你真的有需要，因为对于我来说实用性实在是太低了 <br>
当然，若你想为你的老设备续命，不妨可以试试这几款 OS <br>
你甚至可以将其当作一台**安装了 Chrome OS 的 Linux 设备**使用
