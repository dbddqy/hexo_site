---
title: "[Theory] [Probabilistic Robotics] ch2"
date: 2020-07-23 00:55:22
categories:
- theory
tags:
- probabilistic robotics
- robotics
---

# Recursive State Estimation

## Conditional Independence

*x* and *y* are independent under the condition *z*:
$$
p(x,y|z) = p(x|z)p(y|z) \tag{2.17}
$$

which is equivalent to:
$$
\begin{cases} 
     p(x|z) = p(x|z,y)  
\\\\ p(y|z) = p(y|z,x) \tag{2.18-19}
\end{cases}
$$
**Proof**:

WLOG, insert (2.18) into (2.17) right side, get
$$
p(x|z,y)p(y|z) = \frac{p(x|z,y)p(y,z)}{p(z)} = \frac{p(x,y,z)}{p(z)} = p(x,y|z)
$$
however x and y are not necessarily independent, see book (2.20-21)

## Probabilistic Generative Laws

**Robot States**: x<sub>0</sub>, x<sub>1</sub>, ... , x<sub>t</sub>

**Environment Measurement**: z<sub>1</sub>, ... , z<sub>t</sub>

**Control data**: u<sub>1</sub>, ... , u<sub>t</sub>

(assume take action u first, than take measurement z)

If x is **complete**, then x<sub>t</sub> only depends on x<sub>t-1</sub> and u<sub>t</sub>:
$$
p(x_t|x_{0:t-1},z_{1:t-1},u_{1:t}) = p(x_t|x_{t-1}, u_t) \tag{2.31}
$$
and z<sub>t</sub> depends only on x<sub>t</sub>:
$$
p(z_t|x_{0:t},z_{1:t-1},u_{1:t}) = p(z_t|x_t) \tag{2.32}
$$
(2.31) is called **state transition probability** and (2.32) is called **measurement probability**. They together form the **Hidden Markov Model**.

![](https://github.com/dbddqy/Note/blob/master/Probabilistic_Robotics/pics/HMM.png?raw=true)

## Belief Distributions

**Belief**: with all the measurements and control data, the distribution of state *x*, where the robot believes it is.

Before measurement:
$$
\overline{bel}(x_t) = p(x_t | z_{1:t-1}, u_{1:t}) \tag{2.34}
$$
After measurement:
$$
bel(x_t) = p(x_t | z_{1:t}, u_{1:t}) \tag{2.33}
$$

## Bayes Filters

**Prediction**:
$$
\overline{bel}(x_i) = \int{p(x_t | u_t, x_{t-1})bel(x_{t-1})}dx_{t-1}
$$
**Correction** (measurement update): 
$$
bel(x_i) = \eta{p(z_t | x_t)\overline{bel}(x_t)}
$$

### Bayes Filter Derivation

![](https://github.com/dbddqy/Note/raw/master/Probabilistic_Robotics/pics/bayes_filter_0.jpg)