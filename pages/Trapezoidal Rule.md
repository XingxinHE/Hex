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
