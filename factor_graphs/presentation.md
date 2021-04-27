---
author: Devon Morris
title: Factor Graphs
subtitle: "What does Devon Keep Ranting About?"
date: April 30, 2021
header-includes:
    - \newcommand{\argmin}{\mathop{\mathrm{argmin}}\limits}
    - \newcommand{\argmax}{\mathop{\mathrm{argmax}}\limits}
---
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

## Factor Graph
![](./assets/factor_observed.png){ width=70% }

Notation for observed

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
&-\frac{1}{2}(x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x) \\
=& \argmax_x -\frac{1}{2}(x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x) \\
=& \argmin_x (x - \mu_x)^\top (\Sigma_x)^{-1} (x - \mu_x) \\
\end{aligned}
$$

# Gaussian MAP Estimation
