---
layout: 	post
title: 	Effective Java 读书笔记（1）— 静态工厂方法代替构造器
subtitle: 	"Effective Java 读书笔记"
date:       2017-3-21
author:     "晓晨DEV"
header-img: "img/post-bg-default5.png"
tags:
 - JAVA 
 - 读书笔记

---

### 静态工厂方法代替构造器

优势： 

* 有名称
* 不必在每次调用时候创建一个新的对象
* 可以返回原类型的任何子类型的对象
* 创建参数化类型实例的时候使代码更加简洁

缺点：

* 类如果不含公有或者受保护的构造器就不能实例化
* 和其他构造方法没有区别

===

静态工厂方法就是给类加上一个静态方法；

```java

public final class Boolean implements java.io.Serializable,
        Comparable<Boolean> {

    public static final Boolean TRUE = new Boolean(true);
    public static final Boolean FALSE = new Boolean(false);

    public static Boolean valueOf(boolean b) {
        return (b ? TRUE : FALSE);
    }
}

```

1. 因为方法有名称，我们通过方法名知道了创建了什么对象，而不用对比构造器里面每一个参数。

2. 创建的不一定是新对象，可能是返回之前的对象。

3. 返回具体对象时候有更大的灵活性。

```java

public abstract class EnumSet<E extends Enum<E>> extends AbstractSet<E>
    implements Cloneable, java.io.Serializable {

    EnumSet(Class<E>elementType, Enum[] universe) {
    }
    //RegularEnumSet与JumboEnumSet均为EnumSet的子类
    public static <E extends Enum<E>> EnumSet<E> noneOf(Class<E> elementType) {
        if (universe.length <= 64)
            return new RegularEnumSet<>(elementType, universe);
        else
            return new JumboEnumSet<>(elementType, universe);
    }
}

```

4. 简化声明

```java

//常规实例化方式
Map<String, List<String>> m =
    new HashMap<String, List<String>>();

public static <K, V> HashMap<K, V> newInstance() {
    return new HashMap<K, V>();
}
//使用静态工厂方法实例化，简化繁琐的声明
Map<String, List<String>> m = HashMap.newInstance();

```

劣势：

1. 因为类的构造方法是 private，就不能通过继承扩展该类。但是同样是鼓励我们使用组合而不是继承。

2. 本质上是个静态方法，在api文档上不能够很好的标识出来，通常用命名弥补。

  * valueOf - 返回实例与的参数有相同值
  * of - valueOf 简洁版
  * getInstance - 返回的实例通过方法参数描述。Singleton 返回唯一实例
  * newInstance - 每次返回新的对象
  * getType - 返回对象的另一个不同的类
  * newType - 同 getType 但每次返回新的对象


  