alias:: FTC2

- # 📝Definition
	- Given a continuous function $f(x)$, if
		- $$
		  \displaystyle G(x)=\int _{a}^{x} f(t)\, dt \qquad (\, \, t\, \, \text{between}\, \, a\, \, \text{and}\,  x),
		  $$
	- then
		- $$
		  G'(x)=f(x).
		  $$
	- Geometrically, $G(x)$ is the area between $a$ and $x$. This area varies as $x$ varies.
		- ![name](../assets/images_ftc2_G.svg){:height 200, :width 300}
- # 🎯Intent
	- 📌In terms of [[Differential Equation]]s,
		- FTC2 says that $G(x)$ is the solution to the following differential equation and initial condition:
			- $$
			  \begin{align}
			  y'&=f\quad\quad\text{differential equation}\\
			  y(a)&=0\quad\quad\text{initial condition}
			  \end{align}
			  $$
			- The initial condition $y(a)=0$ is satisfied because $\, \, \displaystyle G(a)=\int _{a}^{a} f(t)\, dt = 0$
		- Hence, FTC2 gives us a formula for an [[Antiderivative]] of $f(x)$. This formula is different from the formulas you have seen. It is in terms of a [[definite integral]], and is called an integral formula.
		- **==Note:==** The integrand $f(x)$ can be any [[Continuous]] function, not just the ones whose antiderivative we know how to find. These integral formulas are still useful there are numerical methods that allow us to compute them.
- # 🗃Example
	- 📌simple example of FTC2
		- Give the solution to the differential equation and initial condition below in terms of an integral.
			- $$
			  \begin{align}
			  H'(x)&=x^2\\ H(0)&=0
			  \end{align}
			  $$
		- Applying the FTC2 directly gives
			- $$
			  \begin{align}
			  H(x)= \int _{0}^{x} t^2\, dt
			  \end{align}
			  $$