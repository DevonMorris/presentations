---
author: Devon Morris
title: Factor Graphs
subtitle: "What does Devon Keep Ranting About?"
date: April 30, 2021
header-includes:
    - \newcommand{\argmin}{\mathop{\mathrm{argmin}}\limits}
    - \newcommand{\argmax}{\mathop{\mathrm{argmax}}\limits}
---
# This is Dense

## I'm Sorry

## Interrupt Me Please

## Ask Questions

# Factors

## Factorization

## 7th Grade
$x^2 - 1 = (x+1)(x-1)$

## Another Formulation
$$
\begin{aligned}
&f(x) = x^2 - 1 \\
&f(x) = (x+1)(x-1)
\end{aligned}
$$

## Why did your teacher torture you?
$$
\begin{aligned}
&f(x) = 0 \\
&(x+1)(x-1) = 0
\end{aligned}
$$

## Multiple Variables
$$
\begin{aligned}
g(x,y) &= xy - x + y - 1 \\
g(x,y) &= (x + 1)(y - 1)
\end{aligned}
$$

## General
$$
\begin{aligned}
&g(x_1, \dots, x_n) = \prod_{j = 1}^{m} f_j(S_j) \\
&S_j \subseteq \left\{x_1, \dots, x_n\right\}
\end{aligned}
$$

# Graphs

## Graph
$$
\begin{aligned}
&G = (V,E) \\
&E \subseteq V \times V
\end{aligned}
$$
![](./assets/example_graph.png){ width=70% }


## Bipartite Graph
$$
\begin{aligned}
&G = (U,V,E) \\
&E \subseteq U \times V
\end{aligned}
$$
![](./assets/bipartite.png){ width=70% }

# Factor Graphs

## Definition
"A factor graph is a **bipartite graph** representing the **factorization** of
a function"

## Definition
$$
X = \left\{x_1, \dots, x_n\right\}
$$

## Definition
$$
F = \left\{f_1, \dots, f_m\right\}
$$

## Factor Graph
$$
\begin{aligned}
&G = (X,F,E) \\
&E \subseteq U \times V
\end{aligned}
$$
![](./assets/factor_example.png){ width=70% }

## Factor Graph
$$
g(x_1, x_2, x_3) = f_1(x_1,x_2)f_2(x_1,x_2,x_3)f_3(x_3)
$$
![](./assets/factor_example.png){ width=70% }

# Bayesian Estimation

## Bayesian Inference
$$
p(x|z) = \frac{1}{\eta} p(z|x)p(x)
$$

Factors!!!

## Factor Graph
$$
p(x|z) = \frac{1}{\eta} p(z|x)p(x)
$$
![](./assets/bayesian_inference.png){ width=60% }

## MAP Estimate
$$
\hat{x}^{MAP} = \argmax_x p(x|z)
$$

## MAP Estimate
$$
\begin{aligned}
\hat{x}^{MAP} &= \argmax_x p(x|z) \\
&= \argmax_x \frac{1}{\eta} p(z|x)p(x) \\
&= \argmax_x p(z|x)p(x)
\end{aligned}
$$

## MAP Estimate
$$
\begin{aligned}
\hat{x}^{MAP} &= \argmax_x p(z|x)p(x) \\
&= \argmax_x \ln{p(z|x)} + \ln{p(x)}
\end{aligned}
$$

## Marginalization
$$
\begin{aligned}
p(x,y) = \int_{Z} p(x,y,z) dz
\end{aligned}
$$

## Marginalization
![](./assets/marginalization.png){ width=90% }

## Marginalization
Geometrically, marginalization is orthogonal projection

![](./assets/marginalization_projection.png){ width=80% }

## Marginalization
The parts we don't have time to cover

* Sum-Product Algorithm - Belief Propagation
* Bayes Trees - Data Structure To Help Marginalization & Sparsity
* Schur Complement - Gaussian Case

# Multivariate Normal

## Random Variable
$$
x \sim \mathcal{N}(\mu_x, \Sigma_x)
$$

## Probability Density
$$
p(x) = \frac{1}{\sqrt{(2\pi)^k \left|\Sigma_x\right|}} \exp\left\{-\frac{1}{2}(x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x)\right\}
$$

## Log Probability Density
$$
\ln p(x) = -\frac{1}{2}\ln\left\{(2\pi)^k \left|\Sigma_x\right|\right\} -\frac{1}{2}(x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x)
$$

## Argmax
$$
\begin{aligned}
\argmax_x \ln p(x) =& \argmax_x -\frac{1}{2}\ln\left\{(2\pi)^k \left|\Sigma_x\right|\right\} \\
&-\frac{1}{2}(x - \mu_x)^\top \Sigma_x^{-1} (x - \mu_x) \\
=& \argmax_x -\frac{1}{2}(x - \mu_x)^\top \Sigma_x^{-1} (x - \mu_x) \\
=& \argmin_x (x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x) \\
\end{aligned}
$$

# Gaussian MAP Estimation

## Recall MAP
$$
\hat{x}^{MAP} = \argmax_x p(x|z)
$$

## Gaussian Prior & Likelihood
$$
\begin{aligned}
x &\sim \mathcal{N}(\mu_x, \Sigma_x) \\
z|x &\sim \mathcal{N}(C\mu_x, R)
\end{aligned}
$$

## MAP Estimate
$$
\begin{aligned}
\hat{x}^{MAP} =& \argmin_x (x - \mu_x)^\top \Sigma_x^{-1} (x - \mu_x) \\
&+ (z - C\mu_x)^\top R^{-1} (z - C\mu_x)
\end{aligned}
$$

# Kalman

## Linear Transition & Measurement
$$
\begin{aligned}
x_k &= Ax_{k-1} + Bu_k + \epsilon_k \\
z_k &= Cx_k + \nu_k \\
\epsilon_k &\sim \mathcal{N}(0, Q_k) \\
\nu_k &\sim \mathcal{N}(0, R_k) \\
\end{aligned}
$$

## Quick Note
By the definition of conditional probability
$$
\begin{aligned}
p(x_k, x_{k-1}) = p(x_k|x_{k-1})p(x_{k-1})
\end{aligned}
$$

## Kalman Prediction
![](./assets/kalman_predict.png){ width=70% }

This is dumb because we have closed form solutions

## Kalman Prediction - Closed Form
$$
\begin{aligned}
x_{k-1} &\sim \mathcal{N}(\hat{x}_{k-1}, \Sigma_k) \\
x_{k}|x_{k-1} &\sim \mathcal{N}(Ax_{k-1} + Bu_k, Q_k) \\
&\downarrow \\
x_k &\sim \mathcal{N}(A\hat{x}_{k-1} + Bu_k, A \Sigma_k A^\top + Q_k)
\end{aligned}
$$

## Kalman Update
![](./assets/kalman_update.png){ width=80% }

This is dumb because we have closed form solutions

## Kalman Update - Closed Form
$$
\begin{aligned}
x_{k} &\sim \mathcal{N}(\hat{x}_{k|k-1}, \Sigma_{k|k-1}) \\
z_{k}|x_{k} &\sim \mathcal{N}(Cx_{k}, R_k) \\
&\downarrow \\
x_k &\sim \mathcal{N}(\hat{x}_{k|k-1} - K(z_k - C\hat{x}_{k|k-1}), (I - KC)\Sigma_{k|k-1})
\end{aligned}
$$

## One Step Kalman Smoother
![](./assets/kalman_smoother_one.png){ width=80% }

This is not dumb, because the closed form solution is much messier

## Example
[gtsam](https://gtsam.org/)

## Fixed Lag Kalman Smoother
![](./assets/kalman_smoother_fix.png){ width=80% }

This is **very** not dumb, because the closed form solution is much messier

## OOSM
![](./assets/oosm.png){ width=80% }

This is **very** **very** not dumb, no backward prediction required.

# Next Time

## Lie Theory

## Factor Graphs on Manifolds

## Calibration!

## ISAM
