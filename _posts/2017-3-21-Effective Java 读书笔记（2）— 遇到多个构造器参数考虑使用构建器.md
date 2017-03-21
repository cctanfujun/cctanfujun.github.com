---
layout: 	post
title: 	Effective Java 读书笔记（2）— 遇到多个构造器参数考虑使用构建器
subtitle: 	"Effective Java 读书笔记"
date:       2017-3-21
author:     "晓晨DEV"
header-img: "img/post-bg-default1.png"
tags:
 - JAVA 
 - 读书笔记

---



## 遇到多个构造器参数考虑使用构建器

对于需要多参数构建的对象使用 Builder 模式

```java
public class NutritionFact3
{
    //均是final，不可变
    
    private final int servingSize;// required
    private final int servings;// required
    private final int calories;// optional
    private final int fat;// optional
    private final int sodium;// optional
    private final int carbohydrate;// optional

    public static class Builder
    {
        // 必须参数
        private final int servingSize;// required
        private final int servings;// required

        // 可选参数
        private int calories = 0;// optional
        private int fat = 0;// optional
        private int sodium = 0;// optional
        private int carbohydrate = 0;// optional

        // 必须参数必须通过通过构造参数传递
        public Builder(int servingSize, int servings)
        {
            this.servingSize = servingSize;
            this.servings = servings;
        }

        // 构建calories,返回本身，以便可以把调用连接起来
        public Builder calories(int calories)
        {
            this.calories = calories;
            return this;
        }

        // 构建sodium
        public Builder sodium(int sodium)
        {
            this.sodium = sodium;
            return this;
        }

        // 构建fat
        public Builder fat(int fat)
        {
            this.fat = fat;
            return this;
        }

        // 构建carbohydrate
        public Builder carbohydrate(int carbohydrate)
        {
            this.carbohydrate = carbohydrate;
            return this;
        }

        //build,返回NutritionFact3
        public NutritionFact3 build()
        {
            return new NutritionFact3(this);
        }
    }

    // 隐藏构造函数
    private NutritionFact3(Builder builder)
    {
        servingSize = builder.servingSize;
        servings = builder.servings;
        calories = builder.calories;
        fat = builder.fat;
        sodium = builder.sodium;
        carbohydrate = builder.carbohydrate;
    }
    
    public static void main(Stringargs)
    {
        NutritionFact3 cocaCola = new NutritionFact3.Builder(240, 8).calories(100).sodium(35).carbohydrate(27).build();
    }
}


```

Builder 模式可以有多个可变参数。叠构造器模式参数一多就很头疼，而用 JavaBean 自身去构建 set 又会让 Bean 在构造过程中处于几个状态。Builder 模式是比较优秀的。