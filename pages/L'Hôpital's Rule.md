alias:: hospital rule

- # 🍴Quick Digest -> L'Hôpital's Rule
	- ## 🎯Intent
	  l'Hospital's Rule uses [[Derivative]] to evaluate [[Limit]] of [[indeterminate form]].
	- ## 📝Definition
	  There are 2 version of this rule under different conditions but surprisingly with same outcome!! I therefore put them into together. Suppose we want to solve the limit of function $f(x)$ and $g(x)$. The rule states:
		- If
			- (option 1) $f,g\to0$ or
			- (option 2) $f,g\to+\infty$ or
			- (option 3) $f,g\to-\infty$
		- as
			- (condition 1) $x\to a^+$
			- (condition 2) $x\to a^-$
			- (condition 3) $x\to a$
		- and $f,g$ are [[differentiable]] near $x=a$
		- then we have
			- (rule1)
			  $$
			  \lim_{x\to a}\frac{f(x)}{g(x)}=\lim_{x\to a}\frac{f'(x)}{g'(x)}
			  $$
			- (rule2)
			  $$
			  \lim_{x\to a^+}\frac{f(x)}{g(x)}=\lim_{x\to a^+}\frac{f'(x)}{g'(x)}
			  $$
			- (rule3)
			  $$
			  \lim_{x\to a^-}\frac{f(x)}{g(x)}=\lim_{x\to a^-}\frac{f'(x)}{g'(x)}
			  $$
		- provided that the right hand side
			- (result 1/2) exists or
			- (result 2/2) is $\pm\infty$
		- P.S.✏ No matter which option/condition/rule you chose, you can always have one of two result at the end. However⚠, the rule works for different input but how to prove the rule is totally different!
	- ## 📏Proof 
	  To prove something...
		- Prove that
		  $$
		  \lim_{x\to a}\frac{f(x)}{g(x)}=\lim_{x\to a}\frac{f'(x)}{g'(x)}
		  $$
		  when
		  $$
		  f(a)=g(a)=0
		  $$
			- before to prove, you can take a look at the similar example [here](((6308dfd3-1a08-418a-9320-7ab61e116719)))
			- Start to prove ->
			- Note that for $x$ near $a$, we can approximate $f(x)$ and $g(x)$ by their linear approximations.
			- This give us
			  $$
			  \begin{align}
			  \frac{f(x)}{g(x)} &\approx \frac{f(a)+f'(a)\Delta x}{g(a)+g'(a)\Delta x}\\
			  &=\frac{f'(a)\Delta x}{g'(a)\Delta x}\quad \text{since }f(a)=g(a)=0\\
			  &=\frac{f'(a)}{g(a)}\quad\text{provided $f'(a)$ and $g'(a)$ exist.}
			  \end{align}
			  $$
	- ## 🗃Example
	  The following are few examples on how to use l'Hospital's Rule
		- Calculate $\lim_{x\to0^+}\frac{e^x-1}{x-\sin{x}}$
			- The limit is indeterminates as it is the form $\frac{0}{0}$
			- Then we can use the rule to solve this
			- $$
			  \lim_{x\to0^+}\frac{e^x-1}{x-\sin{x}}=\lim_{x\to0^+}\frac{e^x}{1-\cos{x}}=\infty
			  $$
		- Compute $\lim_{x\to\infty}\frac{\ln{(x^2)}+4x+30}{8x+\sqrt{x}}$
			- The limit is indeterminates as it is the form $\frac{\infty}{\infty}$
			- Then we can use the rule to solve this
			- $$
			  \lim_{x\to\infty}\frac{\ln{(x^2)}+4x+30}{8x+\sqrt{x}}=\lim_{x\to\infty}\frac{\frac{2}{x}+4}{8x+\frac{1}{2\sqrt{x}}}=\frac{1}{2}
			  $$
		- Calculate $\lim_{x\to\pi}\frac{x\sin{x}}{\cos^2{x}+1}$
			- The limit is NOT indeterminates as it is the form $\frac{0}{2}$
			- Therefore we do not need to apply this rule.
		- Compute $\lim_{x\to\infty}\frac{\ln{(e^x+5x)}}{4x+3}$
			- The limit is indeterminates as it is the form $\frac{\infty}{\infty}$
			- Then we can use the rule to solve this
			- $$
			  \lim_{x\to\infty}\frac{\ln{(e^x+5x)}}{4x+3}=\lim_{x\to\infty}\frac{\frac{e^x+5}{e^x+5x}}{4}=\lim_{x\to\infty}\frac{1}{4}\frac{e^x+5}{e^x+5x}
			  $$
			- This limit is still indeterminate then we can have 2 solutions:
				- METHOD 1: Apply Hospital rule again
					- then we have 2 times applied the rule...
					- $$
					  \lim_{x\to\infty}\frac{1}{4}\frac{e^x+5}{e^x+5x}=\lim_{x\to\infty}\frac{1}{4}\frac{e^x}{e^x+5}=\lim_{x\to\infty}\frac{1}{4}\frac{e^x}{e^x}=\frac{1}{4}
					  $$
				- METHOD 2: Algebraic manipulation:
					- denominate with $e^x$
					- $$
					  \begin{align}
					  \frac{e^x}{e^x+5}&=\frac{1}{1+5e^{-x}}\\
					  \lim_{x\to\infty}\frac{1}{4}\frac{e^x+5}{e^x+5x}&=\lim_{x\to\infty}\frac{1}{4}\frac{1}{1+5e^{-x}}=\frac{1}{4}
					  \end{align}
					  $$
		- Calculate $\lim_{x\to0^+}xe^{1/x}$
			- l'Hospital's Rule can solve $\frac{0}{0}$ and $\frac{\infty}{\infty}$, but this form is $0\cdot\infty$
			- we need to use some [[algebraic]] trick.
			- solution
			  $$
			  \begin{align}
			  xe^{1/x} &= \frac{e^{1/x}}{1/x}\\ 
			  \text{let } 1/x &=u\\
			  &=\frac{e^u}{u}\\
			  \text{as }x\to0^+,u\to\infty\\
			  \text{apply l'Hop's rule and we got}\\
			  \frac{e^u}{u}\space\overset {\text{l'Hop}}{\Large \sim }\space e^u \underset {u\rightarrow \infty }{\longrightarrow } \infty
			  \end{align}
			  $$
		- Compute $\displaystyle {\lim _{x\rightarrow \infty } \frac{x^{1000000}}{e^x}}$, as example using L'Hopital's Rule repeatedly
			- This limit is an indeterminate form of the type $\displaystyle \frac{\infty }{\infty }.$
			- Applying l'Hôpital's rule repeatedly we find:
			  $$
			  \begin{align}
			  \frac{x^{1000000}}{e^x}&\overset {\text{l'Hop}}{\Large \sim } \frac{1000000x^{999999}}{e^x}\\
			  &\overset {\text{l'Hop}}{\Large \sim } \frac{1000000\cdot 999999x^{999998}}{e^x}\\
			  &\vdots\\
			  &\overset {\text{l'Hop}}{\Large \sim } \frac{10^6!}{e^x} \underset {x\rightarrow \infty }{\longrightarrow } = 0
			  \end{align}
			  $$
	- ## 🕳Pitfall
	  Watch out!
		- 📌When the expression is **not** [[indeterminate form]], using L'Hospital's rule may have wrong result
			- Take $\frac{\sin{x}}{x^2}$ as an example
			- If we apply the rule, we got
			  $$
			  \frac{\sin{x}}{x^2} 
			  \space\overset {\text{l'Hop}}{\Large \sim } \space
			  \frac{\cos{x}}{2x}
			  \space\overset {\text{l'Hop}}{\Large \sim } \space
			  \frac{-\sin{x}}{2}\to0
			  $$
			- but if we use [[Linear Approximation]] to approximate
			  $$
			  \sin{x}\approx x,\\
			  \text{so we have}\\
			  \frac{\sin{x}}{x^2}\approx\frac{x}{x^2}=\frac{1}{x}=\infty
			  $$
			- the results don't match!
			- Because at the step
			  $$
			  \frac{\cos{x}}{2x}
			  \space\overset {\text{l'Hop}}{\Large \sim } \space
			  \frac{-\sin{x}}{2}
			  $$
			  $\frac{\cos{x}}{2x}$ is not [[indeterminate form]]!! It is $\frac{1}{0}=\infty$
	- ## 🧠Intuition
	  Find an intuitive way of understanding this concept.
	- ## 🧮Expression
	  $$
	  \begin{align}
	  f(x)&=
	  \end{align}
	  $$
	- ## 📈Diagram
	  ![name](../assets/name.png)
	- ## ✒Descriptive Explanation
	  A narrative... a descriptive words subject on the concept... 描述性解释…
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
	- ## ⚖Laws
	  The laws related to this math concepts.
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?