---
aliases: []
tags:
  - mathematics
  - physics
---


# 📝Definition
If $\mathbf{r}$ is the [[position vector]] of a particle moving along a smooth curve in space, then
$$
\mathbf{v}(t)=\frac{d\mathbf{r}}{dt}
$$
is the particle's velocity vector, [[tangent line|tangent]] to the curve. At any time $t$, the direction of $\mathbf{v}$ is the direction of motion, the magnitude of $\mathbf{v}$ is the particle’s speed, and the derivative $\mathbf{a} = d\mathbf{v}/dt$, when it exists, is the particle’s acceleration vector. In summary,
- **Velocity** is the [[derivative]] of position: $\quad\mathbf{v} = \frac{d\mathbf{r}}{dt}$
- **Speed** is the magnitude of velocity: $\quad\text{Speed} = \lVert \mathbf{v} \rVert$.
- **Acceleration** is the derivative of velocity(a.k.a. 2nd derivative): $\quad\mathbf{a} = \frac{d\mathbf{v}}{dt} = \frac{d^2\mathbf{r}}{dt^2}$ .
- The **[[unit vector]]** $\mathbf{v} / \lvert\mathbf{v}\rvert$ is the direction of motion at time $t$.



# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁velocity vector example 1
	- 💬Question: Find the velocity, speed, and acceleration of a particle whose motion in space is given by the position vector $\mathbf{r}(t) = 2 \cos t\mathbf{i} + 2\sin t\mathbf{j} + 5 \cos^2 t\mathbf{k}$. 
	- ✏Solution:
		- Find velocity
			- $$\begin{align}\mathbf{v} = \frac{d\mathbf{r}}{dt}&=-2 \sin t\mathbf{i} + 2\cos t\mathbf{j} - 10 \cos t\sin t\mathbf{k}\\&=-2 \sin t\mathbf{i} + 2\cos t\mathbf{j} - 5 \sin 2t\mathbf{k}\end{align}$$
		- Find acceleration
			- $$\begin{align}\mathbf{a} = \frac{d\mathbf{v}}{dt} &= \frac{d^2\mathbf{r}}{dt^2}\\&=-2 \cos t\mathbf{i} - 2\sin t\mathbf{j} - 10 \cos 2t\mathbf{k}\end{align}$$
		- Find speed
			- $$\begin{align}\lVert \mathbf{v} \rVert=\sqrt{(-2\sin t)^2+(2\cos t)^2+(-5\sin2t)^2}=\sqrt{4+25\sin^2 2t}\end{align}$$





# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized