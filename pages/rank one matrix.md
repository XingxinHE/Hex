---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
  - matrix
---

# 📝Definition
[[#^30a632e9e0e39867|Rank]] one matrix is matrix that all columns of $A$ and all [[linear combination]]s $Ax$ lie on one line.

# 🧠Intuition
A rank one matrix$A$ can be decomposed into column vector $C$ and row vector $R$.
$$
\begin{align}
\begin{bmatrix} 1&2&10&100\\ 3&6&30&300\\2&4&20&200 \end{bmatrix}
&=
\begin{bmatrix}1\\3\\2\end{bmatrix}\begin{bmatrix}1&2&10&100\end{bmatrix}
\\
A&=CR
\end{align}
$$
> [!note]
> If we read from right to left, that is exactly [[outer product]].
> 

# ⛈Characteristics
## ☁column space and row space
The column space and row space of rank one matrix is a line.
The matrix $A$ 
$$
A=\begin{bmatrix} 1&2&10&100\\ 3&6&30&300\\2&4&20&200 \end{bmatrix}
=
\begin{bmatrix}1\\3\\2\end{bmatrix}\begin{bmatrix}1&2&10&100\end{bmatrix}
$$
- The column space of $A$ is just a vector. $\begin{bmatrix}1\\3\\2\end{bmatrix}$
	- we can verify this by multiplying a constant on the 1st column to get others.
- The row space of $A$ is just a vector as well.$\begin{bmatrix}1&2&10&100\end{bmatrix}$
	- we can verify this by multiplying a constant on the 1st row to get others.
🌧
🌨
🌩
⛅
🌤
🌪
🌥
🌦

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🌱Related Elements
🍉


# 🍂Unorganized