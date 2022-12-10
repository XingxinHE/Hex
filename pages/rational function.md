---
aliases: [rational polynomial function]
---

# 📝Definition
A quotient of two [[polynomial]]s $P(z)$ and $Q(z)$,
$$
R(z)\equiv\frac{P(z)}{Q(z)}
$$
is called a rational function, or sometimes a rational polynomial function.

# 📈Diagram
![name|600](../assets/rational_functions.png)

# 💫Operation
## Method of partial fractions
### 📝Definition
Given a rational function
$$
\frac{P(x)}{Q(x)}
$$
Such that:
- $Q(x)$ can be factored linearly with distinct factors
- the degree of $P(x)$  is less than the degree of $Q(x)$
The method is the following.
- 1️⃣Factor the denominator $Q(x)$
- 2️⃣Set-up the equation to something like this $$\frac{??}{A}+\frac{??}{B}$$
- 3️⃣Solve for $A$ and $B$
- 4️⃣Rewrite rational function.

### 🧠Intuition
The method of partial fraction is to transform a complicate rational function to a simplified form.

### 🗃Example
- 📂example of partial fraction 1
	- 💬Question:
		- To solve $$\frac{4x-1}{x^2+x-2}$$
	- ✏Solution:
		- 1️⃣Factor the denominator $Q(x)$
			- $$Q(x) = x^2+x-2 = (x-1)(x+2)$$
		- 2️⃣Set-up
			- $$\frac{4x-1}{(x-1)(x+2)} = \frac{A}{x-1}+\frac{B}{x+2}$$
		- 3️⃣Solve for $A$ and $B$
			- Solve A
				- Multiply by  $(x-1)$, then we have
				- $$\frac{4x-1}{x+2} = A + \frac{B}{x+2}(x-1)$$
				- Plug in $x=1$: (Take the limits as $x\to1$.)
				- $$\frac{4-1}{1+2} = A$$
			- Solve B
				- Multiply by $(x+2)$:
				- $$\frac{4x-1}{x-1} = \frac{A}{x-1}(x+2) +B$$
				- Plug in $x=-2$: (Take the limits as $x\to-2$.)
				- $$\frac{-8-1}{-2-1} = B$$
		- 4️⃣Rewrite rational function.
			- $$\frac{4x-1}{x^2+x-2} = \frac{1}{x-1}+\frac{3}{x+2}$$


# 🕹Quiz
- 📌Quiz 1
	- 💬Question: Which of the following functions are rational functions?
		- $0,x, x^{-1}, x^{2/3}, \frac{x^2-1}{x^2+1}, \frac{x^2-1}{\sqrt{x^2+1}}, e^x+1$
	- ✏Solution:
		- $0$✅
			- The constant function $0$ is a polynomial, so it is also a rational function.
		- $x$✅
			- The linear function $x$ is a polynomial, so it is also a rational function where the denominator is $1$.
		- $x^{-1}$✅
			- The function $x^{-1} = \frac{1}{x}$ is a rational function.
		- $x^{2/3}$❌
			- The function $x^{2/3}$ is not rational because it is raised to a **non-integer** power.
		- $\frac{x^2-1}{\sqrt{x^2+1}}$❌
			- The denominator of $\frac{x^2-1}{\sqrt{x^2+1}}$ is not a polynomial, so this is not a rational function.
		- $e^x+1$
			- The function $e^x+1$ is not polynomial, so is not rational.


