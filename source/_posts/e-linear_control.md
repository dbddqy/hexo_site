---
title: "[Exercise] Linear Control"
date: 2020-08-12 19:13:06
categories:
- exercise
tags:
- Intro to Robotics, Mechanics and Control
---

# Linear Control

[![](https://img.shields.io/badge/Github-Source%20Code-blue)](https://github.com/dbddqy/Note/tree/master/Intro_to_Robotics/exercise_linear_control)

## Second-order Linear Systems

The simulation of such system according to book 9.3

```python
class System:
    def __init__(self, x0, v0, m=1., b=2., k=1., control=False):
        self.m = m
        self.b = b
        self.k = k
        self.x = x0
        self.v = v0
        self.control = control
        self.a = (self.f() - self.b*self.v - self.k*self.x) / self.m

    def f(self):
        if self.control:
            kp = 16.
            kv = 2*np.sqrt(kp)
            f_prime = -kp*self.x-kv*self.v
            f = f_prime*self.m + self.b*self.v+self.k*self.x
            return f
        else:
            return 0.

    def update(self, dt=0.1):
        self.v += (self.a * dt)
        self.x += (self.v * dt)
        self.a = (self.f() - self.b*self.v - self.k*self.x) / self.m + np.random.normal(0.0, 0.00)
```

If no active control is applied, and $b^2>4mk$, the response is **overdamped**.

Result (b =4, m = 1.0, k=1.0)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/b=4_no_control.png)

If $b^2=4mk$, the response is **critically damped**.

Result (b =2, m = 1.0, k=1.0)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/b=2_no_control.png)

If $b^2<4mk$, the response is **underdamped**.

Result (b =0.5, m = 1.0, k=1.0)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/b=0.5_no_control.png)

According to book 9.5, apply active control to make the system **critically damped**.

Result (kp=4)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/kp=4_control.png)

Result (kp=16)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/kp=16_control.png)

## Trajectory control

The force function changed to:

```python
def f(self):
    if self.control:
        kp = 16.
        kv = 2*np.sqrt(kp)
        f_prime = kp*(self.goal[0]-self.x)+kv*(self.goal[1]-self.v)+self.goal[2]
        f = f_prime*self.m + self.b*self.v+self.k*self.x
        return f
    else:
        return 0.
```

### Step Function

Trajectory is set as:

- start: x = 2, v = 0, a = 0
-  0~3s: x = 0, v = 0, a = 0
-  3~7s: x = 4, v = 0, a = 0
-  7~10s: x = 2, v = 0, a = 0

Result (kp=4)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/tra_kp=4.png)

Result (kp=16)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/tra_kp=16.png)

So, higher kp, faster the response, "stiffer" the system

### Cubic Polynomial

- start: x = 2, v = 0, a = 0
- trajectory follows polynomial: $y = 0.05(x^3-15x^2+63x)$

Result (kp=16)

![](https://github.com/dbddqy/Note/raw/master/Intro_to_Robotics/exercise_linear_control/cubic_polynomial.png)