---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
---

# 📝Definition
The column space of matrix $A$ contains all [[linear combination]]s $Ax=x_1a_1+x_2a_2$ of the columns.

# 🧠Intuition
Suppose $A$ is a $3\times3$ matrix. Here are some simple matrices to show ==4== possibilities for the ==column space== $\mathbf{C}(A)$
$$
\begin{matrix}
\begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\mathbf{C}(A)=\mathbb{R}^3=xyz\text{ space}
\end{matrix}
\quad
\begin{matrix}
\begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{bmatrix}\\
\mathbf{C}(A)=xy\text{ plane}
\end{matrix}
\quad
\begin{matrix}
\begin{bmatrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{bmatrix}\\
\mathbf{C}(A)=x\text{ axis}
\end{matrix}
\quad
\begin{matrix}
\begin{bmatrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{bmatrix}\\
\mathbf{C}(A)=\text{one point}(0,0,0)
\end{matrix}
$$

# 🌈Properties
## 🔴rank($A$ + $B$) $\leq$ rank($A$) + rank($B$).
This is the rule.

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
The concept of "column space" highly relates to the other concepts: [[linear independent]], [[linear dependent]], and [[linear combination]].

## 🥑column space vs. linear equation

**📝Description**
The following sentence **connects** column space to [[Linear Equation]].⭐
> [!quote]
> $Ax=b$ has a solution vector $x$ if the vector $b$ is in the column space of $A$.

The key takeaway is the following.
> [!abstract]
> One way to interpret this:
> - Since $Ax$ is a [[Matrix-Vector Products]] operation, and if we see it in the [[Matrix-Vector Products#🏷Categories#🔖Column Picture in Matrix-Vector Multiplication⭐|column picture]], the operation is the sense of ==combination of column space==! Therefore, $b$ is the result of the combination of the columns of $A$. Therefore, $b$ must be in the column space of $A$.
> 
> Another way to interpret this:
> - If $b$ is in the column space of $A$, then $b$ is a combination of the columns of $A$ and the numbers in that combination give a solution $x$ to $Ax = b$.

**🗃Example**
For example,
$$
\begin{bmatrix}1&3\\2&4\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}4\\6\end{bmatrix}
$$
The $\begin{bmatrix}x_1\\x_2\end{bmatrix}$ could be $\begin{bmatrix}1\\1\end{bmatrix},\begin{bmatrix}1\\-1\end{bmatrix},\begin{bmatrix}\frac{1}{2}\\-\frac{1}{2}\end{bmatrix}$. 
Because $\begin{bmatrix}1&3\\2&4\end{bmatrix}\begin{bmatrix}1\\1\end{bmatrix}=1\begin{bmatrix}1\\2\end{bmatrix}+1\begin{bmatrix}3\\4\end{bmatrix}=\begin{bmatrix}4\\6\end{bmatrix}$


# 🍂Unorganized