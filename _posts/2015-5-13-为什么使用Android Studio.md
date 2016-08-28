---
layout: post
title: "Why Android Studio 及Tips"
subtitle: "告诉你为什么要使用 Android Studio 以及一些好用的地方"
header-img: "img/post-bg-default4.png"
author:    "晓晨DEV"
date: 2015-05-13
tags: 
 - Android 
---


Android Studio作为Google推荐开发Android使用的IDE，今后成为Android开发的主要工具是毋庸置疑的，从Eclipse过度过来的你要如何使用它呢！   

# 为什么使用Android Stuido
 
 * 比Eclipse速度更快
 * 可视化编辑UI
 * Darcula主题 
 * 更强大的代码提示
 * 智能保存
 * 内置终端
 * 完善的插件系统
   
---

# 开始阶段 

其实上手一个新的IDE并没有什么复杂的地方，目前也有很多Android Studio的教程，我整理一些，你简单看看就可以上手了。我就总结些你应该注意的地方。   
 
 * 使用Eclipse快捷键。我并不是推荐你使用Eclipse的快捷键，而是你如果是从Eclipse过度过来的用户这样会非常容易上手，网上关于Android Studio快捷键部分的教程我认为是没有意义的，你可以自己去定义你的快捷键。
 * 使用Gradle构建项目。这里是Android Studio和Eclipse不同的地方，我认为也是一个非常好用的地方，虽然第一次上手可能稍有困惑，但是如果你简单看看，也是很容易掌握的，文章后面我也会整理一些Gradle学习资源。
 * Android Studio 插件，虽然Eclipse也有一些插件，感觉仓库的管理不如AS。
 * 第一次使用注意事项：最好连接VPN，因为第一次要下载gradle，虽然你也可以用本地的，但是新手也许并不会设置；设置黑色主题；设置好快捷键；完成你的Hello Android Studio吧！
 
**推荐学习文章**
  <br/><br/>
[Google利器Android Studio从入门到精通](http://yanbober.github.io/2015/01/28/android_studio_guide/?bsh_bid=612588611){:target="_blank"}

---

# Gradle学习

Android Studio 使用Gradle来构建项目，那么需要你对Gradle有一些了解
<br/><br/>
**推荐学习文章**
<br/><br/>
[使用Gradle构建Android程序](http://rinvay.github.io/android/2015/04/09/Build-Android-with-Gradle/){:target="_blank"}
<br/><br/>
[Gradle插件用户指南(译)](http://rinvay.github.io/android/2015/03/26/Gradle-Plugin-User-Guide(Translation)/){:target="_blank"}
<br/><br/>
[stormzhang Android Studio 系列教程](http://www.stormzhang.com/){:target="_blank"}
<br/><br/>
[美团Android自动化之旅—生成渠道包](http://tech.meituan.com/mt-apk-packaging.html){:target="_blank"}
<br/><br/>
[美团Android自动化之旅—适配渠道包](http://tech.meituan.com/mt-apk-adaptation.html){:target="_blank"}


---

# Android Studio Tips

整理一些好用的Tips

* 使用Genymotion模拟器，Android Studio也有genymotion插件
<br/><br/>
* 你可以设置logcat颜色，这样调试信息更加显而易见。打开* `setting>editor>Color & Fontd>Android Logcat`进行设置.
<br/><br/>
* 在xml界面里可使用`tools`属性来预览
<br/><br/>
* 你可以使用插件来控制你的编码规范
