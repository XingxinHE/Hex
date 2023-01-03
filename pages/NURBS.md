---
aliases: [NURBS Curves, NURBS Curve, NURBS Surfaces, NURBS Surface, tensor-product spline surfaces]
tags:
  - unknown
---

# NURBS
NURBS is short for **N**on**U**niform **R**ational **B**-**S**pline.

# NURBS Curves
## 📝Definition
A $p$th-degree NURBS curve is defined by
$$
\begin{align}
C(u)=
\frac{\sum_{i=0}^{n}N_{i,p}(u)w_i\textbf{P}_i}
{\sum_{i=0}^{n}N_{i,p}(u)w_i}\quad\quad a\leq u\leq b
\end{align}
$$
where the following
- $\textbf{P}_i$ - control points (forming a control polygon)
- $w_i$ - weights
- $N_{i,p}(u)$ - $p$th degree [[B-Spline]] basis functions defined on the nonperiodic (and nonuniform) knot vector

## 🌱Related Elements
The closest pattern to current one, what are their differences?





# NURBS Surfaces
## 📝Definition
A NURBS surface of degree $p$ in the $u$ direction and degree $q$ in the $v$ direction is a bivariate vector-valued piecewise [[rational function]] of the form
$$
\begin{align}
S(u,v)=
\frac{\sum_{i=0}^{n}\sum_{j=0}^{m}N_{i,p}(u)N_{j,q}(v)w_{i,j}\textbf{P}_{ij}}
{\sum_{i=0}^{n}\sum_{j=0}^{m}N_{i,p}(u)N_{j,q}(v)w_{i,j}}\quad\quad 0\leq u,v\leq 1
\end{align}
$$
where
- $\textbf{P}_{ij}$ - form a bidirectional control net
- $w_{ij}$ - weights
- $N_{i,p}(u)$ - the nonrational [[B-Spline]] basis functions defined on the knot vectors $U$
	- $$U=\{\underbrace{0,...,0}_{p+1},u_{p+1},...,u_{r-p-1},\underbrace{1,...,1}_{p+1}\}$$
	- $r = n + p + 1$
- $N_{j,q}(v)$ - the nonrational [[B-Spline]] basis functions defined on the knot vectors $V$
	-  $$V=\{\underbrace{0,...,0}_{q+1},v_{q+1},...,v_{s-q-1},\underbrace{1,...,1}_{q+1}\}$$
	- $s = m + q + 1$


Suppose introducing the piecewise rational basis functions
$$
\begin{align}
R_{i,j}(u,v)=
\frac{N_{i,p}(u)N_{j,q}(v)w_{i,j}}
{\sum_{k=0}^{n}\sum_{l=0}^{m}N_{k,p}(u)N_{l,q}(v)w_{k,l}}\quad\quad 0\leq u,v\leq 1
\end{align}
$$
Then the definition can be writtern as
$$
S(u,v)=\sum_{i=0}^{n}\sum_{j=0}^{m}R_{i,j}(u,v)\textbf{P}_{i,j}
$$
