# 🧾 Cheat Sheet
$$
\begin{align}
(1)&\log_n(0) = \text{Undefined}\\
(2)&\log_n(1) = 0\\
(3)&\log_n(n) = 1\\
(4)&\log_n(n^x) = x\\
(5)&n^{\log_n(x)} = x\\
(6)&\log_n(x^r) = r\log_n(x) \neq \log_n^r(x) = (\log_n(x))^r\\
(7)&\log_n(xy) = \log_n(x) + \log_n(y)\\
(8)&\log_n\left(\frac{x}{y}\right) = \log_n(x) - \log_n(y)\\
(9)&-\log_n(x) = \log_n\left(\frac{1}{x}\right)\\
(10)&\frac{\log(x)}{\log(n)} = \log_n(x)\\
\end{align}
$$


# 📝Definition
- The logarithm $\log_bx$ for a base $b$ and a number $x$ is defined to be the [[function#^a7ed31bf0b55411a|inverse function]] of taking $b$ to the power $x$, i.e., $b^x$. Therefore, for any $x$ and $b$,
- $$
x=\log_b(b^x)
$$

- or equivalently,
- $$
x=b^{\log_b(b^x)}
$$
        
# 📈Diagram
- ![name](../assets/Logarithm_900.svg)

# ⛈Characteristics / Properties
📌 [[singularity]]
For any base, the logarithm function has a singularity at $x=0$.

# 🌓Complement
[[exponential function|exponential]]

# 👑Importance
Logarithm is very important in [[Calculus]].