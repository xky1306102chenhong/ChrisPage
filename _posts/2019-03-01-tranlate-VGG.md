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
架构，为了获得更好的准确率。 比如，ILSVRC-2013性能最好的提交（submissions）在一层卷积层使用
更小的接受窗口和更小的步长。另一项提升卷积神经网络性能的做法是在整个图片和多个规模上密集地训练
网络和测试网络。<font color="red">在本文中，我们提出卷积神经网络架构设计的另一个重要方面-深度。
为此（to this end），我们先固定架构（architecture）的其他参数，然后通过添加更多的卷积层来慢慢
地增加网络深度。</font>  
最后，我们提出了准确率更好的卷积神经网络架构，这个网络架构不仅在ILSVRC的分类和定位任务上实现了
最先进的准确度，而且也应用到了其他的图像识别数据集上，在其他数据集上也取得了优异（excellent）表现，
甚至只是作为相对简单网络（pipelines）的一部分（比如，使用没有微调的线性SVM的深度特征分类）。我们
公开了两种性能最好的模型去促进进一步的研究。<font color="red">本文剩下的部分按如下组织。在第二部分（Sect.2），描述
我们的网络配置。在第三部分（Sect.3）陈述图像分类训练和评估的细节，然后四部分（Sect.4）
在ILSVRC分类任务中比较网络配置。第五部分（Sect.5）总结全文。为了完整性，我们也在附录A中描述和评估
我们ILSVRC-2014对象定位系统，在附录B中讨论深度特征到其他数据集的泛化。最后，在附录C中给出论文修改清单。</font>  
+ 网络配置  
