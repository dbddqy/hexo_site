---
title: "[Project] [Software] Visual Kinematics"
date: 2020-07-17 14:46:27
categories:
- project
tags:
- robotics
---

# Visual Kinematics

[![](https://img.shields.io/badge/Github-Source%20Code-blue)](https://github.com/dbddqy/visual_kinematics) [![](https://img.shields.io/badge/PyPI-0.0.7-orange)](https://pypi.org/project/visual-kinematics/)

This project concentrates on an python-based robotics toolbox for **kinematics calculation**, **robot pose visualization** and **robot path planning**.

## Requirements

- easy to use, only need DH parameters as input (so numerical inverse required).
- support both classic and modified DH parameters
- support robot with different degrees of freedom
- support different representations for rotaion (euler angles, angle axis, quaternion, etc.)
- support high performance analytical inverse (has to be user defined)
- visualizing robot pose and trajectory (a slider for simulating the trajectory)
- support path interpolation in joint space and cartesian space (p2p and linear) 

## Some Results

**Trajectory:**

![](https://github.com/dbddqy/visual_kinematics/raw/master/pics/trajectory.gif?raw=true)

**Linear motion with analytical inverse:**

![](https://github.com/dbddqy/visual_kinematics/raw/master/pics/analytical_inv.gif?raw=true)

**7-axis:**

![](https://github.com/dbddqy/visual_kinematics/raw/master/pics/7-axis.gif?raw=true)
