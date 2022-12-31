---
aliases: []
tags:
  - mathematics
  - geometry
---


# 📝Definition

# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
- 📁line plane intersection example 1
	- 💬Question: Find the point where the line and plane intersects.
		- Line:   $x = \frac{8}{3} + 2t,\quad y = -2t,\quad z = 1 + t$
		- Plane:   $3x + 2y + 6z = 6.$
	- 🏹Strategy: Since the point is the intersection, it must be satisfied in both equation! Therefore just plug the line into plane!
	- ✏Solution:
		- $$\begin{align}3x + 2y + 6z &= 6\\3(\frac{8}{3} + 2t) + 2(-2t) + 6(1 + t) &= 6\\8 + 6t - 4t + 6 + 6t &= 6\\t &= -1.\end{align}$$
		- The point of intersection is
			- $(x, y, z)|_{t=-1} = \left(\frac{8}{3} - 2, 2, 1 - 1\right) = \left(\frac{2}{3}, 2, 0\right)$


​
# 🧀Applicability

🍞
🥐
🥖
🥨
🥯
🥞
## 🧇Computer Graphics
Sometimes we want to know where a line and a plane intersect. For example, if we are looking at a flat plate and a line segment passes through it, we may be interested in knowing what portion of the line segment is hidden from our view by the plate. This application is used in #ComputerGraphics  . e.g. [[ray-object intersections]]

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized