---
aliases: []
tags:
  - calculus
  - mathematics
  - optimization
  - VectorCalculus
---


# 📝Definition
The gradient of a scalar-valued [[differentiable]] function $f$ of several variables is the [[vector field]] (or [[vector-valued function]]) $\nabla f$ whose value at a point $p$ is the "**direction and rate of fastest increase**". If the gradient of a function is non-zero at a point $p$, the direction of the gradient is the direction in which the function increases most quickly from $p$, and the magnitude of the gradient is the rate of increase in that direction, the greatest absolute directional derivative. Further, a point where the gradient is the zero vector is known as a [[stationary point]]. 

# ✒Notation
**✏coordinate-free**
In coordinate-free terms, the gradient of a function $f(\bf {r})$ may be defined by:
$$
\begin{align}
df=\nabla f\cdot d{\bf {r}}
\end{align}
$$

where
- $d\bf {r}$ - an infinitesimal displacement 
- $df$ - the total infinitesimal change in $f$ for an infinitesimal displacement($d\bf {r}$)
- $\nabla$ -  the [[vector differential operator]]

**✏coordinate system**
The gradient is given by the [[vector]] whose components are the [[partial derivative]]s of $f$ at $p$. That is, for $f\colon \mathbb {R} ^{n}\to \mathbb {R}$ , its gradient $\nabla f\colon \mathbb {R} ^{n}\to \mathbb {R} ^{n}$  is defined at the point $p=(x_{1},\ldots ,x_{n})$ in $n$-dimensional space as the vector.
$$
{\displaystyle \nabla f(p)={\begin{bmatrix}{\frac {\partial f}{\partial x_{1}}}(p)\\\vdots \\{\frac {\partial f}{\partial x_{n}}}(p)\end{bmatrix}}.}
$$

> [!tip]
> I would like to interpret $\nabla$ as an [[operator]]. It merely means the following wating for inputs.
> $$\nabla ={\begin{bmatrix}{\frac {\partial \textcolor{red}{(?)}}{\partial x}}\\{\frac {\partial \textcolor{red}{(?)}}{\partial y}}\\{\frac {\partial \textcolor{red}{(?)}}{\partial z}}\end{bmatrix}}$$
> When you plug the function in it, the gradient is an operator which gives you a vector.
> $$\nabla f={\begin{bmatrix}{\frac {\partial f}{\partial x}}\\{\frac {\partial f}{\partial y}}\\{\frac {\partial f}{\partial z}}\end{bmatrix}}$$
> The vector is merely all the [[partial derivative]]s.



# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁gradient example 1
	- 💬Question: Compute the gradient of function $$f(x,y)=x^2\sin(y)$$
	- ✏Solution:
		- The gradient is just an operator.
			- $$\nabla ={\begin{bmatrix}{\frac {\partial \textcolor{red}{(?)}}{\partial x}}\\{\frac {\partial \textcolor{red}{(?)}}{\partial y}}\\\end{bmatrix}}$$
		- Plug the function $f$ in it.
			- $$\nabla ={\begin{bmatrix}{\frac {\partial \textcolor{red}{f}}{\partial x}}\\{\frac {\partial \textcolor{red}{f}}{\partial y}}\\\end{bmatrix}}$$
		- Which can be easily computed.
			- $$\nabla ={\begin{bmatrix}{\frac {\partial \textcolor{red}{f}}{\partial x}}\\{\frac {\partial \textcolor{red}{f}}{\partial y}}\\\end{bmatrix}}$$
			- $$\begin{align}\frac {\partial f}{\partial \textcolor{red}x}&=2x\sin(y)\\\frac {\partial f}{\partial \textcolor{red}y}&=x^2\cos(y)\end{align}$$
		- Therefore the gradient of function $f$ is:
			- $$\nabla f(x,y)=\begin{bmatrix}{2x\sin(y)}\\{x^2\cos(y)}\\\end{bmatrix}$$




# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized