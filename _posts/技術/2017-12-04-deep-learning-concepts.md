---
layout: post
title:  深度学习术语集
category: 技术
tags: Deep Learning
keywords:
---

# Early Stopping

所谓early stopping，即在每一个epoch结束时（一个epoch即对所有训练数据的一轮遍历）计算 validation data的accuracy，当accuracy不再提高时，就停止训练。
这是很自然的做法，因为accuracy不再提高了，训练下去也没用。另外，这样做还能防止overfitting。
