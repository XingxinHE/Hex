- ## 📝Definition
	- A mathematical expression can also be said to be indeterminate if it is not definitively or precisely determined.
- ## 🧠Intuition
	- The term "indeterminate" is sometimes used as a synonym for **unknown** or variable (Becker and Weispfenning 1993, p. 188).
- ## 🏷(Sub)Categories
	- There are seven indeterminate forms involving $0, 1$, and $\infty$:
	- $\frac{0}{0}$,
	- $0·\infty$,
	- $\frac{\infty}{\infty}$,
	- $\infty-\infty$,
	- $0^0$,
	- $\infty^0$,
	- $1^\infty$
- ## 🗃Example
	- 📌Example(1) to Use [[Logarithm]] with a base [[Euler Number]] to solve Exponential Indeterminate Forms
		- Assume that , and that
		  $$
		  \begin{align}
		  \lim _{x\rightarrow a} f(x)&=0\\
		  \lim _{x\rightarrow a} f(x) &= +\infty
		  \end{align}
		  $$
		- What is $\displaystyle \lim _{x\rightarrow a} f(x)^{g(x)}$?
		- Solution
			- Any number close to 0 raised to a large power is going to be even smaller, that is even closer to zero. This is not an indeterminate form. The limit of this exponent is 0.
			- Another way to think about this is to take the logarithm of this function, and we get
			  $$
			  \displaystyle \ln \left(f(x)^{g(x)}\right) = g(x) \ln (f(x))
			  $$
			- which is of the form $\infty \cdot (-\infty )$
			- which is **not** an indeterminate form, this tends to $-\infty$. Then the original function tends towards 0 as $x$ approaches $a$:
			  $$
			  \displaystyle f^g = e^{g\ln f} \underset {x \rightarrow a}{\longrightarrow } e^{-\infty }.
			  $$
	- 📌Example(2) to use [[Logarithm]] with a base [[Euler Number]] to solve exponential indeterminate forms
		- Calculate $\displaystyle \lim _{x\rightarrow \pi /2^-} \left( \frac{2x}{\pi } \right)^{\tan x}$
			- Solution
				- This is indeterminate of the form $1^\infty$. Take the logarithm and arrange to be of standard indeterminate form:
				- $$
				  \displaystyle \ln \left[ \left( \frac{2x}{\pi } \right)^{\tan x} \right] = \tan x (\ln 2x - \ln \pi ) = \frac{ (\ln 2x - \ln \pi )\sin x}{\cos x}.
				  $$
				- Now apply l'Hôpital's rule.
				- $$
				  \frac{ (\ln 2x - \ln \pi )\sin x}{\cos x} \overset {\text{l'Hop}}{\Large \sim } \frac{ (1/x)\sin x +(\ln 2x - \ln \pi )\cos x }{-\sin x} \underset {x \rightarrow \pi /2^{-}}{\longrightarrow } -2/\pi
				  $$
				- To evaluate the limit, we take the exponent of the resultant limit above, and we find $e^{-2/\pi}$.