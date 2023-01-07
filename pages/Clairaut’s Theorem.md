---
aliases: [Mixed Derivative Theorem]
tags:
  - mathematics
---


# 📝Definition
If $f(x, y)$ and its [[partial derivative]]s $f_x, f_y, f_{xy}, f_{yx}$ are defined throughout an open region containing a point $(a, b)$ and are all [[continuity|continuous]] at $(a, b)$, then
$$
f_{xy}(a,b)=f_{yx}(a,b).
$$
> [!info] Remark
> This theorem says that to calculate a mixed second-order derivative, we may differentiate in either order, provided the continuity conditions are satisfied. 


# 🚀Benefit / Pros
This ability to proceed in *different order* sometimes ==simplifies== our calculations. See [[Clairaut’s Theorem#^c11da3]].

# 📏Proof
To prove something...



# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁Clairaut’s Theorem example ^c11da3
	- 💬Question: Find $\partial^2 w/\partial x\partial y$ if $$w=xy+\frac{e^y}{y^2+1}$$
	- ✏Solution:
		- The symbol $\partial^2 w/\partial x\partial y$ tells us to differentiate first with respect to $y$ and then with respect to $x$.
		- Differentiate these chunk $\frac{e^y}{y^2+1}$ is really complicate.
		- However, if we **interchange** the order of differentiation and differentiate first with respect to $\textcolor{red}x$ we get the answer more quickly.
			- $\frac{\partial w}{\partial x}=y$
			- $\frac{\partial^2}{\partial y \partial x}=1$
		- Isn't it beautiful?! 😄


# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized