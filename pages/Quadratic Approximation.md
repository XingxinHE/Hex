- ## 📝Definition
	- The quadratic approximation near $x=a$ is **the best fit parabola** to $f$ at the point $x=a$.
	- The formula for the quadratic approximation of a function $f$ near a point $x=a$ is
		- $$
		  f(x)\approx f(a)+f'(a)(x-a)+\frac{f''(a)}{2}(x-a)^2
		  $$
	- When $a=0$, this quadratic approximation becomes
		- $$
		  f(x)\approx f(0)+f'(0)(x)+\frac{f''(0)}{2}(x)^2
		  $$
- ## 🧮Expression
	- 📌Quadratic approximation of basic functions
		- $(1+x)^r$ near $x=0$
		  $$
		  1+rx+\frac{r(r-1)}{2}x^2+O(x^3)
		  $$
		- $\sin{(x)}$ near $x=0$
		  $$
		  x+O(x^3)
		  $$
		- $\cos{(x)}$ near $x=0$
		  $$
		  1-\frac{x^2}{2}+O(x^3)
		  $$
		- $e^x$ near $x=0$
		  $$
		  1+x+\frac{x^2}{2}+O(x^3)
		  $$
		- $\ln{(1+x)}$ near $x=0$
		  $$
		  x-\frac{x^2}{2}+O(x^3)
		  $$
- # 🧬Related Elements
	- {{embed ((ea90b1d5-b3bd-420b-bb60-0ce4c686c9de))}}
- # 🗃Example
	- {{embed ((6343928b-dd01-4e0a-8586-de4ac2f9cf7e))}}