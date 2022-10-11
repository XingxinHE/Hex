- ## 📝Definition
	- A sum of the elements from some set with constant coefficients placed in front of each.
- # 👑Importance
	- Linear combination is the heart of [[Linear Algebra]].
- ## 🧠Intuition
	- 📌Understanding Linear combination with one expression
		- $$
		  cv+dw=c\begin{bmatrix}1\\1\end{bmatrix}+d\begin{bmatrix}2\\3\end{bmatrix}=\begin{bmatrix}c+2d\\c+3d\end{bmatrix}
		  $$
		- Linear combination is just the following, very simple.
			- **adding** 2 vectors
			- **multiply** vector by numbers
	- TODO use Rhino&Grasshopper to visualize the combination of a point, a line, a plane and R3.
- ## ✒Notation
	- We denote as the following
		- scalar as $\beta_1,\cdots,\beta_n$ ,(also called the coefficients of the linear combination)
		- vector as $a_1,\cdots,a_n$
	- Then the expression of linear combination is.
		- $$
		  \beta_1\alpha_1+\cdots+\beta_n\alpha_n
		  $$
- ## 💫Support Operation
  There are several special linear combination taking advantage of its nature.
	- 📌Use linear combination as Sum
		- when $\beta_1=\cdots=\beta_n=1$
	- 📌Use linear combination as Mean
		- when $\beta_1=\cdots=\beta_n=\frac{1}{n}$
	- 📌Affine combination
		- when $\beta_1+\cdots+\beta_n=1$
	- 📌convex combination / mixture / weighted average
		- when $\beta_1+\cdots+\beta_n=0$
- ## 🗃Example
	- 📌Line and Segment
		- Use $c$ to represent a point on a line formed by $a,b$. Where $\theta$ is a scalar $0\leq\theta\leq1$
		  $$
		  c = (1-\theta)a+\theta b
		  $$
	- 📌Linear Combination Problem Set
		- 💬Question: Restricted by $0\leq c\leq1$ and $0\leq d\leq1$, shade in all the combinations $c\bold{v}+d\bold{w}$. Restricted only by $c\geq0$ and $d\geq0$ draw the "cone" of all combinations $c\bold{v}+d\bold{w}$
			-
		- ✏Solution:
-