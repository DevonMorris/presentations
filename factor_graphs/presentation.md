---
author: Devon Morris
title: Factor Graphs
subtitle: "What does Devon Keep Ranting About?"
date: April 30, 2021
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
