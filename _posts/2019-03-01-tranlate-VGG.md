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
们在 ImageNet Challenge 2014 提交代码的基础，在该挑战赛中，我们的团队取得了定位（localisation）
第一和分类（classification）第二的名次。我们也展示了我们的表征（representations）很好地泛
化到其他数据集上，在其他数据集上取得了最先进的（state-of-the-art）结果。我们公开了两种性能最
好的卷积神经网络模型去促进(关于深度可视表征（deep visual representations）在计算机视觉中的
使用的)进一步研究。
+ 介绍  
卷积神经网络近来在大规模图像和视频识别中取得了巨大的成功(Krizhevsky et al., 2012; Zeiler &
 Fergus, 2013; Sermanet et al., 2014; Simonyan & Zisserman, 2014)，使这个成功实现的是
 大规模公开的图像库，如ImageNet，和高性能的计算系统，如GPUs和大规模分布式集群。特别地，the ImageNet Large-ScaleVisual Recognition Challenge (ILSVRC)
 在深度可视识别架构的发展中扮演了重要的角色，ILSVRC是几代大规模图像识别系统的测试平台，从高维浅层
 特征编码到深度卷积神经网络。  
 随着卷积神经网络成为计算机视觉领域的日常用品，许多人竞先（in a bid）尝试提升Krizhevsky的原始
 架构，为了获得更好的准确率。 比如，