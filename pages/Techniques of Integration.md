# 📝Description
The techniques of integration is a virtual toolkit of techniques to find [[Antiderivative]]s. When I was learning calculus, I find following common techniques among different textbook. They are:
- Substitution
- Integration by parts
- Partial fractions
- Integrals Involving Trig Identities
- Integrals Involving Powers of Trig Functions
- Integrals Involving Trig Substitutions

# 🔗Link
The following are some helpful links.
https://wiki.ubc.ca/Integration_Techniques
https://www.whitman.edu/mathematics/calculus_online/chapter08.html


# Partial fractions
## 📝Definition
The technique of partial fractions applies to [[rational function]]. The idea is to take advantage from the [[rational function#💫Operation#Method of partial fractions|method of partial fractions]] which merely simplifies the rational form and then integrate it.

## 🗃Example
- 📂Practice integrating rational function 1
	- 💬Question:
		- Evaluate the following integral.
		- $$\int \frac{3x^2+4x-11}{(x^2-1)(x-2)}dx$$
	- 🏹Strategy: Review the technique and come back.
	- ✏Solution:
		- 1️⃣Factor the denominator $Q(x)$
			- $$Q(x) = (x^2-1)(x-2) = (x+1)(x-1)(x-2)$$
		- 2️⃣Set-up
			- $$\frac{3x^2+4x-11}{(x+1)(x-1)(x-2)} = \frac{A}{x-1}+\frac{B}{x+1} + \frac{C}{x-2}$$
		- 3️⃣Solve for $A,B$ and $C$
			- Solve $A$
				- Multiply by  $(x-1)$, then we have
				- $$\frac{3x^2+4x-11}{(x+1)\cancel{(x-1)}(x-2)} = A + \frac{B}{x+1}(x-1)+\frac{C}{x-2}(x-1)$$
				- Plug in $x=1$: (Take the limits as $x\to1$.)
				- $$A = \frac{3(1)^2+4(1)-11}{(1+1)(1-2)} = 2$$
			- Solve $B$
				- Multiply by  $(x+1)$, then we have
				- $$\frac{3x^2+4x-11}{\cancel{(x+1)}(x-1)(x-2)} = \frac{A}{x-1}(x+1) + B+\frac{C}{x-2}(x+1)$$
				- Plug in $x=-1$: (Take the limits as $x\to-1$.)
				- $$B = \frac{3(-1)^2+4(-1)-11}{(-1-1)(-1-2)} = -2$$
			- Solve $C$
				- Multiply by  $(x-2)$, then we have
				- $$\frac{3x^2+4x-11}{(x+1)(x-1)\cancel{(x-2)}} = \frac{A}{x-1}(x-2) + \frac{B}{x+1}(x-2)+C$$
				- Plug in $x=2$: (Take the limits as $x\to2$.)
				- $$C = \frac{3(2)^2+4(2)-11}{(2-1)(2+1)} = 3$$
		- 4️⃣Rewrite rational function.
			- $$\frac{3x^2+4x-11}{(x+1)(x-1)(x-2)} = \frac{2}{x-1}+\frac{-2}{x+1} + \frac{3}{x-2}$$
		- 5️⃣Take the antiderivative
			- $$\begin{align}\int \frac{3x^2+4x-11}{(x^2-1)(x-2)}dx&= \int \frac{2}{x-1}dx+\int \frac{-2}{x+1}dx+\int \frac{3}{x-2}dx\\&= 2\ln (|x-1|)-2\ln (|x+1|)+3\ln (|x-2|)+C
\end{align}$$

