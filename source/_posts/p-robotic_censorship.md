---
title: "[Project] Robotic Censorship"
date: 2019-07-21 16:21:53
categories:
- project
tags:
- ITECH master
---

# Robotic Censorship

**(A collaboration with Zhetao Dong, Yanan Guo and Hooman Salyani)**

[![](https://img.shields.io/badge/Github-Repo-blue)](https://github.com/dbddqy/end_effector)

![](https://github.com/dbddqy/end_effector/blob/master/pics/process.gif?raw=true)

This is a final project of 2019 CDDF seminar (computational design and digital fabrication) at University of Stuttgart.

> This project use use robot and object recognition algorithm to apply a block of paint for censorship.

The robot has a stereo camera module equipped on its end-effector for object detection and depth inference, as well as two stepper motors and gear system for applying the paint.

The robot goes to some pre-defined scanning locations and takes the scan. If any human face is found, it goes above that face and paint on it, otherwise it goes to next scan location. If there is little paint left in the syringe, it performs the auto-reload.

**Hardware:**

- Raspberry Pi 3B+
- Stereo camera module
- Stepper Motors
- Gear and rack
- Syringe

**Software:**

- OpenCV (python wrapper)
- Tensorflow (not used in the end)

**Process:**

![](https://github.com/dbddqy/end_effector/blob/master/pics/process.png?raw=true)

**End_effector:**

![](https://github.com/dbddqy/end_effector/blob/master/pics/end_effector.png?raw=true)

**Communication with the KUKA robot:**

![](https://github.com/dbddqy/end_effector/blob/master/pics/communication.png?raw=true)

**Full video:**

<div align="left">
    <iframe src="https://player.vimeo.com/video/443476046" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/443476046">Robotic Sensorship 01</a></p>
</div>

<div align="left">
    <iframe src="https://player.vimeo.com/video/443476348" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    <p><a href="https://vimeo.com/443476348">Robotic Sensorship 02</a></p>
</div>
