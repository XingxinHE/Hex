---
aliases: [matrix-vector multiplication]
---

# ✒Notation
$$
\begin{align}
Ax
\end{align}
$$
- When you saw the preceding pattern, it is matrix-vector multiplication.

# 📝Definition
- The matrix-vector product of $m\times n$ matrix $A$, $n$-vector $x$, denoted $y = Ax$, with
    - $$
      y_i=A_{i1}x_1+\cdots+A_{in}x_n,\quad i=1,...,m
      $$
    
# 🧠Intuition
- Remember, the meaning row and column is of enormous importance!
- Quick digest matrix-vector multiplication
    - $$
      \begin{align}
      \begin{bmatrix}
      0&2&-1\\-2&1&1
      \end{bmatrix} 
      \begin{bmatrix}2\\1\\-1\end{bmatrix}&=
      2\begin{bmatrix}0\\-2\end{bmatrix}+
      1\begin{bmatrix}2\\1\end{bmatrix}+
      -1\begin{bmatrix}-1\\1\end{bmatrix}\\
      &=
      \begin{bmatrix}0\\-4\end{bmatrix}+
      \begin{bmatrix}2\\1\end{bmatrix}+
      \begin{bmatrix}1\\-1\end{bmatrix}\\
      &=\begin{bmatrix}3\\-4\end{bmatrix}
      \end{align}
      $$
      
# 🏷Categories
- Matrix-Vector Multiplication has 2 picture, by rows and by columns.
## Rows Picture in Matrix-Vector Multiplication
- ✒Notation
    - $$
      \begin{bmatrix}
      2 & 3 \\
      2 & 4 \\
      3 & 7 
      \end{bmatrix}
      \begin{bmatrix}
      x_1 \\
      x_2 
      \end{bmatrix}=\begin{bmatrix}
      2x_1+3x_2 \\
      2x_1+4x_2 \\
      3x_1+7x_2 
      \end{bmatrix}
      $$
    
- 🎯Intent
    - This is the way to find separate components for the result. Therefore, we use this form for ==**computation**==.
    
- 📝Definition
    - The row picture can be seen as a result of 3 [[dot product]]s.
        - $$
          \begin{bmatrix}
          2&3
          \end{bmatrix}
          \begin{bmatrix}
          x_1\\x_2
          \end{bmatrix}=2x_1+3x_2
          $$
        
## Column Picture in Matrix-Vector Multiplication⭐
- ✒Notation
    - $$
      \begin{bmatrix}
      2 & 3 \\
      2 & 4 \\
      3 & 7 
      \end{bmatrix}
      \begin{bmatrix}
      x_1 \\
      x_2 
      \end{bmatrix}=x_1\begin{bmatrix}
      2 \\
      2 \\
      3 
      \end{bmatrix}+x_2\begin{bmatrix}
      3 \\
      4 \\
      7 
      \end{bmatrix}
      $$
    
- 🎯Intent
    - We use this form to ==**understand**==.
    
- 📝Definition
    - The column picture
        - 1️⃣first digest the matrix into [[matrix#^22608a853b87cf2e|columns]] vector.
            - $$
              a_1=\begin{bmatrix}
              2 \\
              2 \\
              3 
              \end{bmatrix}\quad a_2=\begin{bmatrix}
              3 \\
              4 \\
              7 
              \end{bmatrix}
              $$
            
        - 2️⃣And then multiply the columns by scalars
            - $$
              x_1\quad x_2
              $$
            
        - 3️⃣Add vectors
            - $$
              x_1\bold{a_1}+x_2\bold{a_2}=Ax
              $$
            - Notice that $\bold{a_1},\bold{a_2}$ are column vectors.
            
    - ⭐**==Conclusion==**: Column picture sees $Ax$ as a " [[linear combination]]" of $a_1$ and $a_2$. Therefore, $Ax$ is a [[linear combination]] of the columns of $A$. This is fundamental!!
  -
  
- 🗃Example

- 🧀Applicability
    - Matrix-Vector Multiplication as mean
        - $\tilde{x}=Ax$ is de-meaned version of $x$, with
        - $$
          A=\begin{bmatrix}
          1-1/n&-1/n&\cdots&-1/n\\
          -1/n&1-1/n&\cdots&-1/n\\
          \vdots&&\ddots&\vdots\\
          -1/n&-1/n&\cdots&1-1/n\\
          \end{bmatrix}
          $$
          
    - Return matrix – portfolio vector
        - Suppose $R$ is $T\times n$ matrix of assets returns
            - $R_{ij}$ is return of asset $j$ in period $i$ (say, in percentage)
            - $n$-vector $w$ gives portfolio (investments in the assets)
            
        - Then the Matrix-Vector multiplication
            - $$
              Rw=M
              $$
            
        - $T$-vector $M$ is the result of $Rw$ which is time series of the portfolio return
        - $\bold{avg}(Rw)$ is the portfolio (mean) return, $\bold{std}(Rw)$ is its risk.
        
    - Feature Matrix
        - $$
          s=X^Tw
          $$
        - $s$, the score
        - $X$ the feature matrix, row-features, column-objects
        - $w$ is a weight vector which giving scroes.
        
  -
  
