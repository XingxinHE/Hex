- # 📝Definition
	- Geometric definition
		- The definite integral of $f$ from $a$ to $b$, denoted by
			- $$
			  \int_{a}^{b}f(x)dx
			  $$
		- is the area of the region above the $x$-axis, below the curve $y=f(x)$, and in between the two vertical lines $x=a$ and $x=b$, as shown shaded in the figure below.
			- ![name](../assets/images_defint_riemann4.svg){:height 200, :width 200}
- # 🧪Composition
	- Lower limit of the integral
		- the $x$-value $a$
	- Upper limit of the integral
		- the $x$-value $b$
	- This is a different sense of the word “[[Limit]]" from when we take the limit of a function.
- # 🌓Complement
	- ## 📌 [[Indefinite Integral]] vs. Definite Integral
	  id:: 1de28d3e-6db2-4bb3-b8fa-36e73d2b03d6
		- |                         | Definite Integral      | Indefinite Integral                                          |
		  | ----------------------- | ---------------------- | ------------------------------------------------------------ |
		  | Start Point & End Point | Well-defined Points    | No Points                                                    |
		  | Symbol(same)            | $\int$                 | $\int$                                                       |
		  | Definition(different)   | the area under a curve | the operation that reverses differentiation, the antiderivative |
		  | Compute Method          | Riemann Sum            |                                                              |
		- ⭐That's where [[First Fundamental Theorem of Calculus]] comes in. It gives a precise connection between the two versions of the integral. It tells us we don't need to evaluate limits of Riemann sums in definite integral, instead we only need to find antiderivatives.
- # ⛈Properties
	- Sums
		- $$
		  \int _{a}^{b}\left( f(x) +g(x) \right) \, dx \, =\,  \int _{a}^{b} f(x)\, dx +\int _{a}^{b} g(x) \, dx
		  $$
	- Constant Multiples
		- $$
		  \int _{a}^{b} c \, f(x) \, dx \, =\,  c\, \int _{a}^{b} f(x)\, dx\qquad \text{for any constant}\, c
		  $$
	- Same Upper and Lower Limits
		- $$
		  \int _{a}^{a} \, f(x) \, dx\, =\, 0
		  $$
	- Reversing Limits of Integrals
		- $$
		  \int _{b}^{a} \, f(x) \, dx\, =\, - \int _{a}^{b} \, f(x) \, dx\qquad \text{for any}\,  a,b
		  $$
		- This is the definition of a definite integral with its lower limit greater than its upper limit. It is defined this way to be consistent with FTC1.
	- Combining integrals
		- $$
		  \int _{a}^{c} \, f(x) \, dx\, =\, \int _{a}^{b} \, f(x) \, dx\, +\, \int _{b}^{c} \, f(x) \, dx\qquad \text{for any}\,  a,b,c
		  $$
- # 💫Operation
	- ## Estimation
		- If $\, f(x)\leq g(x)$, and $a\leq b$ then
			- $$
			  \displaystyle \int _{a}^{b} f(x)\,  dx\, \,  \, \leq \, \, \,  \int _{a}^{b} g(x)\,  dx \qquad (\text{for}\, \,  a\leq b).
			  $$
		- Notice that the order of $a$ and $b$ matters for this inequality. If instead of $a\leq b$ we have $a\geq b$, then
			- $$
			  \displaystyle \int _{a}^{b} f(x)\,  dx\,  \geq \,  \int _{a}^{b} g(x)\,  dx \qquad (b\leq a).
			  $$
		- Summary
			- In other words, if the [[Limit]]s of the integrals are reversed, the inequality is also reversed.
	- ## Substitution
		- 📝Definition
			- If
				- $$
				  \displaystyle \int _{a}^{b} f(x)\,  dx = \int _{a}^{b} g(u(x)) u'(x) \, dx,
				  $$
			- and $u'$ **does not change sign** between $a$ and $b$, then
				- $$
				  \displaystyle \int _{a}^{b} f(x)\,  dx = \int _{a}^{b} g(u(x)) u'(x) \, dx = \int _{u(a)}^{u(b)} g(u) \, du.
				  $$
		- 🧠Intuition
			- The limits of the integral over $u$ are the values of $u$ corresponding to the limits of the integral over $x$.
- # 🕳Pitfalls
	- 📌Caution on substitution
		- When we use the method of substitution, we need to be very careful about when $u'$ (or $du$) changes sign. If $u'$ changes sign within the integration interval $[a,b]$, the method of substitution may give the wrong answer. In this case, we need to first rewrite the integral as a sum of two integrals such that within the limits of each integral $u'$ does not change sign, and then use the method of substitution on each integral separately.
- # 🗃Example
	- 📌Estimating the integral
		- Giving the following graph
			- ![name](../assets/images_defint_aunderparabolanotriangle.svg){:height 200, :width 200}
		- Question
			- By only looking at the graph of $y=x^2$, decide which of the following are greater than $\displaystyle \int _0^b \,  x^2 \,  dx\,$ for every $b>0$? (Check all that apply.)
		- Answer
			- $0$
			- $3$
			- $b^3$✅
			- $b^3/2$✅
		- Solution
			- Draw a graph
				- ![name](../assets/images_defint_aunderparabola.svg){:height 200, :width 200}
			- Identify the geometries
				- Area of shaded region under parabola (this is the ==definite integral==) $\int _0^b \,  x^2 \,  dx$
				- Area of shaded triangle $\frac{1}{2}b\cdot b^2=\frac{b^3}{2}$
				- Area of rectangle $b\cdot b^2=b^3$
			- Identify the inequalities
				- Area of shaded region under parabola < Area of shaded triangle < Area of rectangle
			- Therefore we have that results.
	- 📌Definite integral of Piecewise linear functions
		- Given the graph of $y=f(x)$ below.
			- ![name](../assets/images_defint_areaunderpiecewiselinearnoshade.svg){:height 200, :width 200}
		- By inspection, the shaded region covers $5$ unit squares
			- $$
			  \displaystyle \int _0^3 \,  f(x)\,  dx=5
			  $$
		- Result
			- ![name](../assets/images_defint_areaunderpiecewiselinear.svg){:height 200, :width 200}