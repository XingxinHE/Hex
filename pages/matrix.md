- # 📝Definition
	- A matrix is a rectangular array of numbers, e.g.
		- $$
		  \begin{bmatrix}
		  0&1&-2.3&0.1\\
		  1.3&4&-0.1&0\\
		  4.1&-1&0&1.7
		  \end{bmatrix}
		  $$
- # 🧠Intuition
	- When encounter a matrix, you should immediately be aware ==**what the row and column means**==.
- # 🎯Intent
	- In computer graphic,
		- It means to cover calculation between different Cartesian coordinate spaces.
- # 🧪Composition
	- Suppose $A$ is an $m\times n$ matrix with entries $A_{ij}$ for $i=1,...,m,\space j=1,...,n$
	- 📌Column
		- Its $j$th column is the $m$-vector
		- $$
		  \begin{bmatrix}
		  A_{1j}\\\vdots\\A_{mj}
		  \end{bmatrix}
		  $$
	- 📌Row
		- Its $i$th row is the $n$-row-vector.
		- $$
		  \begin{bmatrix}
		  A_{i1}&\cdots&A_{in}
		  \end{bmatrix}
		  $$
	- 📌Slice of Matrix
		- $A_{p:q,r:s}$ is the $(q-p+1)\times (s-r+1)$ matrix
		- $$
		  A_{p:q,r:s}=
		  \begin{bmatrix}
		  A_{pr}&A_{p,r+1}&\cdots&A_{ps}\\
		  A_{p+1,r}&A_{p+1,r+1}&\cdots&A_{p+1,s}\\
		  \vdots&\vdots&\space&\vdots\\
		  A_{qr}&A_{q,r+1}&\cdots&A_{qs}\\
		  \end{bmatrix}
		  $$
- # ✒Notation
	- **⚠==Warning==**
		- You should be aware there is a huge difference between "math notation" and "computer science notation" of Matrix.
	- 📌General Notation
		- id:: 73e387de-a492-4c49-89d9-c9e5ba5d8a2e
		  $$
		  M_{ij} = \begin{bmatrix}
		  F_{11}&F_{12}&F_{13}&F_{14}\\
		  F_{21}&F_{22}&F_{23}&F_{24}\\
		  F_{31}&F_{32}&F_{33}&F_{34}\\
		  \end{bmatrix}
		  $$
		- where $i$ and $j$ represents $i$-th row of the $j$-th column. In this case, $i=3,j=4$
	- 📌Column picture of matrix
		- An $m\times n$ matrix $A$ can express as block matrix with its ($m$-vector) columns $a_1,...,a_n$
		- $$
		  A = \begin{bmatrix}
		  a_1&a_2&\cdots&a_n
		  \end{bmatrix}
		  $$
		- 💡a.k.a The $a_1$ you saw is not just a number, but a $m$-vector(column) ==stacked== into $a_1$. It could be exploded ==vertically==.
	- 📌Row picture of matrix
		- An $m\times n$ matrix $A$ can express as block matrix with its ($n$-row-vector) columns $b_1,...,b_m$
		- $$
		  A = \begin{bmatrix}
		  b_1\\b_2\\\vdots\\b_m
		  \end{bmatrix}
		  $$
		- 💡a.k.a The $b_1$ you saw is not just a number, but a $n$-vector(row) ==squeezed== into $b_1$. It can be exploded ==horizontally==.
- # ⛈Characteristics / Properties
	- 📌size
		- The size is given by (row dimension) $\times$ (column dimension).
	- 📌 [[scalar]]-matrix arithmetic operation properties
		- Given any two scalars $a$ and $b$ and any three $m\times n$ matrices $F$, $G$, and $H$, the following properties hold.
		- $$
		  F+G=G+F\\
		  (F+G)+H = F+(G+H)\\
		  a(bF)=(ab)F\\
		  a(F+G) = aF+aG\\
		  (a+b)F = aF+bF\\
		  (F+G)^T=F^T+G^T
		  $$
	- 📌 [[scalar]]-matrix-matrix arithmetic operation properties
		- Given any scalar $a$, an $n\times m$ matrix $F$, an $m\times p$ matrix $G$, and a $p\times q$ matrix $H$, the following properties hold.
		- $$
		  (aF)G = a(FG)\\
		  (FG)H = F(GH)\\
		  (FG)^T = G^TF^T
		  $$
	- 📌Matrix Norm
		- 📝Definition
			- For $m\times n$ matrix A, we define
			- $$
			  \lVert A\rVert=\bigg(\sum_{i=1}^{m}\sum_{j=1}^{n}A_{ij}^2\bigg)^{1/2}
			  $$
		- ⛈Characteristics / Properties
			- satisfies norm properties:
			- $$
			  \lVert\alpha A\rVert=\lvert a\rvert \lVert A\rVert\\
			  \lVert\alpha A+B\rVert \leq \lVert A\rVert+\lVert B\rVert\\
			  \lVert A\rVert\geq0\\
			  \lVert A\rVert=0\text{ only if }A=0
			  $$
- # 💫Support Operation
	- 📌Complexity of Matrix operation
		- Suppose $m\times n$ matrix $A$.
		- Storage.
			- stored $A$ as $m\times n$ array of numbers. For sparse $A$, store only $\bold{nnz}(A)$ nonzero values.
		- Matrix Addition and Subtraction
			- It costs $mn$ [flops](((632141f6-8c0c-40c2-bab8-bce388937019))).
		- Matrix-Vector multiplication
			- It costs $m(2n-1)\approx2mn$ [flops](((632141f6-8c0c-40c2-bab8-bce388937019))). (for sparse $A$, around $2\bold{nnz}(A)$ [flops](((632141f6-8c0c-40c2-bab8-bce388937019))))
	- ## 📌Addition and Subtraction
		- We can add or subtract matrices of the same size:
			- $$
			  (A + B)_{ij} = A_{ij} + B_{ij},\quad i = 1,...,m\quad j = 1,...,n
			  $$
	- ## 📌 [[scalar]] multiplication
		- $$
		  (\alpha A)_{ij}=aA_{ij},\quad i = 1,...,m\quad j = 1,...,n
		  $$
	- ## 📌Transpose
		- 📝Definition
			- The transpose of an $m\times n$ matrix $A$ is denoted $A^T$ , and defined by
				- $$
				  (A^T)_{ij} = A_{ji}, i = 1,...,n\quad j = 1,...,m
				  $$
		- ⛈Characteristics
			- Transpose converts column to row vectors (and vice versa).
				- $$
				  (A^T)^T=A
				  $$
		- 🗃Example
			- Simple example
				- $$
				  \begin{bmatrix}
				  0 & 4 \\
				  7 & 0 \\
				  3 & 1 
				  \end{bmatrix}^T=\begin{bmatrix}
				  0 & 7 & 3 \\
				  4 & 0 & 1 
				  \end{bmatrix}
				  $$
			- The transpose of [this matrix](((73e387de-a492-4c49-89d9-c9e5ba5d8a2e))) is:
				- $$
				  M_{ij}^T = 
				  \begin{bmatrix}
				  F_{11}&F_{21}&F_{31}\\
				  F_{12}&F_{22}&F_{32}\\
				  F_{13}&F_{23}&F_{33}\\
				  F_{14}&F_{24}&F_{34}\\
				  \end{bmatrix}
				  $$
	- ## 📌Matrix-Vector Products
	  id:: 6338f24c-ceaa-47b3-8f93-437461a1dc34
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
	- ## 📌Matrix Products
		- If there are matrices $F$($n\times m_1$) and $G(m_2\times p)$, **the prerequisite for a valid matrix multiplication is** that $m_1=m_2$. Then the product is a matrix with shape $n\times p$. The $i,j$ element of the matrix is:
			- $$
			  (FG)_{ij} = \sum_{k=1}^{m}F_{ik}G_{kj}
			  $$
			- The `2,2` element of output matrix is the dot product of $2$-th row of $F$ and $2$-th colomn of $G$
			- $$
			  M_{22}=\begin{bmatrix}3&0&1\end{bmatrix}\begin{bmatrix}2\\0\\2\end{bmatrix}
			  $$
- # 🏷(Sub)Categories
	- 📌Zero Matrix
		- $m\times n$ zero matrix has all entries zero, written as $0_{m\times n}$ or just $0$.
	- 📌Identity Matrix
		- Identity matrix is a square matrix with $I_{ii}=1$ and $I_{ij}=0$ for $i\neq j$.
		- The notation implies that if the element is $1$, the row and column have to be the same index. Therefore written as $I_{ii}$, e.g. $I_{3,3}=1$
		- $$
		  \begin{bmatrix}
		  1&0\\0&1
		  \end{bmatrix},
		  \begin{bmatrix}
		  1 & 0 & 0 & 0 \\
		  0 & 1 & 0 & 0 \\
		  0 & 0 & 1 & 0 \\
		  0 & 0 & 0 & 1 
		  \end{bmatrix}
		  $$
	- 📌Sparse Matrix
		- Most entries are $0$.
		- can be stored and manipulated efficiently
		- $\bold{nnz}(A)$ is number of nonzero entries
- # 🤳Applicability
	- 📌Matrix Representation
		- image
			- We can use matrix $X$ to represent an image. $X_{ij}$ is $i, j$ pixel value in a monochrome image.
		- rainfall data
			- We can use matrix $A$ to represent a rain fall data.
			- The row is a bunch of location(Shanghai, Beijing, Boston) and the columns is the day(Day1, Day2, Day365).
			- $A_{ij}$ is rainfall at location $i$ on day $j$
		- multiple asset returns
			- We can use matrix $R$ to represent asset returns.
			- The row is the period, e.g. 1st quarter, 3rd quarter. The column is the asset type, e.g. stock, house renting revenue...
			- $R_{ij}$ is return of asset $j$ in period $i$.
		- contingency table: $A_{ij}$ is number of objects with first attribute $i$ and second attribute $j$
		- feature matrix: $X_{ij}$ is value of feature $i$ for entity $j$
	- 📌 [[Graph]]
		- We can use matrix to denote a graph or a relation. A directed graph can be represented as $m\times n$ matrix with $A_{ij}=1$ if $(i,j)\in R$. $R$ is the relation.
		- {{embed ((63395407-b179-4c98-91ea-3fe021021ae0))}}
		- For preceding graph,
		  id:: 63395397-23d2-42d9-b8be-b61f43d8e59f
			- it can be represented as $6\times6$ matrix as followed.
			- $$
			  \begin{bmatrix}
			  0 & 1 & 0 & 0 & 0 & 0 \\
			  1 & 0 & 0 & 1 & 0 & 0 \\
			  0 & 0 & 0 & 0 & 0 & 0 \\
			  0 & 0 & 0 & 0 & 0 & 0 \\
			  0 & 0 & 0 & 1 & 0 & 1 \\
			  1 & 0 & 1 & 0 & 0 & 0 
			  \end{bmatrix} 
			  $$
			- $A_{2,4}=1$ means there is a directed edge from $2$ to $4$.
			- $A_{3,6}=0$ means there is no directed edge from $3$ to $6$.
			- $A_{6,3}=1$ means there is a directed edge from $6$ to $3$.
- # ⌨Sample Code
	- 📌Matrix Representation
		- ``` julia
		  julia> A = [0.0 1.0 -2.3 0.1;
		              1.3 4.0 -0.1 0.0;
		              4.1 -1.0 0.0 1.7]
		  3×4 Matrix{Float64}:
		   0.0   1.0  -2.3  0.1
		   1.3   4.0  -0.1  0.0
		   4.1  -1.0   0.0  1.7
		  ```
	- 📌Matrix-Matrix Product
		- Python
			- ```python
			  >>> import numpy as np
			  >>> F = np.array([[2,3,1],
			                    [3,0,1]])
			  >>> G = np.array([[1,2],
			                    [4,0],
			                    [3,2]])
			  >>> F@G
			  array([[17,  6],
			         [ 6,  8]])
			  ```
		- Julia
			- ``` julia
			  julia> F = [2 3 1;
			              3 0 1]
			  2×3 Matrix{Int64}:
			   2  3  1
			   3  0  1
			  
			  julia> G = [1 2;
			              4 0;
			              3 2]
			  3×2 Matrix{Int64}:
			   1  2
			   4  0
			   3  2
			  
			  julia> F*G
			  2×2 Matrix{Int64}:
			   17  6
			    6  8
			  ```