- 📝Definition
	- The matrix-vector product of $m\times n$ matrix $A$, $n$-vector $x$, denoted $y = Ax$, with
		- $$
		  y_i=A_{i1}x_1+\cdots+A_{in}x_n,\quad i=1,...,m
		  $$
- 🧠Intuition
	- Remember, the meaning row and column is of enormous importance!
	- The most intuitive way to understand matrix-vector multiplication is the following.
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
- 🤳Applicability
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