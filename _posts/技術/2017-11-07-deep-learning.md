---
layout: post
title:  深度学习
category: 技术
tags: Deep Learning
keywords:
---

# API

- [gluon API ](https://mxnet.incubator.apache.org/api/python/index.html)

CNN 
https://hjtso.github.io/2017/09/16/zh-Deep-learning%E7%AC%94%E8%AE%B02-CNN%E5%8D%B7%E7%A7%AF%E7%A5%9E%E7%BB%8F%E7%BD%91%E7%BB%9C/zh/


# win10 mxnet gpu 安装
1. 下载并安装 virtual studio 2015 community

  不安装的话,cuda安装会出错, 遇到过黑屏
    
2. 下载cuda8.0  

  目前官方网站只显示cuda9.0,通过此链接下载[cuda8.0](https://developer.nvidia.com/cuda-80-ga2-download-archive)
  cmd窗口 nvcc -V   有结果表示安装成功
  
3. 下载并安装 [miniconda](https://conda.io/miniconda.html)

4. 安装 mxnet-cu80

  先卸载 cpu版mxnet   pip uninstall mxnet
  再安装 mxnet-cu80   pip install --pre mxnet-cu80
  
  
[为你的深度学习任务挑选性价比最高GPU](https://www.jiqizhixin.com/articles/2016-07-18-4)
  



