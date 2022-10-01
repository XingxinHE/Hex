- ## 📝Definition
	- A function that satisfies [superposition](((2df2df99-4e4f-4f16-81f4-84543a22c5bf))) is called **linear**.
	- Another definition is that the function $f: \mathbb{R}^n\to\mathbb{R}$  is **linear** which it MUST satisfy following 2 properties:
		- [Homogeneity](((632151e6-ae83-446b-9b27-306674825fed)))
		- [Additivity](((632151e6-599a-4cf0-8247-e10d0964bc26)))
- ## 🧠Intuition
	- The word "linear" always means "straight line".
- # ✒Notation
	- $$
	  \begin{align}
	  f(x)=mx+b
	  \end{align}
	  $$
	- 📌Point-slope form
		- id:: 6337df95-fe77-4604-b1cf-a4e212e50eec
		  $$
		  y-y_0=m(x-x_0)
		  $$
- # ⛈Characteristics / Properties
	- 📌Slope
		- If a line goes through $(x_0, y_0)$ and has slope $m$ then its equation is
			- {{embed ((6337df95-fe77-4604-b1cf-a4e212e50eec))}}
		- If a line goes through $(x_1, y_1)$ and $(x_2, y_2)$, its slope is equal to
			- $$
			  \frac{y_2-y_1}{x_2-x_1}
			  $$
	- 📌Homogeneity
	  id:: 632151e6-ae83-446b-9b27-306674825fed
		- 齐次性
		- $f(\alpha x)=\alpha f(x)$
		- emphasize on scaling
	- 📌Additivity
	  id:: 632151e6-599a-4cf0-8247-e10d0964bc26
		- 可加性
		- $f(x+y)=f(x)+f(y)$
		- emphasize on adding
	- 📌Superposition
	  id:: 2df2df99-4e4f-4f16-81f4-84543a22c5bf
		- Definition:
		  id:: 632151e6-1947-42e1-b8c9-361e1111000f
			- Suppose $f$ is an [inner product function](((63214f0c-c066-4f21-85f8-69acff34dc3b))), $f$ can therefore be written as $a^T$. We have:
			  $$
			  \begin{align}
			  f(\alpha x+\beta y)&=a^T(\alpha x+ \beta y)\\
			  &=a^T(\alpha x)+a^T(\beta y)\\
			  &=\alpha(a^Tx)+\beta(a^Ty)\\
			  &=\alpha f(x)+\beta f(y)
			  \end{align}
			  $$
			- $x, y$ are $n$-vector.  $\alpha,\beta$​ are scalar.
- ## 📈Diagram
	- ![name](../assets/linear_function.png){:height 200, :width 200}
- ## ✒Descriptive Explanation
  A narrative... a descriptive words subject on the concept... 描述性解释…
- ## 🌓Complement
  What is the complement of this subject? e.g. vector-covector, constructor-destructor
- ## 📏Proof 
  To prove something...
- ## 🗃Example
  Example is the most straightforward way to understand a mathematical concept.
	- 📌Average Function - an example of linear function
		- The average of a $n$-vector can be defined as:
			- $$
			  f(x)=(x_1+x_2+\cdots+x_n)/n
			  $$
		- It can be denoted as avg($x$) . It also can be written as:
			- $$
			  f(x)=a^Tx,\text{   st. }\\a=(\frac{1}{n},\frac{1}{n},\cdots,\frac{1}{n})^T=\bold{1}/n
			  $$
			  meaning times $1/n$​ for every elements.
	- 📌Max Function - an example of NOT linear function
		- The maximum of a $n$-vector can be expressed as followed:
			- $$
			  f(x)=\text{max}\{x_1,\cdots,x_n\}
			  $$
		- Obviously, it is not a linear function.
- ## 🤳Applicability
   What are the situations in which this subject can be applied?
- ## 🧪Composition
  What kind of stuffs composite this subject?
- ## 🏷(Sub)Categories
  What are the sub objects of this subject?
- ## ⚖Laws
  The laws related to this math concepts.
- ## 🎯Intent
   A short description what does this thing do?
- # 🧬Related Elements
   The closest pattern to current one, what are their differences?
	- ## Inner Product Representation of a Linear Function
		- The logic can be back and forth.
		  | Hypothesis/Conclusion                                        | Relation | Hypothesis/Conclusion |
		  | ------------------------------------------------------------ | -------- | --------------------- |
		  | A function defined as the inner product of its argument with some fixed vector. | 🔄        | A function is linear. |
		- We therefore say $a^Tx$ the inner product representation of $f$.
		- See [here](((63214f0c-c066-4f21-85f8-69acff34dc3b))) what a inner product function is.