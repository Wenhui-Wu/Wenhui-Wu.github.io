---
layout: post
title: Dell Update卡死在启动界面的解决方法
date: 2022-09-22 19:25 +0200
image:
tags:
- 生活
- 杂学
---

如果Dell Update会卡死在启动界面，或者SupportAssistant无法正常检查驱动更新，可以通过手动启动`Dell Client Management Service`来解决。

我遇到的问题是这样的：
在试图打开Dell Update的时候，程序会卡在Dell Update的蓝色巨幅Banner处，无响应大概持续一到两分钟之后Banner消失。
SupportAssistant也类似。
	尽管能成功加载程序，但是在检查驱动更新的那一步会反复报错，无法进行。

问题的根源在于`Dell Client Management Service`这个服务无法启动。
	而这个问题则可以通过删除`UpdateService`文件夹解决。
		这个文件夹的位置在`C:\ProgramData\Dell\`。
			需要注意的是`ProgramData`文件夹是默认隐藏的，需要通过`查看-显示-隐藏的项目`来显示。

删除文件夹，启动服务，Dell Update就能顺利打开了。
需要注意的是，删除文件夹的方法并不能根绝问题。
	也许第二次打开Dell Update的时候还会卡死。
	只好在有更好方法之前，多动动手啦。

这个方法来源于戴尔的客户服务。
小哥操作了一遍之后，被我悄悄记下来了。
不得不说戴尔的售后真的不错，但是程序也是真的不行……
