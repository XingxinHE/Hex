---
aliases: [linear dependent,linearly dependent]
---

# 📝Definition
- The [[set]] of $n$- [[vector]] $\{a_1, ..., a_k\}$ (with $k\geq1$) is linearly dependent if
    - $$
      \beta_1\alpha_1+\cdots+\beta_k\alpha_k=0
      $$
    
- holds for some $\beta_1,... ,\beta_k$, that are **not all zero**. (a.k.a. at least one of them is non-zero)

# 🧠Intuition
- At least one column does not contribute anything new to the matrix.
- At least at least one $a_i$ is a [[Linear Combination]] of the others.

# 🌓Complement
- [[Linear Independence]]

# ⛈Characteristics / Properties
- 📌The character of linear dependent of $n$-vector
    - For $1$-vector
        - $\{a_1\}$ is linearly dependent **only if** $a_1 = 0$
        
    - For $2$-vector
        - $\{a_1,a_2\}$ is linearly dependent **only if** one $a_i$ is a multiple of the other. (a.k.a $a_1=m\cdot a_2$ where $m$ is a real number)
        
    - For $k$-vector st. $k>2$
        - for more than two vectors, there is no simple to state condition
        
# 🗃Example
- 📌example of linear dependent vector
    - the vectors
        - $$
          a_1 = \begin{bmatrix}0.2\\-7\\8.6\end{bmatrix}
          a_2 = \begin{bmatrix}-0.1\\2\\-1\end{bmatrix}
          a_3 = \begin{bmatrix}0\\-1\\2.2\end{bmatrix}
          $$
        
    - They are linearly dependent, because
    - Solution 1
        - $a_1 + 2a_2 - 3a_3 = 0$
        
    - Solution 2
        - $a_2 = (-1/2)a_1 + (3/2)a_3$
        