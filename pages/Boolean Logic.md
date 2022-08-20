alias:: boolean

- # 📝Definition
	- Boolean logic is a mathematical system built around the two values `TRUE` and `FALSE`. The values `TRUE` and `FALSE` are called the **Boolean values** and are often represented by the values `1` and `0`.
- # ✒Notation
	- [$\neg$](((6325d3a4-68de-4075-b3d4-6643aed93cb6))) $\backslash$neg stands for "negation"
		- negation
	- [$\lor$](((6325d3a5-1d19-4b9e-b1df-1ce5da48875a))) $\backslash$lor stands for "logic or"
		- conjunction
	- [$\land$](((6325d3a5-8717-4fa1-a580-fa38a09d24ca))) $\backslash$land stands for "logic and"
		- disjunction
	- [$\oplus$](((63258218-4b4b-4df3-9ca9-ddc9bd668b42)))
		- `XOR` operation
	- [$\leftrightarrow$](((6325d653-e24c-45b4-8194-05d97c78784d)))
		- equality operation
	- [$\rightarrow$](((6325829f-9526-4eac-870e-7150df55064a)))
		- implication operation
- # 💫Support Operation
	- We can manipulate Boolean values with the Boolean operations.
	- 📌Negation or `NOT` operation
		- $$
		  \neg0=1\\\neg1=0
		  $$
	- 📌Conjunction or `AND` operation
		- $$
		  0\land0=0\\
		  0\land1=0\\
		  1\land0=0\\
		  1\land1=1\\
		  $$
	- 📌Disjunction or `OR` operation
		- $$
		  0\lor0=0\\
		  1\lor0=1\\
		  0\lor1=1\\
		  1\lor1=1\\
		  $$
	- 📌Exclusive or or `XOR` operation
		- The `XOR` operation is 1 if **either** but **not both** of its two operands is 1.
		- $$
		  
		  \begin{align}
		  0\oplus0&=0\\
		  0\oplus1&=1\quad\text{matched}\\
		  1\oplus0&=1\quad\text{matched}\\
		  1\oplus1&=0
		  \end{align}
		  $$
	- 📌Equality operation
		- The equality operation is 1 if both of its operands have the same value.
		- $$
		  \begin{align}
		  0\leftrightarrow0&=1\quad\text{matched}\\
		  0\leftrightarrow1&=0\\
		  1\leftrightarrow0&=0\\
		  1\leftrightarrow1&=1\quad\text{matched}
		  \end{align}
		  $$
	- 📌Implication operation
		- The implication operation is 0 if its first operand is 1 and its second operand is 0; otherwise, it is 1.
		- $$
		  \begin{align}
		  0\rightarrow0&=1\\
		  0\rightarrow1&=1\\
		  1\rightarrow0&=0\quad\text{matched}\\
		  1\rightarrow1&=1\\
		  \end{align}
		  $$
	- 📌Conversion between operation
		- $$
		  \begin{align}
		  P\lor Q &\quad\quad\neg(\neg P\land\neg Q)\\
		  P\rightarrow Q &\quad\quad\neg P\lor Q\\
		  P\leftrightarrow Q &\quad\quad(P\rightarrow Q)\land(Q\rightarrow P)\\
		  P\oplus Q &\quad\quad\neg(P\leftrightarrow Q)
		  \end{align}
		  $$
- # ⚖Laws
	- 📌Distributive Law
		- $P\land(Q\lor R)\text{ equals }(P\land Q)\lor(P\land R),\text{ and its dual}$
		- $P\lor(Q\land R)\text{ equals }(P\lor Q)\land(P\lor R)$