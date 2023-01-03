---
aliases: [normal, principal unit normal vector]
tags:
  - mathematics
  - geometry
  - calculus
---

https://mathworld.wolfram.com/NormalVector.html
# 📝Definition
**📄Definition - normal vector**
The normal vector to a [[surface]] is a [[vector]] which is perpendicular to the surface at a given point. 
![|400](../assets/NormalVector_700.svg)

> [!info] Remark
> When normals are considered on closed surfaces, the inward-pointing normal (pointing towards the interior of the surface) and outward-pointing normal are usually distinguished.

___

**📑Definition - principal unit normal vector**
At a point where $\kappa \neq 0$, the ==principal unit normal vector== for a [[smooth curve]] in the plane is
$$
\mathbf{N}=\frac{1}{\kappa}\frac{d\mathbf{T}}{ds}.
$$
For calculation, a better representation would be
$$
\mathbf{N}=\frac{d\mathbf{T}/dt}{\lVert d\mathbf{T}/dt\rVert}=\frac{\mathbf{T}'(t)}{\lVert\mathbf{T}'(t) \rVert}=\mathbf{N}(t),
$$
where $\mathbf{T}$ is the [[tangent vector|unit tangent vector]].

# 🧠Intuition
The principal normal vector $\mathbf{N}$ will *point toward the concave side* of the curve.

# 🗃Example
- 📁principal unit normal vector example
	- 💬Question: Find $\mathbf{T}$ and $\mathbf{N}$ for the circular motion $$\mathbf{r}(t)=(\cos2t)\mathbf{i}+(\sin2t)\mathbf{j}.$$
	- 🏹Strategy: xxx
	- 🗣Answer: xxx
	- ✏Solution:
		- Find $\mathbf{T}$ first
			- Recall what is the equation.
				- $$\begin{align}\mathbf{T}(t)&=\frac{\mathbf{v}(t)}{\lVert\mathbf{v}(t)\rVert}=\frac{\mathbf{r}'(t)}{\lVert\mathbf{r}'(t)\rVert}\end{align}$$
			- Find $\mathbf{v}$.
				- $$\begin{align}\mathbf{v}(t)=(-2\sin2t)\mathbf{i}+(2\cos2t)\mathbf{j}\end{align}$$
			- Find $\lVert \mathbf{v}\rVert$
				- $\lVert \mathbf{v}\rVert=\sqrt{(-2\sin2t)^2+(2\cos2t)^2}=2$
			- $$\begin{align}\mathbf{T}(t)&=\frac{\mathbf{v}(t)}{\lVert\mathbf{v}(t)\rVert}=\frac{\mathbf{r}'(t)}{\lVert\mathbf{r}'(t)\rVert}\\&=\frac{(-2\sin2t)\mathbf{i}+(2\cos2t)\mathbf{j}}{2}\\&=(-\sin2t)\mathbf{i}+(\cos2t)\mathbf{j}\end{align}$$
		- Find $\mathbf{N}$
			- Recall the equation.
				- $\mathbf{N}=\frac{\mathbf{T}'(t)}{\lVert\mathbf{T}'(t) \rVert}$
			- Find $\mathbf{T}'(t)$
				- $\mathbf{T}'(t)=(-2\cos2t)\mathbf{i}+(-2\sin2t)\mathbf{j}$
			- Find $\lVert\mathbf{T}'(t) \rVert$
				- $\lVert\mathbf{T}'(t) \rVert=\sqrt{(-2\cos2t)^2+(-2\sin2t)^2}=2$
			- Calculate
				- $\mathbf{N}=\frac{\mathbf{T}'(t)}{\lVert\mathbf{T}'(t) \rVert}=\frac{(-2\cos2t)\mathbf{i}+(-2\sin2t)\mathbf{j}}{2}=(-\cos2t)\mathbf{i}+(-\sin2t)\mathbf{j}$

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized