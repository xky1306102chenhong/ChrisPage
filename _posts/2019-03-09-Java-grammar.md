---
layout: post
title: Java语法
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>

+ Java的运行机制  
`*.java--编译(javac)-->*.class--JVM解释执行(java)-->特定平台的机器码`  
+ 注释  
```
1. // 单行注释
2. /* 多行注释*/
3. /**
    *文档注释
    */
 ```
 + 标识符规则  
 ```
 1. 可由字母、数字，下划线，美元符组成，但不能以数字开头。
 2. 不能是Java关键字、保留字和三个特殊直接量
 ```
 + Java关键字  
 Java关键字都是小写的，有50个(两个为使用但关键字goto和const也称为保留字)  
![avatar](/images/posts/2019-03-09/JavaKeyword.png)  
+ 三个特殊直接量  
`true, false, null`
+ 八种基本数据类型  
![avatar](/images/posts/2019-03-09/JavaBasicDataType.png)   
![avatar](/images/posts/2019-03-09/JavaDataType.jpeg)
+ 自动类型转换、强制类型转换和表达式类型的自动提升
+ 常量池  
当程序第一次使用某个字符串直接量时，Java会使用常量池(相当于集合，不会有重复元素)来缓存该字符串直接量。
如下：
```java
String s0 = "Hello";
String s1 = "Hello";
String s2 = "Hel"+"lo"
System.out.println(s0 == s1);
System.out.println(s0 == s2);
// 输出：
// true
// true
```
+ 运算符  
+ 顺序结构
+ 分支结构
+ 循环结构
+ 循环控制(break, continue, return)
+ 数组  
`1. 数组是一种引用数据类型`  
`2. 没有多维数组`
`3. 工具类Arrays`
```java
/**
 * @author Chris Chen
 * @date 2019/3/10 下午7:05
 */
public class Test {
    public static void main(String[] args) {
        int[][] a;
        a = new int[4][];
        for (int i=0;i<a.length;i++){
            System.out.println(a[i]);
        }
        a[0] = new int[1];
        a[0][0] = 0;
        a[1] = new int[2];
        System.out.println(a[0].length);
        System.out.println(a[1].length);
    }
}

```  
+ 引用数据类型  
`堆内存、栈内存和垃圾回收机制`  
