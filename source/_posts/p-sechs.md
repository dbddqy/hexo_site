---
title: "[Project] Sechs (ongoing)"
date: 2019-10-01 13:15:26
categories:
- project
tags:
- robotics
- ongoing
---

# Sechs

**(A collaboration with An Mo)**

[![](https://img.shields.io/badge/Github-Repo-blue)](https://github.com/moanan/sechs)

![](/pics/p-sechs/A1-A5_20200706.jpg)

**Towards a high performance force-aware 6-axis robot!**

![](/pics/p-sechs/force_feedback.gif)

---

## Design Requirements

- 6 axis
- High performance
  - Joint acceleration: 2π [rad/s] (except J1: 1π [rad/s])
  - Tool payload: 2 [kg]
- Robot teaching by hand (force-aware)
- Desktop size
- 3d printing for most parts

---

## DH Parameters

The parameters listed here are not final.

| Axis | d       | theta     | a    | alpha     |
| :--- | :------ | :-------- | :--- | :-------- |
| 1    | 0.112   | 0.0       | 0.0  | 0.0       |
| 2    | 0.0     | -0.5 * pi | 0.0  | -0.5 * pi |
| 3    | -0.0525 | 0.5 * pi  | 0.2  | 0.0       |
| 4    | 0.2     | 0.0       | 0.0  | 0.5 * pi  |
| 5    | 0.085   | 0.0       | 0.0  | -0.5 * pi |
| 6    | 0.08    | 0.0       | 0.0  | 0.5 * pi  |

---

## Load Estimation

The python-based [Dynamic Model](https://github.com/moanan/sechs/tree/master/1-calculation/torqueLoadCase) is built for estimating required torque for each joint.

| Axis | Required Torque[Nm] | Motor                 | Motor Torque[Nm] | Reduction  | Output Torque[Nm] | Safety Factor |
| :--- | :------------------ | :-------------------- | :--------------- | :--------- | :---------------- | :------------ |
| 1    | 3.4                 | Sunnysky X4110S 170kv | ~2               | 4:1 (belt) | 8                 | 2.3           |
| 2    | 28.8                | SK3 - 4250-350kv      | 1.18             | 30:1       | 35.4              | 1.2           |
| 3    | 11.7                | SK3 - 4250-350kv      | 1.18             | 15:1       | 17.7              | 1.5           |
| 4    | 2.6                 | T-Motor AS 2820 880kv | 0.3              | 19.2:1     | 5.76              | 2.2           |
| 5    | 3.9                 | T-Motor AS 2820 880kv | 0.3              | 19.2:1     | 5.76              | 1.5           |
| 6    | N/A                 | T-Motor AS 2820 880kv | 0.3              | 19.2:1     | 5.76              | N/A           |

---

## Mechanical Design 20200706

![](/pics/p-sechs/mechanical_design_20200706.png)

---

## Testing 20200812

<div align="left">
    <iframe src="https://player.vimeo.com/video/447085333" width="640" height="320" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/447085333">Testing Force FeedBack</a></p>
</div>

## Testing 20200716

<div align="left">
    <iframe src="https://player.vimeo.com/video/443796757" width="320" height="640" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/443796757">Testing Jogging</a></p>
</div>

<div align="left">
    <iframe src="https://player.vimeo.com/video/443797208" width="320" height="640" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/443797208">Testing Teaching</a></p>
</div>

<div align="left">
    <iframe src="https://player.vimeo.com/video/443797861" width="320" height="640" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/443797861">Testing Offline Planning</a></p>
</div>
