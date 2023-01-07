---
aliases: []
tags:
  - unknown
---


# 📝Definition
Laplace's equation is a second-order [[partial differential equation]].
___
The 2-dimensional Laplace equation
$$
\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}=0
$$
___
The 3-dimensional Laplace equation
$$
\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}+\frac{\partial^2 u}{\partial z^2}=0
$$
___
> [!info] Remark
> The solutions of Laplace's equation are call [[harmonic function]]s. The "solution" here indicates a function $u$ satisfies the preceding Laplace's equation. See [[Laplace's equation#^49c924]].

# ✒Notation
This is often written as
$$
\nabla ^{2}f=0
$$
or
$$
\Delta f=0.
$$
where
 - ${\displaystyle \Delta =\nabla \cdot \nabla =\nabla ^{2}}$ is [[Laplace operator]]. 😲Yes. There are 3 types of representation of it.
 - $\nabla \cdot$ is the [[divergence]] operator
 - $\nabla$ is the [[gradient]] operator
 - $f(x,y,z)$ is twice-[[differentiable]] [[real-valued function]]

# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁Laplace's equation example ^49c924
	- 💬Question: Show that the function $u(x, y)= e^x \sin y$ is a solution of Laplace’s equation.
	- ✏Solution:
		- Recall what is the Laplace's equation.
			- $\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}=0$
		- Therefore, we just take the 2nd order partial derivatives of $u$ and check. That's it!
		- For $\frac{\partial^2 u}{\partial x^2}$
			- $\frac{\partial u}{\partial x}=e^x\sin y$
			- $\frac{\partial^2 u}{\partial x^2}=e^x\sin y$
		- For $\frac{\partial^2 u}{\partial y^2}$
			- $\frac{\partial u}{\partial y}=e^x\cos y$
			- $\frac{\partial^2 u}{\partial y^2}=-e^x\sin y$
		- Verify
			- $$\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}=(e^x\cos y)+(-e^x\cos y)=0$$
			- Therefore $u$ is a solution of Laplace's equation.

# 🌱Related Elements


## 🍎Laplace's equation vs. Poisson's equation
Poisson's equation is a generalization of Laplace's equation. For example, let the right-hand side is specified as a given function $h(x,y,z)$, we have
$$
{\displaystyle \Delta f=h.}
$$
Then the preceding is a [[Poisson's equation]].


# 🍂Unorganized