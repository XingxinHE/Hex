- # 📝Definition
	- Suppose that $f: \mathbb{R^n} \to \mathbb{R}$ is differentiable, which means that its partial derivatives exist. Let $z$ be an $n$-vector. The (first-order) *Taylor Approximation* of $f$ near (or at) the point $z$ is the function $\hat{f}(x)$ of $x$ defined as:
	  $$
	  \hat{f}(x)=f(z)+\frac{\partial f}{\partial x_1}(z)(x_1-z_1)+\cdots+\frac{\partial f}{\partial x_n}(z)(x_n-z_n)
	  $$
	- $\frac{\partial f}{\partial x_i}(z)$ , denotes the partial derivative of $f$ with respect to its $i$th argument, evaluated at the $n$-vector $z$.
	- $\hat{f}$  ,  the hat is a hint that it is an approximation of the function $f$.
	- $\hat{f}(x;z)$  , is written with 2nd argument to show the point  $z$ at which the approximation is developed.
	- $f(z)$  , the first item of Taylor is **constant**, while others can be seen as the contributions to the change(from $f(z)$) due to the changes in the component of $x$ (from $z$).
- # 🎯Intent
	- The intent is to do a scalar-valued operation of $n$ variables, or **relations** between $n$ variables and a scalar.
	  $$
	  \begin{bmatrix}
	  x_1\\x_2\\\vdots\\x_n 
	  \end{bmatrix}
	  \to a
	  $$
	- Normally, this relation is **approximated** by
		- [[Linear Function]]
		- [[Affine Function]]
	- Sometime these 2 functions are called **model**.
- # ⛈Characteristics
	- 📌$\hat{f}$ **is** an [[Affine Function]] of $x$
		- Apparently, since there is always a $f(z)$ ,which is a constant, in the beginning, $\hat{f}(x)$ is therefore an **affine function**. It could be written as followed:
		  $$
		  \hat{f}(x)=f(z)+\nabla f(z)^T(x-z)
		  $$
			- $f(z)$, it is a constant which is the value of this function when $x=z$
			- $\nabla f(z)$  , is a $n$-vector, the **gradient** of $f$ at the point $z$ is:
			  
			  $$
			  \nabla f(z)=\begin{bmatrix}\frac{\partial f}{\partial x_1}(z)\\\vdots\\\frac{\partial f}{\partial x_n}(z)\end{bmatrix}
			  $$
			- $(x-z)$, the **deviation/perturbation(偏差/扰动)** of $x$ respect to $z$
		- Therefore we can write the Taylor Approximation in the form of affine function
			- $$
			  \hat{f}(x)=f(z)+\nabla f(z)^T(x-z)=\underbrace{\nabla f(z)^T}_\text{"a"}x+\underbrace{f(z)-\nabla f(z)^Tz}_\text{"b"}
			  $$
	- 📌elaboration on "approximation"
		- A simple example, for $n = 1$, is shown in the following figure. Over the full $x$-axis scale shown, the Taylor approximation $\hat{f}$ does not give a good approximation of the function $f$. But for $x$ near $z$, the Taylor approximation is very **good**.
		- ![name](../assets/taylor_approximation_example.png){:height 300, :width 300}
		- A function $f$ of one variable is called the first-order Taylor approximation $\hat{f}(x)=f(z)+f'(z)(x-z)$ which exactly is [[Linear Approximation]]. The word "linear" emphasizes that the graph of that function is a straight line.
- # 🗃Example
	- Example is the most straightforward way to understand a mathematical concept.
	- 📌Example of using Taylor Approximation
		- Question
			- Consider the function $f : \mathbb{R}^2 \to \mathbb{R}$ given by $f(x) = x_1 + \text{exp}(x_2 − x_1 )$ , which is not linear or affine. The assignment is to **find** the Taylor Approximation $\hat{f}$ **near the point** $z=(1,2)$.
		- Solution
			- take the partial derivative of this function:
			  
			  $$
			  \nabla f(z)=
			  \begin{bmatrix}
			  1-\text{exp}(z_2-z_1)\\
			  \text{exp}(z_2-z_1)
			  \end{bmatrix}
			  $$
			- two, place $z_2=2, z_1=1$ in it
			- $\text{exp}=e,\quad e^1=2.7183$, therefore $\nabla f(z)$ at $z=(1,2)$ is:
			  
			  $$
			  \nabla f(z)=
			  \begin{bmatrix}
			  1-e^1\\
			  e^1
			  \end{bmatrix}
			  =
			  \begin{bmatrix}
			  -1.7183\\
			  2.7183
			  \end{bmatrix}
			  $$
			- $f(z)$ at $z=(1,2)$ is:
			  
			  $$
			  f(z)=x_1 + \text{exp}(x_2 − x_1 )=1+e^{2-1}=3.7183
			  $$
			- the Taylor approximation therefore is:
			  
			  $$
			  \begin{align}
			  \hat{f}(x)&=f(z)+\nabla f(z)^T(x-z)\\
			  &=3.7183+\begin{bmatrix}-1.7183&
			  2.7183\end{bmatrix}^T(x-\begin{bmatrix}1\\2\end{bmatrix})\\
			  &=3.7183+\begin{bmatrix}-1.7183&
			  2.7183\end{bmatrix}^T(\begin{bmatrix}x_1\\x_2\end{bmatrix}-\begin{bmatrix}1\\2\end{bmatrix})\\
			  &=3.7183-1.7183(x_1 -1)+2.7183(x_2-2)
			  \end{align}
			  $$
		- Result
			- Use a table to measure the performance of Taylor Approximation at $x=1.00, y=2.00$
			- | $x$           | $f(x)$ | $\hat{f}(x)$ | $\lvert\hat{f}(x)-f(x)\rvert$ |
			  | ------------- | ------ | ------------ | ----------------------- |
			  | (1.00, 2.00)  | 3.7183 | 3.7183       | 0.000                   |
			  | (0.96, 1.98)  | 3.7332 | 3.7326       | 0.0005                  |
			  | (1 .10, 2.11) | 3.8456 | 3.8455       | 0.0001                  |
			  | (0.85, 2.05)  | 4.1701 | 4.1119       | 0.0582                  |
			  | (1.25, 2.41)  | 4.4399 | 4.4032       | 0.0367                  |