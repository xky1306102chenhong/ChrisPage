---
layout: post
title: String、StringBuffer和StringBuilder辨析
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>

+ String  
  + 不可变对象
+ StringBuffer
  + 可变对象
  + 线程安全
  + 多数情况下，速度上StringBuffer快于String  
  ```java
  //String的速度快于StringBuffer
  String S = "Hello" + "Worl" + "d!";
  StringBuffer = new StringBuilder("Hello").append("worl").append("d!");
  
  //StringBuffer的速度快于String
  String S1 = "Hello";
  String S2 = "Worl";
  String S3 = "d!";
  String S = S1 + S2 + S3;
  StringBuffer = new StringBuilder("Hello").append("worl").append("d!");
  ```
+ StringBuilder
  + 可变对象
  + 非线程安全
  + 用在字符串缓冲区被单个线程使用的时候（这种情况很普遍）
  + 多数情况下，速度快于StringBuffer