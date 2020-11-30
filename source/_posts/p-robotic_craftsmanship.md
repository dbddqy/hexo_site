---
title: "[Project] Robotic Craftsmanship"
date: 2020-02-06 09:21:52
categories:
- project
tags:
- ITECH master
---

# Robotic Craftsmanship

**(A collaboration with Yanan Guo and Ruqing Zhong)**

[![](https://img.shields.io/badge/Github-Repo-blue)](https://github.com/dbddqy/machine_perception/tree/master/demo2.2_detect_cylinder)

![](/pics/p-robotic_craftsmanship/result.png)

This is a final project of 2020 behavior fabrication seminar at University of Stuttgart.

Craftman can intuitively handle material without knowing its precise dimensions in advance. However, robots are still in most of the cases blind and repeating the same motion over and over again.

![](/pics/p-robotic_craftsmanship/material_uncertainty.png)

This project explores the posibility of using robotic arm to cut the mortise of bamboo connections. As the exact geometry of the bamboo is unknown, the robot should be equipped with some sensor to perceive the material.

**Sensor:**

- RGBD camera: Realsense D415

**Algorithms used:**

- region growing for segmentation (initial point given by aruco markers)
  (that is a short cut we take, a more proper and general method can be deep neural network based instance segmentaion, e.g., Mask R-CNN)
- ICP (iterative closest point) for aligning mutiple frames
- least squares cylinder fitting for estimating cylinder parameters

**Segmentation:**

![](/pics/p-robotic_craftsmanship/segmentation.gif)

**Robotic milling:**

![](/pics/p-robotic_craftsmanship/milling.gif)

**Result:**

![](/pics/p-robotic_craftsmanship/result.gif)
