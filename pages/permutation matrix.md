---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
  - matrix
---

# 📋Prerequisite
Every row and column contains precisely a single $1$ with $0$s everywhere else, and every [[permutation]] corresponds to a unique permutation matrix. 

# 📝Definition
A permutation matrix is a [[matrix]] obtained by permuting the rows and columns of an $n\times n$ [[identity matrix]] according to some permutation of the numbers $1$ to $n$.

A permutation matrix $A$ satisfies
$$
AA^\operatorname{T}=I
$$
where:
- $A^\operatorname{T}$ is the [[transpose]].
- $I$ is the [[identity matrix]].

# 🧠Intuition
Find an intuitive way of understanding this concept.

# ⛈Characteristics
## 🌦the order of matrix product matters
Suppose $A^p$ is a permutation matrix and $M$ is a matrix as operand.
___
$\textcolor{red}{A^P} M$
**📝Description**
It exchanges the row.

**🗃Example**
$$
\textcolor{red}{\begin{bmatrix}0&1\\1&0\end{bmatrix}}\begin{bmatrix}a&b\\c&d\end{bmatrix}=\begin{bmatrix}c&d\\a&b\end{bmatrix}
$$

> [!info] Remark
> It can be understood by [[matrix multiplication#🧾 Cheat Sheet#📜M-M 3]]. 
> Where $\textcolor{red}{\begin{bmatrix}0&1\\1&0\end{bmatrix}}$ acts as a selector on rows to build.

___
$M\textcolor{blue}{A^p}$
**📝Description**
It exchanges the column.

**🗃Example**
$$
\begin{align}
\begin{bmatrix}a&b\\c&d\end{bmatrix}\textcolor{blue}{\begin{bmatrix}0&1\\1&0\end{bmatrix}}=\begin{bmatrix}b&a\\d&c\end{bmatrix}
\end{align}
$$

> [!info] Remark
> It can be understood by [[matrix multiplication#🧾 Cheat Sheet#📜M-M 2]]. 
> Where $\textcolor{blue}{\begin{bmatrix}0&1\\1&0\end{bmatrix}}$ acts as a selector on columns to build.



# 🌈Properties
## 🔴Determinant
The [[Determinant]] of a permutation matrix is always $\pm1$.

## 🟠Amount of permutation matrix
There are $n!$ permutation matrices of size $n$, where $n!$ is a [[factorial]].


🟡
🟢
🔵
🟣

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized