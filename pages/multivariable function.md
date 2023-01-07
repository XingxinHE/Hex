---
aliases: [function of 2 variables, function of 3 variables]
tags:
  - function
  - mathematics
---


# 📝Definition

## 📄multivariable function
A function is called **multivariable** if its [[domain|input]] is made up of multiple numbers.
$$
f(\underbrace{x,y}_{})=x^2y
$$
## 📑function of 2 variables
A function of 2 variables, defined on the domain $D$ in the [[plane]], is a rule $f$ that associates with each point $(x, y)$ in $D$ a unique real number, denoted by
$$
f (x, y).
$$

## 📑function of 2 variables(rigorous)
A function $f$ of 2 variables is a rule that assigns to each ordered pair of real numbers $(x,y)$ in a set $D$ a unique real number denoted by
$$
f (x, y).
$$
The set $D$ is the [[domain]] of $f$ and its [[range]] is the set of values that $f$ takes on, that is
$$
\left\{f(x,y) | (x,y)\in D \right\}.
$$
![|400](../assets/func_2_variables.svg)

## 📃function of 3 variables
A function of 3 variables, defined on the domain $D$ in space, is a rule $f$ that associates with each point $(x, y, z)$ in $D$ a unique real number, denoted by
$$
f (x, y, z).
$$


___
The relationship between domain and range is represented as set. More formally, it is [[level set]].


# 🧠Intuition
The [[domain]](input) of function has multiple numbers.

# 🌓Complement
[[vector-valued function]]

## 🌔"multivariable function" vs. "vector-valued function"
- multivariable function - emphasizes the inputs are multiple numbers.
- vector-valued function - emphasizes the output are multiple numbers.

> [!info] Remark
> These 2 are super important!

# ⚖Theorem
## Properties of Limits of Functions of Two Variables
The following rules hold if $L, M$, and $k$ are real numbers and we have 2 functions
$$
\lim_{(x,y)\to(x_0,y_0)}f(x,y)=L\quad\text{and}\quad\lim_{(x,y)\to(x_0,y_0)}g(x,y)=M.
$$
- 1️⃣ sum rule: $$\lim_{(x,y)\to(x_0,y_0)}(f(x,y)+g(x,y))=L+M$$
- 2️⃣ Difference Rule: $$\lim_{(x,y)\to(x_0,y_0)}(f(x,y)-g(x,y))=L-M$$
- 3️⃣ Constant Multiple Rule: $$\lim_{(x,y)\to(x_0,y_0)}kf(x,y)=kL$$
	- any number $k$
- 4️⃣ Product Rule: $$\lim_{(x,y)\to(x_0,y_0)}(f(x,y)\cdot g(x,y))=L\cdot M$$
- 5️⃣ Quotient Rule: $$\lim_{(x,y)\to(x_0,y_0)}\frac{f(x,y)}{g(x,y)}=\frac{L}{M},\quad M\neq0$$
- 6️⃣ Power Rule: $$\lim_{(x,y)\to(x_0,y_0)}[f(x,y)]^n=L^n$$
	- $n$ is a positive integer
- 7️⃣ Root Rule: $$\lim_{(x,y)\to(x_0,y_0)}\sqrt[n]{f(x,y)}=\sqrt[n]{L}=L^{1/n}$$
	- $n$ a positive integer, and if $n$ is even, we assume that $L > 0$.





# 🌈Properties
## 🔴limit
### 📝Definition
We say that a function $f(x, y)$ approaches the [[limit]] $L$ as $(x, y)$ approaches $(x_0,y_0)$, and write
$$
\lim_{(x,y)\to(x_0,y_0)}f(x,y)=L
$$
if, for every number $\epsilon>0$, there exists a corresponding number $\delta>0$ such that for all $(x,y)$ in the [[domain]] of $f$,
$$
\lvert f(x,y)-L<\epsilon\rvert\quad\text{whenever}\quad 0<\sqrt{(x-x_0)^2+(y-y_0)^2}<\delta.
$$

### 🧠Intuition
The definition of limit says that the distance between $f(x, y)$ and $L$ becomes arbitrarily small whenever the distance from $(x, y)$ to $(x_0, y0)$ is made sufficiently small (but not 0).
![|400](../assets/multivariable_function_limit.svg)

### 🗃Example
- 📁the limit of multivariable function example 1
	- ✏Solution:
		- $$\lim_{(x,y)\to(x_0,y_0)}f(x,y)=\lim_{(x,y)\to(0,1)}\frac{x-xy+3}{x^2y+5xy-y^3}=\frac{0-(0)(1)+3}{(0^2)(1)+5(0)(1)-(1)^3}=-3$$


- 📁the limit of multivariable function example 2
	- ✏Solution:
		- $$\lim_{(x,y)\to(x_0,y_0)}f(x,y)=\lim_{(x,y)\to(3,-4)}\sqrt{x^2+y^2}=\sqrt{(3)^2+(-4)^2}=5$$


## 🟠continuity
### 📝Definition
A function $f(x, y)$ is **[[continuity|continuous]] at the point** $(x_0 , y_0)$ if
1. $f$ is defined at $(x_0 , y_0)$
2. $\lim_{(x,y)\to(x_0,y_0)}f(x,y)$ exists
3. $\lim_{(x,y)\to(x_0,y_0)}f(x,y)=f(x_0,y_0)$
A function is continuous if it is continuous at every point of its [[domain]].

### 🗃Example
- 📁multivariable function continuous example 1
	- 💬Question: Where is the function $f(x,y)=\frac{x^2-y^2}{x^2+y^2}$ continuous?
	- 🗣Answer:
		- The function $f$ is discontinuous at $(0, 0)$ because it is not defined there.
		- Since $f$ is a rational function, it is continuous on its domain, which is the set $D=\{(x,y)|(x,y)\neq(0,0)\}$.
		- ![|200](../assets/not_continuous_multivariable_func.png)

- 📁multivariable function continuous example 2
	- 💬Question: Show that $$f(x,y)=\begin{cases}\frac{2xy}{x^2+y^2},&(x,y)\neq(0,0)\\0,&(x,y)=(0,0)\end{cases}$$ is continuous at every point except the origin.
	- ✏Solution:
		- When point $\neq(0,0)$
			- The function $f$ is continuous at any point $(x, y) \neq (0, 0)$ because its values are then given by a rational function of $x$ and $y$ and the limiting value is obtained by substituting the values of $x$ and $y$ into the functional expression.
		- At point $(0,0)$
			- the value of $f$ is defined, but $f$, we claim, has no limit as $(x, y) \to(0, 0)$. The reason is that different paths of approach to the origin can lead to different results, as we now see.
			- For every value of $m$, the function $f$ has a constant value on the “punctured” line $y = mx, x \neq 0$, because
				- $$f(x,y)|_{y=mx}=\frac{2xy}{x^2+y^2}|_{y=mx}=\frac{2x(mx)}{x^2+(mx)^2}=\frac{2mx^2}{x^2+m^2 x^2}=\frac{2m}{1+m^2}$$
			- Therefore, $f$ has this number as its limit as $(x, y)$ approaches $(0, 0)$ along the line:
				- $$\lim_{\begin{align}(x,y)\to(0,0)\\\text{along }y=mx\end{align}}f(x,y)=\lim_{(x,y)\to(0,0)}\left[f(x,y)|_{y=mx}\right]=\frac{2m}{1+m^2}$$
			- This limit changes with each value of the slope $m$. There is therefore no single number we may call the limit of $f$ as $(x, y)$ approaches the origin. The limit fails to exist, and the function is not continuous.
		- ![|200](../assets/not_continuous_multivariable_func1.png)



## 🟡differentiable
### 📝Definition
A function $z = f(x, y)$ is [[differentiable]] at $(x_0 , y_0)$ if $fx(x_0 , y_0)$ and $fy(x_0 , y_0)$ exist and $\Delta z$ satisfies an equation of the form
$$
\Delta z=f_x(x_0 , y_0)\Delta x+f_y(x_0 , y_0)\Delta y+\epsilon_1\Delta x+\epsilon_2\Delta y
$$
in which each $\epsilon_1,\epsilon_2\to0$ as both $\Delta x,\Delta y\to0$. We call $f$ differentiable if it is differentiable at every point in its [[domain]], and say that its graph is a smooth [[surface]].

> [!info] Remark
> $f_x$ denotes the [[partial derivative]] with respect to the variable $x$
> $f_y$ denotes the [[partial derivative]] with respect to the variable $y$

🟢
🔵
🟣



# 🎨Representation
> [!info] Remark
> This section describe how to "graph" these multivariable functions.

> [!tip] typical graphing problem
> ![\|400](../assets/graph_multivariable_function.png)



## Functions of 2 Variables
There are ==**2**== standard ways to picture the values of a function $f(x, y)$.
- 1️⃣One is to draw and label curves in the domain on which $f$ has a constant value. (a.k.a. [[level curve]])
- 2️⃣The other is to sketch the [[surface]] $z = f(x, y)$ in space.



## Functions of 3 Variables


# 🗃Example
- 📁analyze domain and range of multivariable function example
	- 💬Question: For each of the following functions, evaluate $f(3, 2)$ and find and sketch the domain.
		- $f(x,y)=\frac{\sqrt{x+y+1}}{x-1}$
		- $f(x,y)=x\ln(y^2-x)$
	- ✏Solution:
		- for $f(x,y)=\frac{\sqrt{x+y+1}}{x-1}$
			- $f(3,2)=\frac{\sqrt{x+y+1}}{x-1}=\frac{\sqrt{3+2+1}}{3-1}={\sqrt{6}\over2}$
			- The expression for $f$ makes sense if the denominator is not 0 and the quantity under the square root sign is nonnegative. So the domain of $f$ is
				- $$D=\{(x,y)|x+y+1\geq0,x\neq1\}$$
			- The inequality $x + y + 1 \geq 0$, or $y \geq -x- 1$, describes the points that lie on or above the line $y = − x- 1$, while $x \neq 1$ means that the points on the line $x = 1$ must be excluded from the domain.
			- ![|200](../assets/multivariable_functions_domain.svg)
		- for $f(x,y)=x\ln(y^2-x)$
			- $f(3,2)=3\ln(2^2-3)=0$
			- Since $(y^2-x)$ lies in logarithm and therefore $(y^2-x)>0$. that is, $x < y^2$, the domain of $f$ is
				- $$D=\{(x,y)|x<y^2\}$$
			- ![|200](../assets/multivariable_functions_domain2.svg)


- 📁graph multivariable function example
	- 💬Question: Graph $f(x, y) = 100 - x^2 - y^2$ and plot the level curves $f(x, y) = 0, f(x, y) = 51$, and $f(x, y) = 75$ in the domain of $f$ in the plane.
	- ✏Solution:
		- domain
			- The domain of $f(x,y)$ is the whole $xy$-plane.
		- range
			- The range of $f(x,y)$ is the the set of real numbers $\leq100$.
		- level curve $f(x, y) = 0$
			- The level curve $f(x, y) = 0$ is the set of points in the $xy$-plane at which
				- $f(x,y)=0=100-x^2-y^2\quad\text{or}\quad x^2+y^2=100$
				- which is the circle of radius 10 centered at the origin.
		- level curve $f(x, y) = 51$
			- $f(x,y)=51=100-x^2-y^2\quad\text{or}\quad x^2+y^2=49$
		- level curve $f(x, y) = 75$
			- $f(x,y)=75=100-x^2-y^2\quad\text{or}\quad x^2+y^2=25$
		- diagram
			- ![|300](../assets/graph_a_2_variables_function.svg)
		- see the difference between [[contour curve]] and [[level curve]].
			- ![|200](../assets/contour_curve.svg)


# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized