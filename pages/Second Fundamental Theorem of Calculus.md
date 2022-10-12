alias:: FTC2

- # 📝Definition
	- Given a continuous function $f(x)$, if
		- $$
		  \displaystyle G(x)=\int _{a}^{x} f(t)\, dt \qquad (\, \, t\, \, \text{between}\, \, a\, \, \text{and}\,  x),
		  $$
	- then
		- $$
		  G'(x)=f(x)\quad\text{or}\quad \frac{d}{dx}\int _{a}^{x} f(t)\, dt=f(x)
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
- # 🧠Intuition
	- ![name](../assets/distance_velocity_FTC.png){:height 200, :width 400}
	- Since $s(T)=\int _{0}^{T} v(t)\, dt$, therefore, if we take the [[Derivative]] of the distance function $s(T)$, we can get the velocity function $v(t)$.
	- $$
	  \begin{align}
	  \frac{d}{dT}s(T)&=\frac{d}{dT}\int _{0}^{T} v(t)\, dt\\
	  v(T)&=\frac{d}{dT}\int _{0}^{T} v(t)\, dt
	  \end{align}
	  $$
- # 🌓Complement
	- [[FTC1]]
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
	- 📌example using FTC2
		- 💬Question: Assume $f$ is continuous, if $\int_0^x f(t)dt=x^2\sin(\pi x)$. Find $f(2)$.
		- ✏Solution:
			- FTC2 implies
				- $$
				  \frac{d}{dx}\int_0^x f(t)dt=f(x)
				  $$
			- Then we have
				- $$
				  \begin{align}
				  \frac{d}{dx}\int_0^x f(t)dt&=f(x)\\
				  \frac{d}{dx}\int_0^x f(t)dt&=f(x)=\bigg(x^2\sin(\pi x\bigg)'\\
				  f(x)&=2x\sin\pi x+x^2\cos(\pi x)\cdot\pi\\
				  f(2)&=4\sin(2\pi)+4\pi\cos(2\pi)\\
				  f(2)&=4\pi
				  \end{align}
				  $$
	- 📌example using FTC2 with [[Quadratic Approximation]]
		- 💬Question: Let $F(x)=\int_0^x f(t)dt$. Find the quadratic approximation for $F(x)$ near $x=0$ in terms of $f$. What assumption do we have to make about $f$?
		- ✏Solution
			- 1️⃣Write what is quadratic approximation of $F(x)$ at $x=0$
				- $$
				  F(x)\approx F(0)+F'(0)x+\frac{F''(0)}{2}x^2
				  $$
			- 2️⃣Solve each component
				- $$
				  \begin{align}
				  F(0)&=\int_0^0f(t)dt=0\\
				  F'(x)&=\frac{d}{dx}\int_0^x f(t)dt=f(x)\\
				  F'(0)&=f(0)\\
				  F''(x)&=\frac{d}{dx}f(x)=f'(x)\\
				  F''(0)&=f'(0)
				  \end{align}
				  $$
			- 3️⃣Plug all components
				- $$
				  F(x)\approx 0+f(0)\cdot x+\frac{f'(0)}{2}\cdot x^2=f(0)x+\frac{f'(0)}{2}\cdot x^2
				  $$
			- 4️⃣So the assumption is that $f$ must be [[Continuous]] and [[differentiable]] at least near $x=0$.