---
aliases: [rank]
tags:
  - LinearAlgebra
  - mathematics
  - matrix
---
# 👑Importance
**💬Question**
Suppose we want the temperature at many points of an engine, there is an equation at every point: easily $n=1000$ unknowns.

**🏹Strategy**
To solve this, $Ax=b$ is a perfect format to solve this.

**🚧Obstacle**
But considering this shape of the matrix $A(m\times n)$:
- $m<n$, many solutions or no solutions to the $m$ equations $Ax=b$
- $m=n$, probably 1 solution to the $n$ equations $Ax=b$
- $m>n$, probably no solution: too many equations with only $n$ unknowns in $x$

**✏Solution**
Therefore, the rank comes in place! **The rank $r$ tells us the ==real size== of our problem**, from independent columns and rows. The beautiful formula is
$$
A=CR=(m\times r)(r\times n)
$$
==3== matices of rank $r$.
> [!note]
> The columns of $A$ that go into $C$ must produce the matrix $I$ inside $R$.



# 📝Definition
The rank of a matrix is the dimension of its column space. It counts the [[linearly independent]] columns.

# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🌈Properties
## 🔴Row Rank = Column Rank
**📝Definition**
Row rank equals column rank for every matrix.
> [!tip]
> That said if $A$ has $r$ independent columns, then $A$ has $r$ independent rows.

**🗃Example**
Inspect the following matrix which has rank $r=1$.
$$
A=\begin{bmatrix}1 &3 &-2\\4 &12 &-8\\2 &6 &-4\end{bmatrix}
$$
Inspect the row:
- $\text{row2}=\text{row1}\times4$
- $\text{row3}=\text{row1}\times2$
Inspect the column:
- $\text{column2}=\text{column1}\times3$
- $\text{column3}=\text{column1}\times-2$



# 🗃Example
📂matrix rank example 1
If $A=\begin{bmatrix}1&2&5\\1&2&5\\1&2&5\end{bmatrix}$ then $C=\begin{bmatrix}1\\1\\1\end{bmatrix}\quad\begin{matrix}n=3\text{ columns in }A\\r=1\text{ column in }C\end{matrix}$
The number $r$ is the "rank" of $A$. It is also the ==rank== of $C$.

# ⌨Sample Code
**🖱 compute the rank in julia**
#julia 
```julia
julia> rank([1 2; 2 1; 3 3;])
2
```

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized