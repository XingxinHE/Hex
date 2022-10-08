- # 📝Definition
	- The $\sum$ notation in a compact way to denote a sum in which each term is obtained from a formula:
		- $$
		  \displaystyle \sum _{i=1}^n a_i = a_1+a_2+\cdots +a_{n-1}+a_{n}
		  $$
		- The preceding notation reads “the sum of $a_i$ from $i=1$ to $i=n$."
- # 🧠Intuition
	- For me, I would like to see it in a programming perspective - iteration. It is merely a [[for loop]].
- # 🧪Composition
	- initial value - e.g. $i=1$
	- sentinel value - e.g. $n$
	- $$
	  \sum_{\text{top of the symbol: variable with initial value}}^{\text{bottom of the symbol: sentinel value or how many steps}}
	  $$
- # 🗃Example
	- example of summation notation 1
		- $$
		  \displaystyle \sum _{i=1}^n i^2 = 1^2+2^2+3^2+\cdots +(n-1)^2+n^2
		  $$
	- example of summation notation 2
		- $$
		  \displaystyle \sum _{n=1}^4 n^2 = 1 + 2^2 + 3^2 + 4^2 = 1 + 4 + 9 + 16 = 30
		  $$
	- example of summation notation 3
		- $$
		  \displaystyle \sum _{j=0}^4 2^j = 1 + 2 + 4 + 8 + 16 = 31
		  $$
	- example of summation notation 4
		- $$
		  \begin{align}
		  \sum _{i=4}^N 10 + \sum _{j=0}^{M} 6 &=\underbrace{(10+ 10 + \cdots + 10)}_\text {N-4+1 times }+ \underbrace{(6+\cdots +6)}_\text {M+1 times})\\
		  &=10(N-3)+6(M+1)
		  \end{align}
		  $$