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

那么，怎么样才算是validation accuracy不再提高呢？并不是说validation accuracy一降下来，它就是“不再提高”，因为可能经过这个epoch后，accuracy降低了，但是随后的epoch又让accuracy升上去了，所以不能根据一两次的连续降低就判断“不再提高”。正确的做法是，在训练的过程中，记录最佳的validation accuracy，当连续10次epoch（或者更多次）没达到最佳accuracy时，你可以认为“不再提高”，此时使用early stopping。这个策略就叫“ no-improvement-in-n”，n即epoch的次数，可以根据实际情况取10、20、30….
