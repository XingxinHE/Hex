# 📝Definition
In calculus, the trapezoidal rule is a technique for approximating the [[definite integral]].

# ✒Formula
To approximate the integral
$$
\begin{align}
\int _a^b f(x)\, dx
\end{align}
$$
- Subdivide the interval into $n$ pieces $a = x_0 < x_1 < \dotsb < x_{n-1} < x_n = b$.
- Let $y_0 = f(x_0), y_1 = f(x_1),...,y_{n-1} = f(x_{n-1}), y_n = f(x_n)$
- $\Delta x = \displaystyle \frac{b-a}{n}$
Then we have:
$$
\int _a^b f(x)\, dx \approx \Delta x\left( \frac12 y_0 + y_1 + \dotsb + y_{n-1} + \frac12 y_n \right).
$$

# ⛈Characteristics / Properties
Suppose $\left| f^{\prime \prime }(x) \right| \leq M$ for $a \leq x \leq b$. Then the error of the Trapezoidal Rule over $n$ subintervals is given by
$$
\left| E_T \right| \leq \frac{M(b-a)^3}{12n^2}.
$$

# 🧬Related Elements
![[Riemann sums#Trapezoidal Rule vs. Midpoint]]


# 🗃Example
![[Riemann sums#^d0153c]]

# 🕹Quiz
- 📌3A (19)
	- 💬Question: Use the trapezoidal rule to estimate $\sqrt{1}+\sqrt{2}+\sqrt{3}+\cdots +\sqrt{9,999} + \sqrt{10,000}$
	- 🏹Strategy: The key is to think about the equation and the integration.
	- ✏Solution:
		- Let the sum expressed as
			- $$S=\sqrt{1}+\sqrt{2}+...+\sqrt{10,000}$$
		- Intuitive guess of the integration is
			- $$\int _{0}^{10^4}\sqrt{x}dx$$
		- Expand the integration using trapezoidal rule
			- $$\int _{0}^{10^4}\sqrt{x}dx \approx \frac1{2}\sqrt{0}+\sqrt{1}+...+\frac1{2}\sqrt{10^4}$$
		- We find that if we compensate a $\frac{1}{2}\sqrt{10^4}-\frac{1}{2}\sqrt{10^4}$, the equation can be rearranged!
			- $$\begin{align}\int _{0}^{10^4}\sqrt{x}dx &\approx \frac1{2}\sqrt{0}+\sqrt{1}+...+\frac1{2}\sqrt{10^4}\\&\approx\frac1{2}\sqrt{0}+\sqrt{1}+...+\frac1{2}\sqrt{10^4}+\frac{1}{2}\sqrt{10^4}-\frac{1}{2}\sqrt{10^4}\\&\approx \frac1{2}\sqrt{0}+\underbrace{\sqrt{1}+...+\sqrt{10^4}}_{S}-\frac{1}{2}\sqrt{10^4}\\&\approx S-\frac1{2}\sqrt{10^4}\end{align}$$
		- But
			- $$\left. \displaystyle \int _{0}^{10^4} \sqrt{x}dx=\frac2{3}x^{3/2}\right|_{0}^{10^4}=\frac2{3}\cdot 10^6$$
		- From the equation above,
			- $$\frac2{3}\cdot 10^6 \approx S-50$$
		- Hence $S \approx 666,717$

