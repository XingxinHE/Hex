---
aliases: [expected value, expectation value]
---


# 📝Definition
## mean
There are several statistical quantities called means.
| mean                      | value                                  | abbreviations |
| ------------------------- | -------------------------------------- | ------------- |
| harmonic mean             | $\frac{2ab}{a+b}$                      | H             |
| geometric mean            | $\sqrt{ab}$                            | G             |
| arithmetic-geometric mean | $\frac{(a+b)\pi}{4K(\frac{a-b}{a+b})}$ | AGM           |
| arithmetic mean           | $\frac{a+b}{2}$                        | A             |
| root-mean-square          | $\sqrt{\frac{a^2+b^2}{2}}$             | RMS           |

When applied to two elements $a$ and $b$ with $0<a\leq b$, these means satisfy
$$
H(a,b)\leq G(a,b)\leq AGM(a,b)\leq A(a,b)\leq RMS(a,b)
$$
> [!NOTE]
> Normally, we refer arithmetic mean as [[average]].

## Expected Value
Given a [[probability density function|probability distribution]] $p(x)$ such that
$$
\int _{-\infty }^{\infty } p(x)\,  dx =1
$$
, the expected value, $E$ , also known as the mean is defined by
$$
\int _{-\infty }^{\infty } x p(x)\,  dx
$$

> [!tip] Tip
> Note that the expected value is completely analogous to [[centroid|center of mass]]. Here we do not need to divide by the total integral of the probability distribution since the integral $\int _{-\infty }^{\infty } p(x)\,  dx$ is normalized to be equal to $1$.



# 🌱Related Elements
The following subjects are related to "mean."
- [[median]]
- [[mode]]
## [[mean]], [[median]], [[mode]]
The comparison is the following.
- mean: the sum of all values divided by the number of values
- median: the value in the middle of the ordered list of values
- mode: the value that occurs most frequently

# 🗃Example
- 📌Expected value 1
	- 💬Question:
		- Consider the exponential probability density function
			- $$p(t) =\begin{cases}  a e^{-a t}, &  \quad t\geq 0,\\ 0, &  t < 0 \end{cases}$$
			- where $a$ is a positive constant.
		- Question 1
			- Use [[definite integral#💫Operation#Substitution|change of variables]] to compute the expected value of $p(t)$.
		- Question 2
			- The **[[mode]]** is the value of $t$ at which the maximum of the probability density function is achieved. What is the mode of the distribution $p(t)$?
	- 🏹Strategy:
		- tips on the [[antiderivative]] of $te^{-t}$ is
			- $$\int te^{-t}\,  dt = -(1+t)e^{-t} +C.$$
	- ✏Solution:
		- Solution on question 1
			- From the equation of expected value, we have
				- $$E=\int _{-\infty }^{\infty }t\cdot p(t)\, dt$$
			- Since the [[domain]] of $p(t)$ is split into $[-\infty, 0], [0, \infty]$, therefore
				- $$E=\int _{-\infty }^{\infty }t\cdot p(t)\, dt=\int _{-\infty }^{0}t\cdot p(t)+\int _{0}^{\infty }t\cdot p(t)=0+\int _{0}^{\infty }t\cdot p(t)$$
			- Let $u=at$, then $du=adt$
				- $$\begin{align}E=\int _{-\infty }^{\infty }t\cdot p(t)\, dt&=\int _{0}^{\infty } t\left( a e^{-a t}\right) \, dt\\&=\int _{0}^{\infty } \frac{u}{a} \left( a e^{-u}\right)\, \frac{du}{a}\\&=\left. \frac{1}{a}\left(-(1+u)e^{-u}\right) \, \right|_{0}^{\infty }\\&=\frac{1}{a}\end{align}$$
		- Solution on question 2
			- First think about what is [[mode]].
				- The mode, or the value of $t$ for the most likely outcome, is the value of $t$ where $a e^{-a t}$ attains its maximum.
			- Then think about is it increasing or decreasing
				- Since $p(t)$ is $0$ for $t<0$ and is strictly decreasing and positive for $t\geq0$, the maximum is at $t=0$.



> [!tips] Tips
> Expected values and exponential distribution is closely related. Here are 2 examples:
> - [[exponential distribution#^ac60dc]]
> - [[exponential distribution#^8ec66b]]
