---
aliases: []
tags:
  - mathematics
  - geometry
  - calculus
---

https://mathworld.wolfram.com/Plane-PlaneIntersection.html
# 📝Definition
lines are parallel if and only if they have the same direction, two planes are parallel if and only if their [[normal vector|normal]]s are parallel, or $\mathbf{n}_1 = k\mathbf{n}_2$ for some scalar $k$. Two planes that are not parallel **intersect** in a [[line]].
![|300](../assets/plane_plane_intersection.svg)




**📄geometric method**
1️⃣ Take the [[cross product]] of the 2 normal vectors which will be a vector perpendicular to $\mathbf{n}_1$ and $\mathbf{n}_2$.
2️⃣ Find a point on the intersection line.

**📑numeric method**
A general approach avoiding the special treatment needed above is to take advantage from [[Hessian normal form]] which defines
$$
\begin{align}
A	&=
\begin{bmatrix}
\hat{\mathbf{n}}_1&\hat{\mathbf{n}}_2
\end{bmatrix}
^\operatorname{T}\\
\mathbf{b} &=	-\begin{bmatrix}p_1 \\ p_2\end{bmatrix}.
\end{align}
$$
Then use a linear solving technique to find a particular solution $\mathbf{x_0}$ to 
$$
A\mathbf{x_0}=\mathbf{b},
$$
and the direction vector will be given by the [[null space]] of $A$.

> [!info] Remark
> - (for *education*) The notion of "geometric" refers to I am doing this calculation by the understanding of the geometric meaning of the process.
> - (for *computation*) The notion of "numeric" refers to I don't care how it work and I just plug into a linear solver.


# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁plane-plane example 1
	- 💬Question:
		- (1)Find a vector parallel to the line of intersection of the planes $3x - 6y - 2z = 15$ and $2x + y - 2z = 5$.
		- (2)Find parametric equations for the line those planes intersected.
	- 🏹Strategy: Try 2 things. geometric method and numeric method.
	- ✏Solution:
		- Solution on (1)
			- geometric method
				- Take the cross product of the 2 normal vectors.
				- $\mathbf{n}_1\times\mathbf{n}_2=\begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\3&-6&-2\\2&1&-2\end{vmatrix}=14\mathbf{i}+2\mathbf{j}+15\mathbf{k}.$
			- numeric method
				- Recall what is a Hessian normal form.
					- $\hat{\mathbf{n}}\cdot\mathbf{r}=-p$
				- The 2 planes in Hessian form then would be.
					- $\begin{bmatrix}3/7\\-6/7\\-2/7\end{bmatrix}\cdot\mathbf{r_1}=-15/7$ 
					- $\begin{bmatrix}2/3\\1/3\\-2/3\end{bmatrix}\cdot\mathbf{r_2}=-5/3$
				- Then
					- $A=\begin{bmatrix}\hat{\mathbf{n}}_1&\hat{\mathbf{n}}_2\end{bmatrix}^\operatorname{T}=\begin{bmatrix}3/7&2/3\\-6/7&1/3\\-2/7&-2/3\end{bmatrix}^\operatorname{T}$
					- $\mathbf{b}=-\begin{bmatrix}p_1 \\ p_2\end{bmatrix}=\begin{bmatrix}15/7\\ 5/3\end{bmatrix}$
				- By using #julia , we have
					- `n1=[3/7; -6/7; -2/7;]`
					- `n2=[2/3; 1/3; -2/3;]`
					- `A=[n1 n2]`
					- `b=[15/7; 5/3;]`
					- `x = A'\b`
			- Verify they are same.
				- `y = [14;2;15]`
				- `dot(x,y)`
				- The result is $0$ which means they are parallel.
		- Solution on (2)
			- From (1) we already know the vector, and obtain just *one* point will solve this question.
			- Let's plug a random number that $z=0$ in both equation.
			- $3x - 6y - 2\times0 = 15$ and $2x + y - 2\times0 = 5$.
			- we can calculate that the point is $(3, -1, 0).$
			- The line is $x = 3 + 14t,\quad y = -1 + 2t,\quad z = 15t .$
	- 🗣Note: The choice $z = 0$ is **arbitrary** and we could have chosen **z = 1** or **z = -1** just as well. Or we could have let $x = 0$ and solved for $y$ and $z$. The different choices would simply give different parametrizations of the same line.



# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized