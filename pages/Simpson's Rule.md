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
