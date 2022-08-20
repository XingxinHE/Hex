alias:: Euler

- # Euler's Method
	- Given the differential equation :
		- $$
		  \frac{dy}{dx}=x+y
		  $$
	- Solution:
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