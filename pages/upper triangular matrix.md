---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
  - matrix
---

# 🚿Source
Every [[square matrix]] $A$ with [[linear independent|independent]] columns ([[full rank]]) can be reduced to a triangular matrix $U$ with nonzero pivots.

# 📝Definition
https://mathworld.wolfram.com/UpperTriangularMatrix.html

# 🧠Intuition
The matrix has all zero below its diagonal.

# ✒Notation
$$
\begin{align}
U
\end{align}
$$

# 🚀Benefit / Pros
The followings are the pros of upper triangular matrix.

## 🛰️easy to solve system of linear equations
**📝Description**
A [[system of linear equations]] typically writes as
$$
Ax=b.
$$

The elimination makes it changed to
$$
Ux=c
$$
where
- $U$ - the upper triangular matrix
- $x$ - the unknown to solve.

It makes easy to solve.
___
**🗃Example**
$$
\begin{align}
Ux&=c\\
\begin{bmatrix}
2&3&4\\
0&5&6\\
0&0&7
\end{bmatrix}
\begin{bmatrix}
x_1\\x_2\\x_3
\end{bmatrix}
&=
\begin{bmatrix}
19\\17\\14
\end{bmatrix}
\end{align}
\tag{1}
$$
Since the "pivot" 2,5,7 on the main diagonal are not zero. We can solve it easily. I would like to see it in [[Matrix-Vector Products#🏷Categories#🔖Column Picture in Matrix-Vector Multiplication⭐]].
$$
x_1
\begin{bmatrix}
2\\0\\0
\end{bmatrix}
+
x_2
\begin{bmatrix}
3\\5\\0
\end{bmatrix}
+
x_3
\begin{bmatrix}
4\\6\\7
\end{bmatrix}
=
\begin{bmatrix}
19\\17\\14
\end{bmatrix}
\tag{2}
$$
See it in bottom to top in the $\text{(1)}$ equation and see it in right to left in the $\text{(2)}$ equation. We got.
- $7x_3=14$ gives $x_3=2$
- $5x_2+6x_3=17$ gives $5x_2+6(2)=17$ gives $x_2=1$
- $2x_1+3(1)+4(2)=19$ gives $x_1=4$
- Therefore $\begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}=\begin{bmatrix}4\\1\\2\end{bmatrix}$

> [!tip]
> If we write the $U$ in linear equation format, then you would understand the benefit right away!
> $$\begin{align}2x_1+3x_2+4x_1&=19\\5x_2+6x_3&=17\\7x_3&=14\end{align}$$
> Solving from bottom to top is also known as "back substitution".



🛸
✈️



# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized