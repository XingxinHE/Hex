# 📝Definition
- The name is the essence of this topic.

# 🎯Intent
- Outer product is the key of data science.



# 🧠Intuition
- 📌Outer product impression
    - $\mathbf{ab}^T$ is a matrix $\mathbf{ab}^T=A$. If neither $\mathbf{a,b}$ are $0$, the result $A$ is a [[rank one matrix]].
    - $$\begin{align}\begin{bmatrix}1\\3\\2\end{bmatrix}\begin{bmatrix}1&2&10&100\end{bmatrix}&=A\begin{bmatrix}| & |& |\\\mathbf{x} & \mathbf{y}& \mathbf{z}\\ | & |& |\\ \end{bmatrix} \\&= \begin{bmatrix} Ax&Ay&Az \end{bmatrix}\\&=\begin{bmatrix} \begin{bmatrix}1\\3\\2\end{bmatrix}1&\begin{bmatrix}1\\3\\2\end{bmatrix}2&\begin{bmatrix}1\\3\\2\end{bmatrix}10&\begin{bmatrix}1\\3\\2\end{bmatrix}100 \end{bmatrix}\\&=\begin{bmatrix} 1&2&10&100\\ 3&6&30&300\\2&4&20&200 \end{bmatrix}\end{align}$$
    - ![|300](../assets/outer_product.svg)