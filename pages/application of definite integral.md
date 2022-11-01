https://ocw.mit.edu/courses/18-01-single-variable-calculus-fall-2006/resources/lec21/
https://ocw.mit.edu/courses/18-01-single-variable-calculus-fall-2006/resources/lec22/

# Areas between two curves
## 📝Definition
This is a classifc application using [[definite integral]] and [[First Fundamental Theorem of Calculus|FTC1]].
$$
A = \int_a^b(f(x)-g(x))dx
$$
![[Finding the area between two curves.png]]

## 🗃Example
### 📌Example 1
- 💬Question: Find the area in the region between $x = y^2$ and $y = x − 2$.
	- ![name|150x150](../assets/area_between_2_curves.svg)
- 🏹Strategy: Generally, there are 2 ways of solving this question.
	- Hard Way: Vertical Slices
	- Easy Way: Horizontal Slices
- ✏Solution: 
	- General setup
		- First, solving the equations
			- $$\begin{align}y+2&=x=y^2\\y^2-y-2&=0\\(y − 2)(y + 1)&=0\end{align}$$
			- Crossing points at $y = −1, 2$. Plug these back in to find the associated $x$ values, $x = 1$ and $x = 4$.Thus the curves meet at $(1,−1)$ and $(4, 2)$
		- Second, graph these functions and find the crossing points
			- ![name](../assets/area_between_2_curves.png)
	- Hard Way: Vertical Slices
		- If we slice the region between the two curves vertically, we need to consider two different regions.
		- ![name](../assets/Vertical_Slices.png)
		- 
