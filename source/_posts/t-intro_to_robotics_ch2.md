---
title: "[Theory] [Intro to Robotics, Mechanics and Control] ch2"
date: 2019-08-18 13:53:34
categories:
- theory
tags:
- Intro to Robotics, Mechanics and Control
- robotics
---

# Spatial Descriptions and Transformations

### Rotation Matrix

$$
{}^A_BR = [ \begin{array}{c} {}^A\hat{X}_B & ^A\hat{Y}_B  & {}^A\hat{Z}_B \end{array}] \\\\
{}^B_AR = {}^A_BR^{-1} = {}^A_BR^T
$$

$^A\hat{X}_B$ is the unit vector along frame B's x direction, described in frame A

### Transformation Matrix
$$
\begin{align} {}^A_BT &= \begin{bmatrix} ^A_BR & {}^AP_{BORG} \\\\ 0^T & 1 \end{bmatrix} \\\\
{}^A_CT &= {}^A_BT {}^B_CT \\\\
^AP &= {}^A_BT ^BP \\\\
^AP &= {}^A_BR ^BP + {}^AP_{BORG}
\end{align}
$$
### Euler Angle

- around axes of fixed reference frame
- around axes of rotated reference frame (itself)
- x-y-z fixed angles equivalent z-y-x euler angle

formula see book (2-64)

### Angle-Axis

Rodrigues' rotation formula, see book (2-80)

### Quaternion

$$
\begin{align}
q_1 = k_xsin(\theta/2) \\\\
q_2 = k_ysin(\theta/2) \\\\
q_3 = k_zsin(\theta/2) \\\\
q_4 = cos(\theta/2) \\\\
\end{align}
$$

### Free Vector

During transformation, apply only the rotation, no translation

