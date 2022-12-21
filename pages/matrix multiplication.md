---
aliases: [matrix product]
tags:
  - LinearAlgebra
  - mathematics
---
# 📋Prerequisite
If there are matrices $F$($n\times m_1$) and $G(m_2\times p)$, **the prerequisite for a valid matrix multiplication is** that $m_1=m_2$. 

# 📝Definition
**📄Definition - row way**
Suppose there 2 matrices $F$($n\times m_1$) and $G(m_2\times p)$, the product is a matrix with shape $n\times p$. The $i,j$ element of the matrix is:
$$
(FG)_{ij} = \sum_{k=1}^{m}F_{ik}G_{kj}
$$
The `2,2` element of output matrix is the dot product of $2$-th row of $F$ and $2$-th colomn of $G$
$$
M_{22}=\begin{bmatrix}3&0&1\end{bmatrix}\begin{bmatrix}2\\0\\2\end{bmatrix}
$$
> [!note]
> The reason why I refer this as "row way" is that, this way of thinking is good for computation. Same analogy of the [[Matrix-Vector Products#🏷Categories#🔖Rows Picture in Matrix-Vector Multiplication|row picture in Matrix-Vector Products]].

___
**📑Definition - column way**
Suppose there are 2 matrices $A$ and $B$, we see the composition of $B$ as the follow
$$\begin{bmatrix}
| & |& |\\
\mathbf{x} & \mathbf{y}& \mathbf{z}\\
| & |& |\\
\end{bmatrix}.$$
Then the multiplication of matrix $A$ and $B$ can be see it as followed.
$$
AB=A
\begin{bmatrix}
| & |& |\\
\mathbf{x} & \mathbf{y}& \mathbf{z}\\
| & |& |\\
\end{bmatrix}
=
\begin{bmatrix}
Ax&Ay&Az
\end{bmatrix}
$$
> [!tip]
> The columns of the result is each column of $B$ goes over the [[Matrix-Vector Products]] with matrix $A$.


# 🧠Intuition
Columns of $AB$ are combinations of columns of $A$.
> [!question]
> #TODO Exaplain why every vector in $C(AB)$ -a.k.a. every combination of the columns of $AB$- is also in the [[column space]] of $A$.


# 🌈Properties
## 🔴Associativity
**📝Definition**
$$
(AB)C=A(BC)
$$
**🧠Intuition**
The order $ABC$ of those matrices must stay the same while we can multiply $AB$ first or multiply $BC$ first.

> [!important]
> Many many proofs in linear algebra depend on this simple fact.

## 🟠Non-commutativity
**📝Definition**
$$
AB\neq BA
$$
**🗃Example**
Let $\displaystyle{{\rm A} = \begin{pmatrix}1 &1 &1\\1 &2 &3\\1 &3 &4\end{pmatrix}}$ and $\displaystyle{{\rm B} = \begin{pmatrix}2 &0 &0\\0 &3 &0\\0 &0 &4\end{pmatrix}}$. Compute ${\rm A B}$ and ${\rm B A}$.
$$
\begin{align}
AB&=\begin{pmatrix}
2 & 3 &  4\\
2 & 6 & 12\\
2 & 9 &16\end{pmatrix}
\\
BA&=\begin{pmatrix}
2 &  2  & 2\\
3 &  6  &9\\
4 & 12 &16\\
\end{pmatrix}
\end{align}
$$

🟡
🟢
🔵
🟣




# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🕳Pitfalls

Let $\displaystyle{{\rm A} = \begin{pmatrix}1 &2\\2 &4\end{pmatrix}}, \displaystyle{{\rm B} = \begin{pmatrix}2 &1\\1 &3\end{pmatrix}}$ and $\displaystyle{{\rm C} = \begin{pmatrix}4 &3\\0 &2\end{pmatrix}}$. Verify that ${\rm A B}={\rm AC}$ and yet ${\rm B}\ne {\rm C}$.



# ⌨Sample Code
**🖱️matrix product in julia**
#julia 

```julia
julia> A=[1 2; 2 4;]
2×2 Matrix{Int64}:
 1  2
 2  4

julia> B=[2 1; 1 3;]
2×2 Matrix{Int64}:
 2  1
 1  3

julia> C=[4 3; 0 2;]
2×2 Matrix{Int64}:
 4  3
 0  2

julia> A*B
2×2 Matrix{Int64}:
 4   7
 8  14

julia> A*C
2×2 Matrix{Int64}:
 4   7
 8  14
```

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized
