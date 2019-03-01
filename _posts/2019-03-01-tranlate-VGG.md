---
layout: post  
title: 针对大规模图像识别的特深的深度卷积神经网络  
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>  

> 翻译自[VGG](https://arxiv.org/abs/1409.1556)

+ 摘要  
在本文的工作中，我们研究在大规模图像识别中卷积网络深度对识别准确度（accuracy）的影响。<font color="red">我们的
主要贡献是一个全面的(对增加深度的网络)的评估，这种网络使用很小(3x3)的卷积过滤器，这种使用这种
过滤器的网络显示，当网络深度深至16-19层时可以在现有(prior-art)配置上取得极大的提升。</font>这些发现是我
们在 ImageNet Challenge 2014 提交代码的基础，在该挑战赛中，我们的团队定位（localisation）
第一和分类（classification）第二的名次。我们也展示了我们的表征（representations）很好地泛
化到其他数据集上，在其他数据集上取得了最先进的（state-of-the-art）结果。我们公开了两种性能最
好的卷积神经网络模型去促进(关于深度可视表征（deep visual representations）在计算机视觉中的
使用的)进一步研究。
+ 介绍
