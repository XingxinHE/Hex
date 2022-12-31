---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
---


# 📝Definition
The transpose of an $m\times n$ matrix $A$ is denoted $A^T$ , and defined by
$$
(A^T)_{ij} = A_{ji}, i = 1,...,n\quad j = 1,...,m
$$


# 🧠Intuition
The transpose of a matrix is an operator which **flips** a matrix over its diagonal.

# 🌈Properties
https://en.wikipedia.org/wiki/Transpose
Let $A$ and $B$ be matrices and $c$ be a scalar.

## 🔴${\displaystyle \left(\mathbf {A} ^{\operatorname{T} }\right)^{\operatorname {T} }=\mathbf {A} .}$
The operation of taking the transpose is an involution (self-inverse).

## 🟠${\displaystyle \left(\mathbf {A} +\mathbf {B} \right)^{\operatorname {T} }=\mathbf {A} ^{\operatorname {T} }+\mathbf {B} ^{\operatorname {T} }.}$
The transpose respects addition.
> [!note]
> Note that the order of the factors reverses.

From this one can deduce that a square matrix $A$ is invertible if and only if $A^T$ is invertible, and in this case we have $(A^{−1})^T = (A^T)^{−1}$. By induction, this result extends to the general case of multiple matrices, where we find that $(A_1 A_2\dots A_{k−1} A_k)^T = A_k^T A_{k−1}^T\dots A_2^T A_1^T$.


## 🟡${\displaystyle \left(\mathbf {AB} \right)^{\operatorname {T} }=\mathbf {B} ^{\operatorname {T} }\mathbf {A} ^{\operatorname {T} }.}$


🟢
🔵
🟣





# 🗃Example
**📁transpose example 1**
$$
\begin{bmatrix}
0 & 4 \\
7 & 0 \\
3 & 1 
\end{bmatrix}^T=\begin{bmatrix}
0 & 7 & 3 \\
4 & 0 & 1 
\end{bmatrix}
$$

**📩transpose example 2**
Suppose a matrix $M$.
$$
M_{ij} = \begin{bmatrix}
F_{11}&F_{12}&F_{13}&F_{14}\\
F_{21}&F_{22}&F_{23}&F_{24}\\
F_{31}&F_{32}&F_{33}&F_{34}\\
\end{bmatrix}
$$
Then the transpose is
$$
M_{ij}^T = 
\begin{bmatrix}
F_{11}&F_{21}&F_{31}\\
F_{12}&F_{22}&F_{32}\\
F_{13}&F_{23}&F_{33}\\
F_{14}&F_{24}&F_{34}\\
\end{bmatrix}
$$

🗂
📨
📂


# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized

