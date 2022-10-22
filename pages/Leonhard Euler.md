alias:: Euler

# Euler Characteristic
id:: 634e3b2d-a1b3-4803-9236-d18373f2c133
	- 📝Definition
		- Definition 1
			- Let a closed surface have genus $g$. Then the polyhedral formula generalizes to the [Poincaré formula](https://mathworld.wolfram.com/PoincareFormula.html)
				- $$
				  \chi(g)=V-E+F, 
				  $$
			- where $\chi(g)=2-2g$ is the Euler characteristic, sometimes also known as the Euler-Poincaré characteristic. The [polyhedral formula](https://mathworld.wolfram.com/PolyhedralFormula.html) corresponds to the special case $g=0$
			- > ==**Note⚠**==: Assuming no _unreferenced_ vertices in $V$, each of the quantities in the right-hand side can be determined from $F$ alone. This indicates that its a purely topological property. Changing the geometric positions (i.e., changing the vertex positions in $V$) will not affect the Euler Characteristic. Due to this, we say that the Euler Characteristic is a ***topological invariant***.
		- Definition 2
			- The algebraic relationship between the number of vertices, edges and faces reveals the topological _genus_ of the surface via the _Euler Characteristic_
				- $$
				  \chi= 2c - 2h - b
				  $$
			- where $c$ is the number of connected components, $h$ is number of holes (as in donut), and $b$ is the number of connected components of the boundary of the surface.
	- 🐍Algorithm
		- 🔗Link: [Euler characteristics](https://github.com/XingxinHE/Junior-SofwareEngineer-Notes/tree/main/code/GeometryProcessing/csc2520_jacobson/geometry-processing-introduction)
		- 🏹Strategy - 1
			- This is my personal implementation.
			- 1️⃣Find the distinct edges from faces matrix $F$ using `std::set`. See [here](https://github.com/XingxinHE/Junior-SofwareEngineer-Notes/blob/main/code/GeometryProcessing/csc2520_jacobson/geometry-processing-introduction/src/edges.cpp).
			- 2️⃣Compute the Euler characteristics $V-E+F$. See [here](https://github.com/XingxinHE/Junior-SofwareEngineer-Notes/blob/main/code/GeometryProcessing/csc2520_jacobson/geometry-processing-introduction/src/euler_characteristic.cpp).
		- 🏹Strategy - 2
			- .
		- Result
			- Time of my algorithm: 5450994, Time of libigl: 84153
	- ⌨Sample Code
		- Code fragments
- # Euler's Method
	- ## 📝Definition
		- Given the differential equation :
			- $$
			  \frac{dy}{dx}=x+y
			  $$
		- Euler's method as Solution:
			- 1.Choose a step size $h$ (The smaller the step size, the more accurate the approximation.)
			- 2.Let $(x_0,y_0)$ be the initial condition.
			- 3.We can use the differential equation and step size to determine the value of the function at $x_1=x+h$:
				- $$
				  \begin{align}
				  x_1 &= x_0+h\\
				  y_1 &= y_0+(x_0+y_0)h\quad\text{linear approximation}
				  \end{align}
				  $$
			- 4.Iterate this process:
				- $$
				  \begin{align}
				  x_{k+1} &= x_k+h\\
				  y_{k+1} &= y_k+(x_k+y_k)h\quad\text{linear approximation}
				  \end{align}
				  $$
	- ## 📈Diagram
		- ![name](../assets/euler_method_example.png){:height 300, :width 500}
		- The preceding diagram shows the intuition of Euler method. You can try it [here](https://mathlets.org/mathlets/eulers-method/).
	- ## 🧠Intuition
		- A) Iterative process
		- B) Step size matter
		- C) Approximation is never perfect
	- ## 🗃Example
		- 📌An example using Euler's Method
			- Question:
				- Consider the differential equation $\frac{dy}{dx}=x+y$. Find the linear approximation for the solution function $f(x)$ that passes through the point $(0,1)$.
			- Thinking:
				- We don't know what this function is, but we do know a value of the function, as well as a value of the derivative, so we can use a [[Linear Approximation]]!
			- Solution:
				- Step 1, linear approximation
					- The linear approximation takes the form
					- $$
					  \begin{align}
					  f(x)&\approx f(0)+f'(0)x\\
					  &=1+\frac{dy}{dx}\bigg|_{(0,1)}x
					  1+x\end{align}
					  $$
				- Step 2, iterative process
					- We can use the result from last step to approximate when $x=0.1$.
						- $$
						  f(0.1)\approx1+0.1\approx1.1
						  $$
						- $$
						  \frac{dy}{dx}\bigg|_{(0.1,1.1)}=1.2
						  $$
					- We can use the result from last step to approximate when $x=0.2$.
						- $$
						  \begin{align}
						  f(x)& \approx f(0.1) + f'(0.1)(x-0.1)\\
						  &=1.1+1.2(x-0.1)
						  \end{align}
						  $$
						- $$
						  f(0.2)\approx1.1+1.2(0.1)=1.22
						  $$
				- keep going...