---
layout: post
title: 深度学习中的卷积运算
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>

深度学习中的卷积运算分三步：  
+ 输入数据的每个通道和对应卷积核的通道做‘对应元素求积在就和’
+ 各个通道的结果求和
+ 再加上偏置量  
  
这样就得到一个输出通道的一个元素
 
![avatar](/images/posts/2019-03-05/convolution.gif)

还有，有多少个输出通道，就需要几个卷积核，每个卷积核搭配一个偏置量。