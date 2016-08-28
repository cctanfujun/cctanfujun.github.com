---
layout: post
title: "如果你现在学Android"
subtitle: "写给想现在学习Android的朋友"
date: 2015-05-08
header-img: "img/post-bg-default3.png"
tags:
 - Android
---


虽然现在网上有不少Android的教程，不过现在Android的发展已经到了5.1，很多之前的开发教程和学习建议已经不是很适用，决定以自己的见解写一篇Android学习的教程，如果大家有什么好的意见或建可以评论给我。

# 工欲善其事，必先利其器
虽然Android开发的门槛比较低，但是有件得心应手的兵器还是很有必要的。 

* <strong>开发设备 ： Mac </strong>（作为开发者，我认为入手一台mac还是很有必要的，推荐还是mac pro，这种设备真的是早用早享受，如果你是学生党那么这真的是你对自己非常好的投资，如果你不是，那么我相信你是买得起的，购买渠道就不详细说了，港货确实能省一笔钱，官网分期无利息也是挺好的。如果你确定不购买的话，那么Linux开发也是比在Win下开发好一些的）


* <strong>调试设备 : 真机</strong> (推荐使用真机调试，速度更快)


* <strong>模拟器 ：genymotion</strong> （有时候还是要用到模拟器的，那么我推荐你使用geymotion，这货速度绝对比自带快很多，虽然自带模拟器也可以使用x86核心，不过速度依旧不如genymotion）


* <strong>IDE ：Android Studio</strong> (这里我想到一句别人说过的话，如果你是Android开发老老手，那么我推荐你使用Android Studio，如果你是新手，那么我更要推荐你使用Android Studio。其实我发现很多人在学习过程中继续使用eclipse的原因是，他看的的书或者视频教程使用的是eclipse，他们和我说新手就该用eclipse，除了一些做NDK开发的，我说的是专业人士，其他人请你们换成AS吧，去学习一下使用AS，也会有不少提升，至少比你照着视频敲看不懂的代码好)


* <strong>梯子 : 云梯</strong>（在我大天朝做开发有一架梯子还是很必要的，你可以去找一些免费的，不过速度确实渣。云梯是我用过的梯子里非常不错的，也有很多人推荐，你可以点我的推荐链接可以省一点钱！[推荐链接](http://kuaitizi.com/?r=868654b89611c354){:target="_blank"}


# 学习路线

## 入门级

* <strong>语言基础Java</strong> （使用Java语言。现在开发Android的方式有很多，如Hybrid开发，但如果你是新手，我推荐你使用原生开发，使用Java语言，因为任何跨平台开发最后你的web和Native都要精通，不然你总有解决不了的的问题） 



* <strong>Android官网</strong>  [http://developer.android.com/](http://developer.android.com/){:target="_blank"}  （需梯子）  
(Android官网更新其实很快的，你应该经常上去看看，需要梯子，如果你英文不错把Training部分练习一遍，就基本可以写一些小东西了)


* <strong>学习ApiDemo</strong>  ApiDemo 是很重要的，很多的功能其实Google官方以及帮我们做好了例子，只要学习一下就好了



* <strong>学习视频</strong> 其实我是很喜欢对着视频学习的，再用播放器调整为2-3倍速度播放，其实视频学习有利有弊吧，利就是你在学习一个知识点的时候，也附带学习了讲课者的思维方式，以及其他一些小知识点你也可能注意到（比如一些好用的插件，软件等）弊可能就是视频良莠不齐，开发方面的视频我并不认为存在什么经典，随着时间的流逝和技术的发展反而不再适用，盲目学习事倍功半。

  这里插入一个小广告吧，下载视频的话，可以关注我的微信公众平台晓晨学习组`（微信号：xiaochenAndroid）`，在里面你能找到学习视频下载，都是我认为不错的学习资源。然后我想说的是视频教程，重要的是理解思想，写代码要关了视频敲一遍，照着写实现了也没有什么提高。



* 遇到问题能Google少百度，可以到eoe找找，[stackoverflow](stackoverflow)，而且要多查查看看，注意文章日期，因为有些问题其实已经有了更好的解决方法，我举个例子，比如要在Android上实现下拉刷新，百度得到的内容基本都是使用pull-to-refresh这个第三方库，但是在Android官方提供的Support包里其实已经带了实现下拉刷新的快捷方法，而且效果更好。

## 进阶篇 
如果你完成了入门教程，那么你应该进阶了  

* **学习使用Git**  
  使用Git对于一个开发者来说是非常重要的。你并不需要成为一个Git专家，只要能正常使用基本就够了。我就推荐两个学习Git的教程吧！  
<br/>


  1. [廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000){:target="_blank"}  
  
  2. [猴子都能懂的Git入门](http://backlogtool.com/git-guide/cn/){:target="_blank"}
  

* 关注一些**开源项目**，并使用他们  
  Android开源库真的太多了，如果你不是特别闲的话，就去关注些大公司，或者知名开发者的，这里我推荐一些资源  
   <br/>
    
    
   [**Android开源项目分类汇总**](https://github.com/Trinea/android-open-project){:target="_blank"} 这是Trinea发起的开源项目整理，我很喜欢他说的，我们不重复造轮子，不代表我们要不知道轮子的原理。  
  
  <br/>
  
  
  [**List of Android UI/UX Libraries**](https://github.com/wasabeef/awesome-android-ui){:target="_blank"} 整理了各种Android UI库 
  
  <br/>
  
  
  
  [**代码家的博客**](http://blog.daimajia.com/){:target="_blank"} 代码家的很多UI 动画库做的非常不错，在他的博客里也很容易找到他的Github，就不贴了。
  
  <br/>
  
  
  [**codeKK源码分析**](http://codekk.com/open-source-project-analysis){:target="_blank"} 你可以看到些知名的库的分析  
  
  
  
 * 使用**第三方服务**  
  除了开源库，你还可以使用很多第三方服务来加快你的开发（如百度地图，ShareSDk等等)  
   这里我要推荐一个网站 [DevStore](http://www.devstore.cn/){:target="_blank"} 整理了大多数第三方开发者服务，不用你一个一个去找了。
 
   
 * **微博**   
  利用好微博这个工具，你可以关注一些开发者，微博上有很多乐于分享的人。你可以更快的的知道很新的开发的资讯。  
 <br/>
   我关注的人 [@代码家](http://weibo.com/u/1628291124?topnav=1&wvr=6&topsug=1){:target="_blank"}  [@googdev](http://weibo.com/u/2942550243?topnav=1&wvr=6&topsug=1){:target="_blank"}  [@开发者头条](http://weibo.com/kaifazhetoutiao?from=myfollow_group){:target="_blank"}  [@陈启超_V](http://weibo.com/chenqichao2016?from=myfollow_group){:target="_blank"}  
   还有很多不一一贴了，请自行搜索
 
 
 * **博客**  
    关注知名开发者的博客也是非常好提高技术的办法，具体到关注谁的问题，我建议你到[知乎]()上提问，有很多大神整理好的，包括国内国外的，我这里就链接几个我收藏的，因为有些大神的技术深度我目前还消化不了。  
 
   1. [晓_晨DEV的博客](http://tanfujun.cc/){:target="_blank"} 不错的博客，推荐关注
   
   2. [stormzhang博客精华](http://www.stormzhang.com/){:target="_blank"} 最近写了Android Studio的系列教程，推荐看看
   
   3. [代码家的博客](http://blog.daimajia.com/){:target="_blank"} 
   
   4. [Trinea的博客](http://www.trinea.cn/){:target="_blank"} 
   
   5. [脉脉不得语的技术博客](http://www.inferjay.com/){:target="_blank"}
   
   6. [胡凯的博客](http://hukai.me/){:target="_blank"} 之前翻译的Android性能优化的文章转载率很高 
   
   7. [Android官方培训课程中文版(v0.9.1)](http://hukai.me/android-training-course-in-chinese/index.html){:target="_blank"} 胡凯的github项目
   
   8. [ChenQichao's Blog](http://chenqichao.me/){:target="_blank"} 感觉他好像对material design情有独钟
   
   9. [Android Performance](http://androidperformance.com/){:target="_blank"} 主要是些译文，与性能优化有关  
   
      ---
   下面是CSDN部分，这部分有些我没有读过，只是看到Mark下
  
   10. [Android_Tutor的专栏](http://blog.csdn.net/android_tutor){:target="_blank"}  他写的“Android开发高手进阶教程”系列文章感觉不错
   
   11. [Hongyang](http://blog.csdn.net/lmj623565791){:target="_blank"}
   
   12. [郭霖的专栏](http://blog.csdn.net/guolin_blog){:target="_blank"}  《第一行代码》作者
   
   13. [任玉刚](http://blog.csdn.net/singwhatiwanna){:target="_blank"} 百度的工程师
   
   14. [Mr.Simple的专栏](http://blog.csdn.net/bboyfeiyu){:target="_blank"}
   
   15. [老罗的Android之旅](http://blog.csdn.net/Luoshengyang/){:target="_blank"} 罗升阳大神，博文质量非常高，《Android系统源代码情景分析》作者 
   16. [Innost的专栏](http://blog.csdn.net/innost){:target="_blank"}
   
    
   
 <br/>
 
 * **知乎专栏**  
 
   我之前有订阅AndroidWeekly邮件，不过是全英文的，可能是英文水平没有那么高看英文看久了就会累，后来在知乎上找到了翻译版专栏。推荐几个我的收藏。  
 
   <br/>
   [AndroidWeekly-知乎专栏](http://zhuanlan.zhihu.com/android-weekly){:target="_blank"}    
   <br/>
     [Android科学院](http://zhuanlan.zhihu.com/andlib){:target="_blank"}  
   
   <br/>

 
 * **搭建你自己的博客分享**  
   
   在开发中你总会碰到好久才能解决的问题，为了避免后来的人掉坑，搭建你的博客来和大家分享吧！  
  这点你可以参考[30分钟内拥有一个漂亮的博客教程](http://tanfujun.cc/%E4%BD%BF%E7%94%A8%E6%88%91%E7%9A%84%E6%A8%A1%E7%89%88%E6%95%99%E7%A8%8B/)

 
 * **我的收藏夹** 最后放一部分我的收藏夹内容  
   1. [AndroidDevTools](http://www.androiddevtools.cn/){:target="_blank"} 整理了不少Android开发需要用到的插件，自己看！ 
   
   2. [Material Design 中文版](http://design.1sters.com/){:target="_blank"}
   
   3. [AndroidCN](http://www.androidcn.org/){:target="_blank"} 一个朋友做的Android社区
   
   4. [伯乐在线](http://blog.jobbole.com/){:target="_blank"} 
   
   5. [推酷](http://www.tuicool.com/){:target="_blank"} 排版很不错，内容丰富
   
   6. [23code](http://www.23code.com/){:target="_blank"} 一个不错的源码分享网站，还有App，可以看效果
   
   7. [修炼源码](http://www.94ifeng.com/){:target="_blank"} 源码网站
   
   8. [谷歌开发者中文频道](http://boolan.com/gdg){:target="_blank"}  有不少谷歌的开发者视频，不用梯子就行
   

   
 
 



 
## 高手篇  


究竟什么是写代码的高手，可能每个人都有自己见解，在这里我其实不知道该写什么东西，我觉得每一个开发者最终的产物都是你的项目，所以你要做的并不是去炫技，而是写出更健壮、更易用的代码。那么我臆测该学的可能有如下： 


* 设计模式 （设计模式更像是一种经验的东西，知道和用是不一样的，根据代码能看出这是什么设计模式似乎很容易，但是高手总是能巧妙的运用他们，你看完后发现，好有道理哦！就是写不出来5555 。。。）



* 学习架构师方面的知识 （开发小项目看不出来，开发大一点的前期的设计真的很重要啊）



* 学习内核相关内容 （有去看过讲内核的沙龙，我就是打酱油的，需要汇编和c，大神讲的理所当然，我是一头雾水，不过深入还是有很多好玩的东西的）



* 写写算法 [leetcode](http://oj.leetcode.com/){:target="_blank"} 全A了，有些题其实还有更优解法的，但是我不推荐你做ACM的（大神请无视）基本上都是些数学内容。



* 学习设计 不会做设计的程序员不是好的产品经理，我最近在学习使用sketch，其实很好玩的。



* 学习各种新技术，做做小玩意（比如木匠活的什么的，我觉得挺好玩的），你除了是一个做技术的还要提高情商，不然你怎么追妹子啊！



* 锻炼身体 这个真的特别重要！！！




其实高手篇就是我写着玩的，大家随意看看就好，拍砖？我其实无所谓的啦！~~


##### 写在最后

整理码字不易，转载请注明  
欢迎关注我的博客 [晓_晨DEV](tanfujun.cc)   
有任何意见或建议 欢迎讨论
{: .notice}






 
 
 







