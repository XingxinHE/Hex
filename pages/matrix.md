- # 📝Definition
	- A matrix is a rectangular array of numbers, e.g.
		- $$
		  \begin{bmatrix}
		  0&1&-2.3&0.1\\
		  1.3&4&-0.1&0\\
		  4.1&-1&0&1.7
		  \end{bmatrix}
		  $$
- # 🎯Intent
	- It means to cover calculation between different Cartesian coordinate spaces.
- # ✒Notation
	- id:: 73e387de-a492-4c49-89d9-c9e5ba5d8a2e
	  $$
	  M_{ij} = \begin{bmatrix}
	  F_{11}&F_{12}&F_{13}&F_{14}\\
	  F_{21}&F_{22}&F_{23}&F_{24}\\
	  F_{31}&F_{32}&F_{33}&F_{34}\\
	  \end{bmatrix}
	  $$
	- where $i$ and $j$ represents $i$-th row of the $j$-th column. In this case, $i=3,j=4$
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
		  (a+b)F = aF+bF
		  $$
	- 📌 [[scalar]]-matrix-matrix arithmetic operation properties
		- Given any scalar $a$, an $n\times m$ matrix $F$, an $m\times p$ matrix $G$, and a $p\times q$ matrix $H$, the following properties hold.
		- $$
		  (aF)G = a(FG)\\
		  (FG)H = F(GH)\\
		  (FG)^T = G^TF^T
		  $$
- # 💫Support Operation
	- 📌Transpose
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
	- 📌Matrix-Vector Products
	  id:: 6338f24c-ceaa-47b3-8f93-437461a1dc34
		- $$
		  P\times Q=
		  \begin{bmatrix}
		  0&-P_z&P_y\\
		  P_z&0&-P_x\\
		  -P_y&P_x&0
		  \end{bmatrix}
		  \begin{bmatrix}
		  Q_x\\Q_y\\Q_z
		  \end{bmatrix}
		  $$
	- 📌Matrix Products
		- If there are matrices $F$($n\times m_1$) and $G(m_2\times p)$, **the prerequisite for a valid matrix multiplication is** that $m_1=m_2$. Then the product is a matrix with shape $n\times p$. The $i,j$ element of the matrix is:
			- $$
			  (FG)_{ij} = \sum_{k=1}^{m}F_{ik}G_{kj}
			  $$
			- The `2,2` element of output matrix is the dot product of $2$-th row of $F$ and $2$-th colomn of $G$
			- $$
			  M_{22}=\begin{bmatrix}3&0&1\end{bmatrix}\begin{bmatrix}2\\0\\2\end{bmatrix}
			  $$
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