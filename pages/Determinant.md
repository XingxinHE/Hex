---
aliases: []
tags:
  - LinearAlgebra
  - mathematics
  - matrix
---


- 📋Prerequisite
    - Determinants are defined **only** for [[square matrix]] .
    - Understand [[matrix#^5cd25e079d5be40e|cofactor matrix]].
    
- 📝Definition
    - The determinant of an $n\times n$ matrix $M$ is given by the formulas
        - $i$ is row, $j$ is column
        - $C$ is [[matrix#^5cd25e079d5be40e|cofactor matrix]].
        - $$
          \begin{align}
          \mathbf{det}M =& \sum^{n}_{i=1}M_{ik}C_{ik}\\
          \text{and}\\
          \mathbf{det}M =& \sum^{n}_{j=1}M_{kj}C_{kj}\\\\
          \end{align}
          $$
        
- 🎯Intent
    - Determinants are mathematical objects that are very useful in the analysis and solution of [systems of linear equations](https://mathworld.wolfram.com/SystemofEquations.html).
    
- 🧠Intuition
    - The *determinant* of a matrix tell you how much the linear transformation is.
        - For example
            - In 2D, the determinant is how much does the **area** of unit $1\times1$ square change?
            - In 3D, the determinant is how much does the **volume** of unit $1\times1\times1$ cube change?
            
- 🐍Algorithm
    - Calculation of determinant
        - $$
          \begin{align}
          \begin{align}
          \text{det}
          \Bigg(
          \begin{bmatrix}
          a&b&c\\
          d&e&f\\
          g&h&i
          \end{bmatrix}
          \Bigg)
          =&a\text{ det}\bigg(\begin{bmatrix}e&f\\h&i\end{bmatrix}\bigg)\\
          -&b\text{ det}\bigg(\begin{bmatrix}d&f\\g&i\end{bmatrix}\bigg)\\
          +&c\text{ det}\bigg(\begin{bmatrix}d&e\\g&h\end{bmatrix}\bigg)\\
          \end{align}
          \end{align}
          $$
          
        - Therefore, it is a **recursively** process.
        
- 🗃Example
    - 📌example of determinant of $2\times 2$ matrix
        - $$
          \begin{align}
          \mathbf{ det}\bigg(\begin{bmatrix}a&b\\c&d\end{bmatrix}\bigg) =& ad-bc
          \end{align}
          $$
        
    - 📌example of determinant of $3\times 3$ matrix
        - $$
          \begin{align}
          \mathbf{det}
          \Bigg(
          \begin{bmatrix}
          a&b&c\\
          d&e&f\\
          g&h&i
          \end{bmatrix}
          \Bigg)
          =&a\mathbf{ det}\bigg(\begin{bmatrix}e&f\\h&i\end{bmatrix}\bigg)\\
          -&b\mathbf{ det}\bigg(\begin{bmatrix}d&f\\g&i\end{bmatrix}\bigg)\\
          +&c\mathbf{ det}\bigg(\begin{bmatrix}d&e\\g&h\end{bmatrix}\bigg)\\
          \end{align}
          $$
          