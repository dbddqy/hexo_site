---
title: "[Project] Move-X (ongoing)"
date: 2019-07-29 09:32:48
categories:
- project
tags:
- robotics
---

# Move-X

[![](https://img.shields.io/badge/Github-Repo-blue)](https://github.com/dbddqy/mobile_robot)

![](https://github.com/dbddqy/mobile_robot/raw/master/pics/move_x.jpg)

**By building a omni-directional robot platform, this project is mainly for me to learn mechanics and control, as well as robot state estimation and sensor fusion for autonomous vehicles.**

## Low Level:

Mecanum wheels locomotion strategy. Using DJI Robomaster hardware.

- mechanical design
- mecanum wheel kinematics
- motor control: closed-loop velocity control
- publish wheel odometry and IMU data through serial communication

## High Level:

Laser-based SLAM and Navigation.

- implement slam-gmapping
- implement navigation related ros packages
- develop own solution for slam and sensor fusion
  (combining the theoretical study of *Probabilistic Robotics* and *State Estimation for Robotics*)

## Testing Chassis

![](https://github.com/dbddqy/mobile_robot/raw/master/pics/test_chassis.gif)

## Testing odometry

![](https://github.com/dbddqy/mobile_robot/raw/master/pics/test_odom.gif)

## Testing slam-gmapping

![](https://github.com/dbddqy/mobile_robot/raw/master/pics/test_gmapping.gif)
