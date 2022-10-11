alias:: Euclidean Norm

- # 📝Definition
	- Suppose:
		- $x$ is a $n$-vector
	- $\lVert x\rVert$, is denoted as its *Euclidean norm*.
		- $$
		  \lVert x\rVert=\sqrt{x_1^2+x_2^2+\cdots+x_n^2+}
		  $$
	- Since it is no difference as the **squareroot of the inner product** of the vector with **itself**, we can write as:
	  $$
	  \lVert x\rVert=\sqrt{x^Tx}
	  $$
	- Another notation of Euclidean Norm:
	  $$
	  \lVert x\rVert_2
	  $$
	  The subscript $2$ indicates that the entries of $x$ are raised to the second power. That's why we call it L-2 Norm.
- # 🧠Intuition
	- Norm is to measure magnitude⭐
		- The double bar notation indicates the norm of a vector is a (numerical) measure of its **magnitude**(not considering orientation). Therefore, we can say a vector is **small** if its *norm is a small* number, and **large** is with a *large number*. This is also the reason use $\lVert \rVert$ to denote.
- # ⛈Characteristics / Properties
	- 📌nonnegative homogeneity非负齐次性
		- $$
		  \lVert\beta x\rVert = \lvert\beta\rvert\lVert x\rVert
		  $$
	- 📌 [[Triangle Inequality]] (subadditivity次可加性)
		- $$
		  \lVert x+y\rVert\leq\lVert x\rVert+\lVert y\rVert
		  $$
	- 📌Nonnegativity
		- $$
		  \lVert x\rVert\geq0
		  $$
	- 📌Definiteness
		- $$
		  \lVert x\rVert=0, \text{only if }x=0
		  $$
- # 🏷(Sub)Categories
	- What are the sub objects of this subject?
	- 📌 Norm of a sum
		- Suppose you have 2 vectors, $x$ and $y$. The norm of $x+y$ is:
		  $$
		  \lVert x+y\rVert=\sqrt{\lVert x\rVert^2+2x^Ty+\lVert y\rVert^2}
		  $$
	- 📌 Norm of a block vectors
		- Suppose you have a block vectors $d$ which is composed by $a,b,c$:
		  $$
		  d=\begin{matrix}a_1\\\vdots\\a_n\\b_1\\\vdots\\b_n\\c_1\\\vdots\\c_n\end{matrix}
		  $$
		- The norm-squared of a stacked vector is the sum of the norm-squared values of its subvectors:
		  $$
		  \lVert d\rVert^2=d^Td=a^Ta+b^Tb+c^Tc=\lVert a\rVert^2+\lVert b\rVert^2+\lVert c\rVert^2
		  $$
		- This philosophy⭐ always is treated as its reverse:  <u>the norm of a stacked vector</u> **is** <u>the norm of the vector formed from the norms of the subvectors</u>.
		  $$
		  \lVert (a,b,c)\rVert=\sqrt{\lVert a\rVert^2+\lVert b\rVert^2+\lVert c\rVert^2}=\lVert(\lVert a\rVert,\lVert b\rVert,\lVert c\rVert)\rVert
		  $$
- # 🧬Related Elements / Byproduct
	- The closest pattern to current one, what are their differences?
	- 📌RMS(root-mean-square)
	  id:: 632aafb4-b82f-4e4c-ab04-6d535b486768
		- $$
		  \bold{rms}(x)=\sqrt{\frac{x_1^2+\cdots+x_n^2}{n}}=\frac{\lVert x \rVert}{\sqrt{n}}
		  $$
		- The key idea of RMS is to **compare norms of vectors with different dimensions**.🌟