---
layout: post
title: Java开发工程师面试题集
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>

+ **自我介绍**
+ **介绍一下™、®、©、sm四个标识的含义?**
  + ™(Trademark)：商标，但没有法律含义和法律效力。
  + ®：指的是注册商标，表示商标已经注册成功。
  + ©：表示受版权保护的标识。
  + SM：服务标识(Service Mark)  
  
  ![avatar](/images/posts/2019-03-05/tm.png)
+ **Java规范(Java Specification)制定过程?**
  + [JCP](https://zh.wikipedia.org/wiki/JCP)(Java Community Process):是一个由Oracle(以前是Sun)领导的机构(mechanism)，通过[JSRs](https://zh.wikipedia.org/wiki/JCP)(Java Specification Requests，Java规范请求)的方式<span style="border-bottom:2px solid red;">制定Java技术的标准技术规范。</span>
  + JSR变为final状态前需要正式的公开审查，并由JCP Executive Committee投票决定。最终的JSR会提供一个参考实现，它是免费而且公开源代码的；还有一个验证是否符合API规范的Technology Compatibility Kit。
  + JCP设有执行委员会(EXECUTIVE COMMITTEE,EC)，阿里巴巴是执行委员会里唯一的中国公司。
+ **说说Java SE、Java EE和Java ME的关系？**
   + Java SE(Java Platform, Standard Edition): <span style="border-bottom:2px solid red;">Java平台</span>，标准版可以在桌面(desktops)和服务器(servers)上开发和部署Java应用。JDK(Java SE Development Kit)实现了Java SE规范，例如有Oracle JDK，OpenJDK和AJDK等。
   + Java EE(Java Platform, Enterprise Edition): <span style="border-bottom:2px solid red;">Java平台</span>，企业版是社区驱动的企业软件的<span style="border-bottom:2px solid red;">标准</span>(例如Servlet、JAX-RS、JMS等)。2018年3月更名为Jakarta EE。Oracle提供的Java EE 8 Platform SDK是Java EE规范的参考实现。
   + Java ME(Java Platform, Micro Edition): <span style="border-bottom:2px solid red;">Java平台</span>，微型版为在嵌入式和物联网中的移动设备上运行的应用提供一个强健的、灵活的环境。
+ **为什么会存在J2SE与Java SE、J2EE与Java EE和J2ME与Java ME？**
  + 因为在Sun公司在1998年发表JDK1.2版本的时候，使用了新名称Java 2 Platform，所以就出现了J2XX。
  + 因为在2005年6月，JavaOne大会召开，SUN公司公开Java SE 6。此时，Java的各种版本已经更名以取消其中的数字“2”：J2EE更名为Java EE, J2SE更名为Java SE，J2ME更名为Java ME。
+ TCP(三次握手四次挥手，与UDP的区别，流量控制原理)
+ 排序算法
+ 5亿的数据如何排序
+ 进程间通信方式，那种效率高
+ 讲一下进程和线程的区别
+ 如何找数组内第二大元素
+ 两个非空链表相加
+ 剑指Offer
+ String和StringBuffer的区别