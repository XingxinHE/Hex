---
aliases: [characteristic function]
tags:
  - function
  - mathematics
---
# 📝Definition
In mathematics, an indicator function or a characteristic function of a subset of a [[set|set]] is a function that maps elements of the subset to $\textbf{1}$, and all other elements to $\textbf{0}$.

# ✒Notation
The indicator function of a subset $A$ of a set $X$ is a function
$$
\mathbf{1}_A:X\to\{0,1\}
$$
defined as
$$
\mathbf{1}_A(x):=
\begin{cases}
1\quad\text{if }x\in A,\\
0\quad\text{if }x\notin A
\end{cases}
$$
# 🗃Example
The [[Dirichlet Function]] is the indicator function of the rational numbers as a subset of the real numbers.

# 🧀Applicability
[[surface reconstruction]]

# 🌱Related Elements
## 🥭indicator function vs. [[characteristic function]]
Normally, they are super similar.
"indicator function" refers to **0-1** indicator function.
"characteristics function" refers to **0-infinity** indicator function.

## 🍎indicator function vs. [[implicit surface representation|implicit surface functions]] vs. [[signed distance function]]
Compared to typical implicit surface functions, this function represents the surface $\partial \mathbf{S}$ of the shape $\mathbf{S}$ as the ==_discontinuity_== between the $\mathbf{1}$ values and the $\mathbf{0}$ values. Awkwardly, the [[gradient]] of the indicator function ${\nabla}{\chi}_\mathbf{S}$ is _**not defined**_ along $\partial \mathbf{S}$.

> [!info] Info
> The preceding investigation is the key insight of [[📄Poisson Surface Reconstruction]].
