---
layout: post
title: Android代码片段
excerpt: "Android代码片段"
tags: [Android]
categories: [Android]
modified: 2016-03-21
comments: true
---

#单例模式 

## 双重校检写法

```java

public class Singleton{
  private volatile static Singleton singleton;
  private Singleton(){}
  public static Singleton getSingleton(){
    if(singleton == null){
      synchronized (Singleton.class){
        if(singleton == null){
          singleton = new Singleton();
        }
      }
    }
  }

}



```

## 静态内部类写法

```java

public class Singleton { 
  private static class SingletonHolder {
  private static final Singleton INSTANCE = new Singleton(); 
  } 
  private Singleton (){} 
  public static final Singleton getInstance() { 
    return SingletonHolder.INSTANCE; 
  } 
}

```