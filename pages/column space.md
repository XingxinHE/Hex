---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
---

# 📝Definition
The column space of matrix $A$ contains all [[linear combination]]s $Ax=x_1a_1+x_2a_2$ of the columns.
	

# 🗃Example
- 📌Example 1 Independent Columns
	- $$A_1 = \begin{bmatrix}1&0&0\\2&4&0\\3&5&6\end{bmatrix}$$
	- Each column gives a new direction. Their combinations fill 3D space $\mathbb{R}$.
- 📌Example 2 Dependent Columns
	- $$A_2 = \begin{bmatrix}1&2&3\\1&4&5\\6&0&6\end{bmatrix}$$
	- Column1 + Column2 = Column3. Their combinations don't fill 3D space but a plane.
- 📌Example 3 Edge Case
	- $$A_3 = \begin{bmatrix}1&3&4\\2&6&8\\5&15&20\end{bmatrix}$$
	- Every pair of column is dependent. Their combinations is just a line.

# 🌱Related Elements
The concept of "column space" highly relates to the other concepts: [[linear independent]], [[Linear Dependence|linear dependent]], and [[linear combination]].

# 🍂Unorganized