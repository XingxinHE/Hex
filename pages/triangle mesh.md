alias:: simplicial 2-complexes

- ✒Notation
	- explicit mesh representation
		- The following is the typical *_explicit_* mesh representation of a discrete surface immersed in $\mathbb{R}^3$.
		- $V$ - The matrix `V` is $|V|$ by 3 in size.
			- the $i$th row of this matrix contains the $x, y$ and $z$ coordinates of the $i$th vertex of the mesh.
			- $$
			  \begin{array}{rc}
			  &\begin{matrix}\\v_1\\v_2\\\vdots\\v_n\end{matrix}
			  &\begin{array}{ccc}
			  	&\begin{matrix}x&&y&&z\end{matrix}\\
			  	&\begin{bmatrix}v_{1x}&v_{1y}&v_{1z}\\v_{2x}&v_{2y}&v_{2z}\\\vdots&\vdots&\vdots\\v_{nx}&v_{ny}&v_{nz}\\\end{bmatrix}
			  	&\begin{matrix}\end{matrix}\end{array}
			  \end{array}
			  $$
		- $E$ - The matrix `E` is $|E|$ by 2 size.
		- $F$ - The matrix `F` is $|F|$ by 3 in size.
			- the $j$th row of this matrix contains the indices into the rows of `V` of the first, second and third corners of the $j$th triangle as a non-negative number (remember in C++ arrays and matrices start with index `0`).
- ⛈Characteristics / Properties
	- {{embed ((28012548-e918-478b-8a20-78c5d51e7588))}}