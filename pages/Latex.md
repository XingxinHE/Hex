$$
\textcolor{blue}{\text{blue}}
$$

- 📈Diagram
  -
  
$$
 
f(x) = 
    \underbrace{(x + 2)^3}_\text{text 1} + 
    \bigl(
      \mathrlap{\overbrace{\phantom{(c - 2d)}}^{\text{text 2}}}
      (c - 
      \mathrlap{\underbrace{\phantom{2d) + (3e}}_{\text{text 3}}}
      2d) +
      \overbrace{(3e - 4f)}^{\text{text 4}}
    \bigr) + 
    \overbrace{(x - 3)}^\text{text 5}
 
$$

$$
\xRightarrow[g(x)]{f(x)}
$$

$$
\tilde{x}
$$

$$
\overset {\text{l'Hop}}{\Large \sim }
$$

- $\lVert x\rVert$

$$
V = \begin{bmatrix}V_1\\V_2\\\vdots\\V_n\end{bmatrix}
$$

$$
A^{−1}MA=
\begin{bmatrix}
\lambda_1&0&\cdots&0\\
0&\lambda_2&\cdots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&0&\cdots&\lambda_n\\
\end{bmatrix}
$$

$$
\begin{cases}
                c_i(x)=0, & i\in\Epsilon  \text{, Equality等式}\\
                c_i(x)\geq0, & i\in I\text{, Inequality不等式}
        \end{cases}\\
$$

### Symbol and Letters
- | Appearance                       | Code          |
  | -------------------------------- | ------------- |
  | $\tilde{M}$                      | `\tilde{}`    |
  | $\equiv$ , equivalent to         | `\equiv`      |
  | $\not\equiv$ , not equivalent to | `\not\equiv`  |
  | $\bar{A}$                        | `$\bar{A}$`   |
  | $\hat{A}$                        | `$\hat{A}$`   |
  | $\tilde{A}$                      | `$\tilde{A}$` |

### Vectors and Matrix

- 📌  **vertical dashed lines inside a matrix**
  
  > ​	The `c` in `{c:c}` represents the column while `:` represents the dashed line.
  >
  > ​	Therefore, `{c:c}` means the dashed line start from *1* column from the left.
  
  ```latex
  \begin{array}{c:c}
  1 &  2 \\ 
  3 & 4 \\
  5 & 6 \\ 
  \end{array}
  ```
  
  $\begin{array}{c:c}
  1 &  2 \\ 
  3 & 4 \\
  5 & 6 \\ 
  \end{array}$
  
  
  📌 **Matrix Template**
  
  ```latex
  \begin{bmatrix}
  1&0&0\\
  0&1&0\\
  0&0&1\\
  \end{bmatrix}
  ```
  
  $\begin{bmatrix}
  1&0&0\\
  0&1&0\\
  0&0&1\\
  \end{bmatrix}$
  
  **📌Determinant Template**
  
  ```latex
  \begin{vmatrix}
  1 & 4 & 1 \\ 
  0 & -2 & 1 \\ 
  0 & 2 & 1
  \end{vmatrix}
  ```
  
  $\begin{vmatrix}
  1 & 4 & 1 \\ 
  0 & -2 & 1 \\ 
  0 & 2 & 1
  \end{vmatrix}$

### Documentation
- 📌 **Reference equation by tag**
    - You create the equation with `label` and `tag`.
      `$ a = b \tag{a}\label{a} $`
    - Then you can reference the equation:
      `$ \eqref{a} $`
    