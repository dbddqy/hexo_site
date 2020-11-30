---
title: "[Project] [Software] Animation"
date: 2019-04-02 20:05:15
categories:
- project
tags:
- grasshopper
---

# Animation

**(A collaboration with Ruqing Zhong)**

[![](https://img.shields.io/badge/Github-Source%20Code-blue)](https://github.com/dbddqy/Animation) [![](https://img.shields.io/badge/food4rhino-v1.2-lightgrey)](https://www.food4rhino.com/app/animation)

A lightweight Grasshopper plug-in helps designers to make better animations with less effort.

Components:

![](https://github.com/dbddqy/Animation/blob/master/pics/0.jpg?raw=true)

What it can achieve:

- Control viewport. By giving a camera position and a target point, you can easily control the viewport thus moving the camera, or even zoom in zoom out in your video/gif.
- Assign material. Material can be assigned to you objects, so you can have geometries changing color, reflectivity, transparency, etc. in your video/gif.
- Better visualization. This plug-in automatically bakes geometries into rhino environment before saving every frame (and automatically deletes them), so it can achieve all the Rhino visualization effects (proper shading, proper lighting and shadows, clipping planes, etc.) by adjusting your rhino display setting.

3 example files:

1. A growing box, changing color, with the camera moving around.  

   ![](https://github.com/dbddqy/Animation/raw/master/pics/1.gif)

2. Small emerging pieces, with the camera moving around.

   ![](https://github.com/dbddqy/Animation/raw/master/pics/2.gif)

3. Falling balls, changing color, done together with Kangaroo Physics.

   ![](https://github.com/dbddqy/Animation/raw/master/pics/3.gif)
