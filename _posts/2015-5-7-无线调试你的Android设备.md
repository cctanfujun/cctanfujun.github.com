---
layout: post
title: "无线调试你的Android设备"
subtitle: "省下一条数据线，用wifi连接你的Android真机"
date : 2015-05-07
tags :
 - Developer Tips

---

我的MBP只有两个USB口，连接上鼠标和机械键盘没有接口来插数据线了，反复插拔很麻烦，（之前买了个HUB，由于HUB是3.0接口连接上笔记本上不了网，大家注意如果给MBP买HUB要买2.0接口的，悲剧的送人了）决定研究下无线连接手机进行调试。

## 配置adb环境变量 

把你的adb添加到环境变量具体步骤如下：   

1. 找到android sdk的本地路径，adb命令在platform-tool下面,记为XXXX，我的路径是(/Applications/eclipse/android-sdk-mac_x86/platform-tools),这里你只需要找到SDK文件夹进入找到adb，按`command+i`可以先显示简介，在通用里面的位置，复制到终端就是文件路径。  

2. 打开终端输入  
`touch .bash_profile`   
`open -e .bash_profile`  点回车   

3. 添加路径   
.bash_profile打开了，我们在这里添加路径，如果打开的文档里面已经有内容,我们只要之后添加;XXXX(注意前面一定要用分号隔开)，如果是一个空白文档的话，我们就输入一下内容`export PATH=${PATH}:XXXX`  
保存，关掉这个文档。

4. 终端输入命令  `source .bash_profile `

5. 终端输入命令 adb点回车，如果未显示command not found，说明此命令有效，环境便亮设置完成。

---

## 无线连接手机（手动版）
这种方法需要一条数据线先进行设置，保证电脑和手机在相同wifi下

1. 配置好adb环境变量，使用USB数据线连接手机  
2. 在终端输入`adb tcpip 5555` (5555为端口号可以自行设置)
3. 断开USB线
4. 在终端输入`adb connect <设备ip地址>:5555`(ip地址可以在关于手机里面网络状态查到，不同手机略有区别)
5. 当需要使用数据线可以在终端输入`adb usb`

连接成功后安装以及显示Logcat都没有问题。

---

## 无线连接手机（app版） 

有些时候我们碰巧数据线坏了，或者找不到一条数据线，那么我们就要借助一个app了，下载adbWireless，在各大市场里面很好找（手机需要root）。  
还是要保证相同wifi下，启动这个应用

![adbWireless]({{site.url}}/images/S50508-015351.jpg)    


然后在终端输入`adb connect ip`即可（ip软件上有显示）





