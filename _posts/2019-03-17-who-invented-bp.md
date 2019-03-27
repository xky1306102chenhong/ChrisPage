---
layout: post  
title: 谁发明了误差反向传播算法  
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>  

> _翻译自http://people.idsia.ch/~juergen/who-invented-backpropagation.html_

高效的误差反向传播算法(bp)是进行卷积神经网络复兴和深度学习的关键。哪是谁发明了反向传播算法呢？

误差反向传播算法的现代版本(也称为自动微分)是由芬兰的硕士生Seppo Linnainmaa在1970年首次发表。
尽管误差反向传播算法的一些重要概念甚至在更早就为人熟知。


很容易找到BP历史的误导性记录(截至2014年7月)。
我看过1960s和1970s的原始论文，并且和误差反向传播算法的先驱者谈过。
这里有一个源于我2014年的[调查报告](http://people.idsia.ch/~juergen/deep-learning-overview.html)的一个总结，这个总结还有一些其他的参考文献：

在复杂的、非线性的、可微分的、多阶段的NN相关系统的参数空间中 **通过梯度下降最小化误差(Cauchy 1847, Hadamard, 1908)** 至少在1960年代早期就已经被讨论(比如，Kelley, 1960; Bryson, 1961; Bryson and Denham, 1961; Pontryagin et al., 1961; Dreyfus, 1962; Wilkinson, 1965; Amari, 1967; Bryson and Ho, 1969; Director and Rohrer, 1969)，
通过梯度下降最小化误差最早出现在**变分法(the Calculus of Variations)**中的**欧拉-拉格朗日方程(Euler-LaGrange equations)**的框架内。

在这种系统的权重空间中最速下降法(steepest descent)可以通过以动态规划的方式迭代链式法则来执行。
这种误差反向传播方法的简化推导仅使用链规则（Dreyfus，1962）。

1960s的这种系统以DP的方式就已经很高效了。