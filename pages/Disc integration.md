---
aliases: [disc method]
---
# 📝Definition
Disc integration, also known in [[definite integral|integral calculus]] as the disc method, is a method for calculating the volume of a solid of revolution of a solid-state material when integrating along an axis "parallel" to the axis of revolution.
# ✒Notation
$$
\begin{align}
dV = \pi y^2\, dx.
\end{align}
$$

# 🧠Intuition
The method of disks gives the differential volume element for a curve rotated about the $x$-axis.
> [!tip] Tips
> Think about 2 major stuffs:
> - what is the radius and the area of the disk?
> - what is the thickness? (that's $\Delta$ or $d$)

# 📈Diagram
![name|250](../assets/images_methoddisks2d.svg)
![name|250](../assets/images_methoddisks3d.svg)
![name](../assets/Disc_integration.svg)
# 🌓Complement
[[Shell integration]]
# 🗃Example
## 📌Classic Sphere Volume
- 💬Question: Find the volume of a ball of radius $a$
	- ![name|150](../assets/a_ball_radius.png)
- 🏹Strategy: The sphere requires only one-time spinning of the upper part.
- ✏Solution:
	- The equation for the upper half of the circle is
		- $$y=\sqrt{a^2-x^2}$$
		- The $y$ is the radius of the disk.
	- Thinking spinning from $-a$ to $a$ will be
		- $$V=\int\pi y^2dx=\int_{x=-a}^{x=a}\pi(a^2-x^2)dx=\big(\pi a^2x-\frac{\pi x^3}{3}\big)\bigg|_{-a}^{a}=\frac{2}{3}\pi a^3-(-\frac{2}{3}\pi a^3)=\frac{4}{3}\pi a^3$$
	- Thinking spinning from $0$ to $a$ and double
		- Since the curve is symmetric about the $y$-axis, we can save this effort.
		- $$V=\int_{x=-a}^{x=a}\pi(a^2-x^2)dx=2\int_{x=0}^{x=a}\pi(a^2-x^2)dx=2\big(\pi a^2x-\frac{x^3}{3}\big)\bigg|_{0}^{a}=\frac{4}{3}\pi a^3$$

# 🕹Quiz
## 📌Revolve an equilateral triangle
- 💬Question:
	- Find the volume $V$ of the solid obtained by revolving an equilateral triangle of side-length $a$ around one of its sides.
- ✏Solution:
	- Draw the picture:
		- ![name|200](../assets/images_app1_triangle.svg)
	- Identify the elements
		- thickness of the disk: $dx$
		- radius of the disk: $y$
		- area of the disk: $\pi y^2$
		- limit: $[0, \frac{a}{2}]$, because it is symmetric and therefore it could be double.
	- The volume will be like
		- $$V = 2\int _0^{a/2} \pi y^2 \,  dx = 2\int _0^{a/2} \pi (x \sqrt{3})^2 dx = \frac{\pi a^3}{4}.$$


## 📌A witch’s cauldron
- 💬Question:
	- what is the volume of the cauldron?
	- $y = x^2$ rotated around the $y$-axis.
	- ![name|200](../assets/revolve_x2.png)
- 🏹Strategy:
	- Think about what is the radius?
	- Think about what is the thickness?
- ✏Solution:
	- The area of the disk is $\pi x^2$ in the following figure.
	- ![name|200](../assets/revolve_x2_disk.png)
	- The disk has thickness $dy$ and volume $dV=\pi x2dy$.
	- Then the volume is
		- $$\begin{align}V &= \int_0^a\pi x^2 dy \quad(\text{ substitute}\space y = x^2)\\V&=\int_0^a\pi ydy=\pi\frac{y^2}{2}\bigg|_0^2=\frac{\pi a^2}{2}\end{align}$$

