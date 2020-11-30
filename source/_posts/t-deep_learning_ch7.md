---
title: "[Theory] [Deep Learning] ch7"
date: 2019-05-22 16:23:45
categories:
- theory
tags:
- deep learning
---

# CNN

## Convolutional Layer

![](https://github.com/dbddqy/Note/raw/master/Deep_Learning/pics/CNN.png)

Filter the data with learnable kernel parameters.

## Modifications

- Padding: p
- Stride: s
- Dilated: d

Output size:
$$
[\frac{M_{L-1}+2p-(K_L-1)d-1}{s}]+1
$$

## Pooling

- max pooling
- average pooling

Reduced spatial dimensions of the feature map. And the operation is translational-invariant.
