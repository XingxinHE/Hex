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


# ⛈Characteristics

## 🌦Complexity of matrix multiplication
In the example [[matrix multiplication#^c2f9dd]], the multiplication between matrix $A$($m$ by $n$) and matrix $B$($n$ by $p$) runs up to $2\cdot2\cdot2=8$ times multiplication when $m=n=p=2$.
> [!question]
> Could $n$ by $n$ matrix $A$ and $B$ be multiplied with fewer than $n^3$ samll multiplication? The answer is Yes but it is #thingsIDK . I suppose it is #optimization problem.


# 🗃Example
- 📁matrix multiplication example 1 ^c2f9dd
	- 💬Question: Multiply $AB=\begin{bmatrix}1 &2\\3 &4\end{bmatrix}\begin{bmatrix}5 &6\\7 &8\end{bmatrix}$ both ways.
	- 🏹Strategy: In row way and in column way.
	- ✏Solution:
		- ==Row== way.
			- Big picture is $(\mathbf{Rows\ of\ A})\cdot(\mathbf{Columns\ of\ B})$
			- $$\begin{align}AB&=\begin{bmatrix}\text{row 1$\cdot$ col 1} &\text{row 1$\cdot$ col 2}\\\text{row 2$\cdot$ col 1} &\text{row 2$\cdot$ col 2}\end{bmatrix}\\&=\begin{bmatrix}19 &22\\43 &50\end{bmatrix}\end{align}$$
			- And we take the top cell as an example.
			- (row 1 of $A$)$\cdot$(column 1 of $B$) is $(1,2)\cdot(5,7)=5+14=19$
		- ==Column== way.
			- Big picture: $AB$ is composed by $Ab_1,Ab_2$ which are the combinations of the column of $A$.
			- $$AB=\begin{bmatrix}5\begin{bmatrix}1\\3\end{bmatrix}+7\begin{bmatrix}2\\4\end{bmatrix} &6\begin{bmatrix}1\\3\end{bmatrix}+8\begin{bmatrix}2\\4\end{bmatrix}\end{bmatrix}=\begin{bmatrix}19 &22\\43 &50\end{bmatrix}$$

📩
🗂
📨
📂


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
