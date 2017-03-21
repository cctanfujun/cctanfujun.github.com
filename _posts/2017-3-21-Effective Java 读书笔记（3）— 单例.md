---
layout: 	post
title: 	Effective Java 读书笔记（3）— 单例
subtitle: 	"Effective Java 读书笔记"
date:       2017-3-21
author:     "晓晨DEV"
header-img: "img/post-bg-default2.png"
tags:
 - JAVA 
 - 读书笔记

---


## 单例

1. 利用反射可能从单例类中再生成一个对象,这里可以加上保护机制在生成第二个对象的时候报错

2. 反序列化可能会再生成一个对象，如果没有正确处理

3. 枚举可能是最好的单例

```java

public enum Elvis{
  
  INSTANCE;
  
  public void something();
  
}

```