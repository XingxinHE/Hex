---
aliases: []
tags:
  - DifferentialGeometry
  - mathematics
---

https://mathworld.wolfram.com/Torsion.html
# 📝Definition
**📄Definition - to understand concept geometrically**
The torsion function of a [[smooth curve]] is
$$
\tau=-\frac{d\mathbf{B}}{ds}\cdot\mathbf{N},
$$
where
- $\mathbf{B}$ denotes the [[binormal vector]]
- $s$ denotes the [[arc length]]
- $\mathbf{N}$ denotes the [[normal vector|principal unit normal vector]]
___
**📑Definition - to understand calculation by parts**
A better equation for calculation would be
$$
\tau=-\frac{\mathbf{B}'(t)\cdot\mathbf{N}(t)}{\lVert\mathbf{r}'(t)\rVert},
$$
where
- $\mathbf{r}$ denotes the [[position vector|radius vector]]

___
**📃Definition - purely for numeric computation**
$$
\tau=
\frac{
\begin{vmatrix}
\dot{x}&\dot{y}&\dot{z}\\
\ddot{x}&\ddot{y}&\ddot{z}\\
\dddot{x}&\dddot{y}&\dddot{z}\\
\end{vmatrix}}
{\lVert\dot{\mathbf{r}}\times\ddot{\mathbf{r}}\rVert^2}
$$
where
- $x,y,z$ are the components of the [[vector-valued function]] $\mathbf{r}$
- the dots are [[Newton’s dot notation]]

> [!info] Remark
> This formula is purely for computation without understanding each component in geometric sense.

# 🧠Intuition
The torsion $\tau$ at a point $P$ on a curve is a measure of how much the curve “twists” at $P$.
- If $\tau$ is positive, the curve twists out of the [[osculating plane]] at $P$ in the direction of the binormal vector $\mathbf{B}$;
- If $\tau$ is negative, the curve twists in the opposite direction.

> [!info] Remark
> It is a bit different from [[curvature]] which is never negative.

# 🗃Example
- 📁pure computation for curvature and torsion example ^8902d2
	- 💬Question: Use pure computation method to find the curvature $\kappa$ and torsion $\tau$ for the helix $$\mathbf{r}(t) = (a\cos t)\mathbf{i} + (a\sin t)\mathbf{j} + (bt)\mathbf{k}\quad a,b\geq0,\quad a^2+b^2=0$$
	- 🏹Strategy:
		- recall the formula.
		- curvature
			- $$\kappa=\frac{\lVert\dot{\mathbf{r}}\times\ddot{\mathbf{r}}\rVert}{\lVert \dot{\mathbf{r}}\rVert^3}$$
		- torsion
			- $$\tau=\frac{\begin{vmatrix}\dot{x}&\dot{y}&\dot{z}\\\ddot{x}&\ddot{y}&\ddot{z}\\\dddot{x}&\dddot{y}&\dddot{z}\\\end{vmatrix}}{\lVert\dot{\mathbf{r}}\times\ddot{\mathbf{r}}\rVert^2}$$
	- ✏Solution:
		- Curvature
			- Find $\dot{\mathbf{r}}$
				- $\dot{\mathbf{r}}=(-a\sin t)\mathbf{i}+(a\cos t)\mathbf{j}+(b)\mathbf{k}$
			- Find $\ddot{\mathbf{r}}$
				- $\ddot{\mathbf{r}}=(-a\cos t)\mathbf{i}+(-a\sin t)\mathbf{j}+(0)\mathbf{k}$
			- Find $\dot{\mathbf{r}}\times\ddot{\mathbf{r}}$
				- $\dot{\mathbf{r}}\times\ddot{\mathbf{r}}=\begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\(-a\sin t)&(a\cos t)&(b)\\(-a\cos t)&(-a\sin t)&(0)\end{vmatrix}=(ab\sin t)\mathbf{i}+(-ab\cos t)\mathbf{j}+(a^2)\mathbf{k}$
			- Find $\lVert \dot{\mathbf{r}}\times\ddot{\mathbf{r}} \rVert$
				- $\lVert \dot{\mathbf{r}}\times\ddot{\mathbf{r}} \rVert = \sqrt{(ab\sin t)^2+(-ab\cos t)^2+(a^2)^2}=\sqrt{a^2 b^2+a^4}=a\sqrt{a^2+b^2}$
			- Find $\lVert \dot{\mathbf{r}} \rVert$
				- $\lVert \dot{\mathbf{r}} \rVert = \sqrt{(-a\sin t)^2+(a\cos t)^2+b^2}=\sqrt{a^2+b^2}$
			- Find $\lVert \dot{\mathbf{r}} \rVert^3$
				- $\lVert \dot{\mathbf{r}} \rVert^3 = (\sqrt{a^2+b^2})^3=(a^2+b^2)^{\frac{3}{2}}$
			- Find curvature
				- $$\kappa=\frac{\lVert\dot{\mathbf{r}}\times\ddot{\mathbf{r}}\rVert}{\lVert \dot{\mathbf{r}}\rVert^3}=\frac{a\sqrt{a^2+b^2}}{(a^2+b^2)^{\frac{3}{2}}}=\frac{a}{a^2+b^2}$$
		- Torsion
			- Find $\begin{vmatrix}\dot{x}&\dot{y}&\dot{z}\\\ddot{x}&\ddot{y}&\ddot{z}\\\dddot{x}&\dddot{y}&\dddot{z}\\\end{vmatrix}$
				- $$\begin{vmatrix}\dot{x}&\dot{y}&\dot{z}\\\ddot{x}&\ddot{y}&\ddot{z}\\\dddot{x}&\dddot{y}&\dddot{z}\\\end{vmatrix}=\begin{vmatrix}(-a\sin t)&(a\cos t)&(b)\\(-a\cos t)&(-a\sin t)&(0)\\(a\sin t)&(-a\cos t)&(0)\\\end{vmatrix}=a^2 b$$
			- Find $\lVert \dot{\mathbf{r}}\times\ddot{\mathbf{r}} \rVert^2$
				- $\lVert \dot{\mathbf{r}}\times\ddot{\mathbf{r}} \rVert^2=(a\sqrt{a^2+b^2})^2=a^2(a^2+b^2)$
			- Find torsion
				- $$\tau=\frac{\begin{vmatrix}\dot{x}&\dot{y}&\dot{z}\\\ddot{x}&\ddot{y}&\ddot{z}\\\dddot{x}&\dddot{y}&\dddot{z}\\\end{vmatrix}}{\lVert\dot{\mathbf{r}}\times\ddot{\mathbf{r}}\rVert^2}=\frac{a^2b}{a^2(a^2+b^2)}=\frac{b}{a^2+b^2}$$

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized