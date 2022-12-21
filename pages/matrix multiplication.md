---
aliases: [matrix product]
tags:
  - LinearAlgebra
  - mathematics
---


# 📝Definition

# 🧠Intuition
Find an intuitive way of understanding this concept.

# ⛈Characteristics
☁
🌧
## 🌨Matrix Multiplication Does Not Commute
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


🌩
⛅
🌤
🌪
🌥
🌦

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