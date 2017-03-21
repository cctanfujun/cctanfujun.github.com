---
layout: 	post
title: 	Effective Java 读书笔记（4）—  通过私有构造器强化不可实例化能力
subtitle: 	"Effective Java 读书笔记"
date:       2017-3-21
author:     "晓晨DEV"
header-img: "img/post-bg-default3.png"
tags:
 - JAVA 
 - 读书笔记

---


## 通过私有构造器强化不可实例化能力

```java

public class UtilityClass {
    // Suppress default constructor for noninstantiability
    //错误是为了防止有人调用构造函数
    private UtilityClass() {
        throw new AssertionError();
    }
}

```

这种工具类不想被实例化，私有构造方法，抛出一个error。

劣势: 子类不能访问父类构造函数