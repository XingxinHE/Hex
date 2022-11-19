# 📝Definition
Simpson's rule is a Newton-Cotes formula for approximating the [[definite integral]] of a function $f$ using quadratic polynomials (i.e., parabolic arcs instead of the straight line segments used in the trapezoidal rule). 

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
\int _a^b f(x)\, dx \approx \frac{\Delta x}{3} \left( y_0 + 4y_1 + 2y_2 + 4 y_3 + \dotsb +2y_{n-2} + 4y_{n-1} + y_n \right)
$$
# ⛈Characteristics / Properties
Suppose $\left| f^{(4)}(x) \right| \leq M$ for $a \leq x \leq b$. Then the error of the Simpson's Rule over $n$ subintervals is given by
$$
\left| E_S \right| \leq \frac{M(b-a)^5}{180n^4}.
$$

# 🗃Example
![[Riemann sums#^d0153c]]

- 📌Practice with probability using Simpson's Rule
	- 💬Question:
		- In the United States, the average height of a woman is 64 inches with a standard deviation of 3 inches. Thus the probability density function is given by $$f(x) = \frac{1}{3 \sqrt{2\pi }} e^{-\frac{(x-64)^2}{18}}$$
		- Use Simpson's rule to estimate the probability that a woman is between 64 and 68 inches tall with $n=4$.
	- 🏹Strategy: Recall the [[probability density function]].
	- ✏Solution:
		- The probability can be written as
			- $$\large { P(64 < x < 68) = \int _{64}^{68} \frac{1}{3 \sqrt{2\pi }} e^{-\frac{(x-64)^2}{18}} \,  dx}.$$
		- Appealing to Simpson's rule, we have
			- $$\Delta x = \displaystyle \frac{68-64}{4} = 1.$$
		- Then we have
			- $$\begin{align}P(64 < x < 68)&\approx\frac{\Delta x}{3}\left(y_0 + 4y_1 + 2y_2 + 4y_3 + y_4\right)\\&=\frac{1}{9 \sqrt{2\pi }} \left(1+ 4e^{-\frac{1}{18}}+2e^{-\frac{2}{9}}+4e^{-\frac{1}{2}}+e^{-\frac{16}{18}} \right) \approx 0.41 .\end{align}$$
		- If the normal distribution is an accurate description of the distribution of heights, this means that $41\%$ of women in the US are between 64 and 68 inches tall.

