- # 📝Definition
	- An affine function is with the following form
	  $$
	  f:\mathbb{R}^n\to\mathbb{R}\\f(x)=a^Tx+b
	  $$
	  with $a,x$ are $n$-[[vector]] and $b$ a [[scalar]](sometimes called offset).
- # 🧠Intuition
	- An affine function is just a [[Linear Function]] plus a constant.
- # ⛈Characteristics / Properties
	- 📌Superposition
		- Unlike [[Linear Function]] which has no constraints on the coefficients. For affine function, there IS constraint on superposition ⚠where the coefficients have to be **1** in total.
		- Proof
			- Because superposition is:
			  $$
			  f(\alpha x+\beta y)=\alpha f(x)+\beta f(y)
			  $$
			  And affine function is:
			  $$
			  f(x)=a^Tx+b
			  $$
			  Therefore there are **2** "b" in both sides:
			  $$
			  b=\alpha b_1+\beta b_2
			  $$
			  So the only chance they are the same is that 
			  $$
			  \alpha+\beta=1
			  $$
		- 🤔What can we take advantage of this property?
			- OK, an affine function can satisfy superposition if and only if $\alpha+\beta=1$. Therefore, we can think another way around: if we set $\alpha+\beta=1$, and the function does NOT satisfy superposition, then it is NOT an affine function.
- # 🧬Byproduct
	- There are 2 very important affine functions.
		- [[Taylor Approximation]]
		- [[Regression Model]]
- # 🕳Pitfalls
	- Sometimes (ignorant) people refer to affine function as linear function. But we are not those people.