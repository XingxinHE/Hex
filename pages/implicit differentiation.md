---
aliases: []
tags:
  - unknown
---


# 📝Definition
## single variable version
The method of *implicit differentiation* is the following.
- 1️⃣ Differentiate both sides of the equation with respect to $x$, treating $y$ as a [[differentiable]] function of $x$.
- 2️⃣ Collect the terms with $dy/dx$ on one side of the equation and solve for $dy/dx$.

## multivariable version
Suppose that $F(x, y)$ is [[differentiable]] and that the equation $F(x, y) = 0$ defines $y$ as a differentiable function of $x$. Then at any point where $F_y \neq 0$,
$$
\frac{dy}{dx}=-\frac{F_x}{F_y}.
$$



# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁implicit differentiation single variable example ^a95af4
	- 💬Question: Find $dy/dx$ if $y^2 - x^2 - \sin xy= 0$
	- ✏Solution:
		- We differentiate the equation implicitly.
		- $$\begin{align}y^2 &= x^2 + \sin xy \\ \frac{d}{dx}(y^2)&=\frac{d}{dx}(x^2)+\frac{d}{dx}(\sin xy) \\ 2y\frac{dy}{dx}&=2x+(\cos xy)\frac{d}{dx}(xy) \\ 2y\frac{dy}{dx}&=2x+(\cos xy)(y+x\frac{dy}{dx}) \\ (2y-x\cos xy)\frac{dy}{dx}&=2x+y\cos xy \\ \frac{dy}{dx}&=\frac{2x+y\cos xy}{2y-x\cos xy}\end{align}$$


- 📁implicit differentiation multivariable version example ^0616f6
	- 💬Question: Find $dy/dx$ if $y^2 - x^2 - \sin xy= 0$
	- ✏Solution: 
		- Take $F(x,y)=y^2 - x^2 - \sin xy$.
		- Then recall the formula.
			- $\frac{dy}{dx}=-\frac{F_x}{F_y}$
			- $F_x = -2x-y\cos xy$
			- $F_y = 2y-x\cos xy$
			- $$\frac{dy}{dx}=-\frac{F_x}{F_y}=-\frac{-2x-y\cos xy}{2y-x\cos xy}=\frac{2x+y\cos xy}{2y-x\cos xy}$$
	- 🗣Answer: Compare to [[implicit differentiation#^a95af4]], this multivariable version is much more easier.


# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized