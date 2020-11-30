---
title: "[Exercise] Kalman Filter"
date: 2020-08-06 19:15:02
categories:
- exercise
tags:
- probabilistic robotics
---

# Kalman Filter

[![](https://img.shields.io/badge/Github-Source%20Code-blue)](https://github.com/dbddqy/Note/blob/master/Probabilistic_Robotics/exercise_kf/kf.py)

Ground truth: y = 1.0, generate noisy data.

```python
def generate_data(num=100):
    x0 = np.arange(0., 1., 1./num)
    y_true = np.ones([num, ])
    y0 = y_true + np.random.normal(0., 0.1, num)
    return x0, y0, y_true
```

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/exercise_kf/pics/data.png)

Assume we have the prediction model y = x (which means the signal is constant), and observation model is also set to y = x

```python
F = 1.
H = 1.
```

Set variance and initial value:

```python
# prediction variance: Q, observation variance: R
Q = 0.1
R = 0.01
# initial value
mu_0 = 1.
sigma_0 = 1.  # very uncertain about the initial value
```

Applying the filter:

```python
for i in range(NUM):
    # update prediction
    mu_minus = F * mu_plus
    sigma_minus = F * F * sigma_plus + Q
    # update observation
    k = (H * sigma_minus) / (H * H * sigma_minus + R)
    mu_plus = mu_minus + k * (y0[i] - H * mu_minus)
    sigma_plus = (1. - k * H) * sigma_minus
    # append data
    mu_filtered.append(mu_plus)
    sigma_filtered.append(sigma_plus)
```

Here we tend to believe our observation, so the result:

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/exercise_kf/pics/result_00.png)

If we tend to believe our model,

```python
# prediction variance: Q, observation variance: R
Q = 0.0001
R = 0.1
```

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/exercise_kf/pics/result_01.png)

KF is not sensitive to the initial value, we can set it very wrong.

```python
# initial value
mu_0 = 10.
sigma_0 = 1.
```

And it will be corrected very soon.

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/exercise_kf/pics/result_02.png)

Finally, if the actual model is a bit more complicated, and our prediction model doesn't match it at all:

```python
# truth y = x ** 2
def generate_data(num=100):
    x0 = np.arange(0., 1., 1./num)
    y_true = x0 * x0
    y0 = y_true + np.random.normal(0., 0.1, num)
    return x0, y0, y_true
```

KF can still improve the result a bit. 

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/exercise_kf/pics/result_03.png)