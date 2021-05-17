---
author: Devon Morris
title: Geometry & Manifolds
subtitle: "More rantings from Devon"
date: May 14, 2021
---
# Geometry

## Geometry

> Concerned with properties of space that are related with distance, shape, size, and relative position of figures.

Wikipedia

## Geometry

> Things that don't change with our representation of them

Devon Morris

## Geometry

> Things I can draw

(Dumber) Devon Morris

## Geometry

Deceptively difficult

## Geometry

Incredible intuition, but difficult to express

## Triangle

![](./assets/triangle.png){ width=70% }

## Pythagoras

![](./assets/pythagoras.png){ width=70% }

## Euclid
![](./assets/euclid.jpg){ width=40% }

## Descartes

![](./assets/descartes.jpg){ width=40% }

## Geometry + Algebra = <3

* Don't forget the "+"
* Geometry cannot be replaced by algebra
* Proper algebraic application requires true geometric understanding

# Geometric Linear Algebra

## Vector
![](./assets/vector.png){ width=80% }

## Scaling
![](./assets/scaling.png){ width=60% }

## Addition
![](./assets/addition.png){ width=45% }

## Addition and Scaling
![](./assets/addition_scaling.png){ width=45% }

## Vector Space

* Linear Space
* Vectors can stretch and add

## What is this?

$$
\begin{bmatrix}
1 \\
2 \\
3
\end{bmatrix}
$$

## Euler Angles - Scaling
$$
4
\begin{bmatrix}
0 \\
0 \\
\pi / 2
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
2\pi
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
\implies
\begin{bmatrix}
0 \\
0 \\
\pi / 2
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
$$

## Euler Angles - Addition
$$
\begin{bmatrix}
0 \\
0 \\
\pi / 2
\end{bmatrix}
+
\begin{bmatrix}
0 \\
0 \\
3\pi / 2
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
\implies
\begin{bmatrix}
0 \\
0 \\
\pi / 2
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
-3 \pi / 2
\end{bmatrix}
$$

## Euler Angles - Gimbal Lock
$$
\begin{bmatrix}
0 \\
\pi / 2 \\
\pi / 3
\end{bmatrix}
=
\begin{bmatrix}
\pi / 3 \\
\pi / 2 \\
0
\end{bmatrix}
$$

## Blunder #1

Don't confuse the representation of a thing for the thing itself!

## Length
![](./assets/addition.png){ width=80% }

## Length
$$
||v||
$$

## Angle
![](./assets/addition.png){ width=45% }

## Inner Product
$$
<u,v> = ||u|| * ||v|| \cos{\theta}
$$

## Euler Angles
Infinitestimal Euler Angles

* Pen Demonstration

## Numbers!

## Bases
![](./assets/basis.png){ width=40% }

## Bases
$$
^{\mathcal{A}}v =
\begin{bmatrix}
0.5 \\
1
\end{bmatrix}
$$

## Change of basis
![](./assets/change_basis.png){ width=50% }

## Change of basis
$$
^{\mathcal{B}}v=
\begin{bmatrix}
1 \\
0.5
\end{bmatrix}
$$

## Non-normal bases
![](./assets/non_normal_basis.png){ width=50% }

## Non-normal bases
$$
^{\mathcal{C}}v=
\begin{bmatrix}
0.25 \\
1
\end{bmatrix}
$$

## Non-orthogonal bases
![](./assets/non_orthogonal_basis.png){ width=50% }

## Non-orthogonal bases
$$
^{\mathcal{D}}v=
\begin{bmatrix}
0.33 \\
0.66
\end{bmatrix}
$$

## Inner product is not an algorithm
$$
<^{\mathcal{D}}v, ^{\mathcal{D}}v> =
<^{\mathcal{A}}v, ^{\mathcal{A}}v>
$$

## Inner product is not an algorithm
$$
\begin{bmatrix}
0.33 & 0.66
\end{bmatrix}
\begin{bmatrix}
0.33\\
0.66
\end{bmatrix}
= 0.545 \neq 1.25
=
\begin{bmatrix}
0.5 & 1.0
\end{bmatrix}
\begin{bmatrix}
0.5\\
1.0
\end{bmatrix}
$$

## Inner product is geometric entity

## Inner Product the Right Way
$$
\begin{bmatrix}
0.33 & 0.66
\end{bmatrix}
\begin{bmatrix}
3.25 & 1 \\
1 & 1
\end{bmatrix}
\begin{bmatrix}
0.33\\
0.66
\end{bmatrix} = 1.25
$$

## What is a this?

$$
\begin{bmatrix}
1, 2, 3 \\
4, 5, 6 \\
7, 8, 9
\end{bmatrix}
$$

## Matrix

Algebraic thing

$$
AB = C
$$
$$
D + E = F
$$

## Linear Transformations
![](./assets/linear_transformation.png)

## Linear Transformation
Geometric Entity

## Linear Transformations
$$
Tv = v'
$$

## Linear Transformations
$$
vT = v'
$$

## Change of Basis
$$
^{\mathcal{B}}T_{\mathcal{A}} ^{\mathcal{A}}v = ^{\mathcal{B}}v
$$

## Quadratic Form
$$
v^\top P v = a
$$
Can be used to "represent" an inner product in specific basis

## Isomorphic

Means there exists a transformation that preserves structure.

$$
U \cong V
$$

## Quick Fact

If $V$ is finite dimensional real vector space then

$$
V \cong \mathbb{R}^n
$$

## Multilinear algebra
All of these concepts generalize to tensors in multilinear algebra.

## Multilinear algebra
Tensors are geometric objects. Don't be fooled by deep learning.

## Multilinear algebra
Representations of tensors are not tensors

# Differential Geometry

## Smooth Manifolds

## Think Curvy Space

![](./assets/manifold.png)

## Think Curvy Space

![](./assets/torus.png)

## Charts

![](./assets/charts.png)

Mapping from real numbers to a manifold

## Euler Angles
Euler angles are a chart on $SO(3)$

## Atlas

Charts that cover the entire manifold

## Tangent Space

![](./assets/tangent_space.png)

## Blunder #2
Not all vectors are made equal. Vectors in different tangent spaces cannot be
added!

## Blunder #2
Tangent Vectors have a tail attached at a point on the manifold.

## Retract
![](./assets/retract1.png)

## Retract
![](./assets/retract2.png)

## Local
![](./assets/local.png)

## Exponential & Logarithmic Map
![](./assets/log_exp.png)

## Degrees of freedom
* Representation of manifold (charts)
* Representation of the tangent space (tangent basis)

## Computation on manifolds
* At each point
  * For a selected tangent basis
    * Do linear algebra...
      * Retract to the manifold
        * Repeat

## Gaussians on Manifolds

![](./assets/manifold_gaussian.png)

## General Relativity

# Groups

## Algebraic construct

## Definition

$$
\mathcal{G} = (G,*)
$$

$$
g * h \in G
$$

$$
g * e = e * g = g
$$

$$
g * g^{-1} = e
$$

## Matrices

Invertible matrices form a group $GL_n(\mathbb{R})$

## Matrices

Note: with the strict group definition, we cannot add matrices in
$GL_n(\mathbb{R})$

## Matrices

$$
A I = I A = A
$$
$$
A A^{-1} = I
$$

## Rotation Matrices

$$
R R^{T} = I
$$

## Rotation Matrices
$SO(3)$
