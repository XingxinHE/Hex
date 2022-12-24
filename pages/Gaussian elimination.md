---
aliases: [linear system of equations]
tags:
  - LinearAlgebra
  - mathematics
---


# 📝Definition
Gaussian elimination is a method for solving matrix equations of the [[system of linear equations]].
___
The steps to perform Gaussian elimination starting with the system of equations
$$
\begin{bmatrix}
a_{11}&a_{12}&\dots&a_{1k}\\
a_{21}&a_{22}&\dots&a_{2k}\\
\vdots&\vdots&\ddots&\vdots\\
a_{k1}&a_{k2}&\dots&a_{kk}
\end{bmatrix}
\begin{bmatrix}
x_1\\x_2\\\vdots\\x_k
\end{bmatrix}
=
\begin{bmatrix}
b_1\\b_2\\\vdots\\b_k
\end{bmatrix}
$$
are:
- 1️⃣ Compose the "[[augmented matrix]] equation"
	- $$\left[\begin{array}{cccc|c}a_{11}&a_{12}&\dots&a_{1k}&b_1\\a_{21}&a_{22}&\dots&a_{2k}&b_2\\\vdots&\vdots&\ddots&\vdots&\vdots\\a_{k1}&a_{k2}&\dots&a_{kk}&b_k\end{array}\right]\begin{bmatrix}x_1\\x_2\\\vdots\\x_k\end{bmatrix}$$
	- Here, the [[column vector]] in the variables $\mathbf{x}$ is carried along for labeling the matrix rows.
- 2️⃣ perform elementary row operations to put the augmented matrix into the upper triangular form
	- $$\left[\begin{array}{cccc|c}a'_{11}&a'_{12}&\dots&a'_{1k}&b'_1\\0&a'_{22}&\dots&a'_{2k}&b'_2\\\vdots&\vdots&\ddots&\vdots&\vdots\\0&0&\dots&a_{kk}&b'_k\end{array}\right]$$
- 3️⃣ Back substitution. Solve the equation of the $k$th row for $x_k$, then substitute back into the equation of the $(k-1)$st row to obtain a solution for $x_{k-1}$, etc., according to the formula
	- $$x_i=\frac{1}{a'_{ii}}\left(b'_i-\sum_{j=i+1}^{k}a'_{ij}x_{j}\right)$$
> [!tip] Takeaway
> Few things on elimination I want to point out.
> - 1️⃣ The **objective** of elimination is to make $A$ to $U$ (a.k.a. [[upper triangular matrix]]).
> - 2️⃣ The operation goes *from top to the bottom*.
> - 3️⃣ When performing a $k$-row operation, all the number **under** the pivot of this row **should be zero**.
> - 4️⃣ The **pivot** of the 1st row is the 1st coefficient, 2nd row - 2nd coefficient, etc.

# 🎯Intent
Gaussian elimination / elimination is to change $A$ to $U$!
> [!important]
> The most important stuff about Gaussian elimination is to understand why are we doing it. Please refer to [[upper triangular matrix#🚀Benefit / Pros#🛰️easy to solve system of linear equations]].



# 🧠Intuition
.


# 🗃Example
- 📁classic example of Gaussian elimination 0 ^064827
	- 💬Question: Solve this system. $\begin{bmatrix}9&3&4\\4&3&4\\1&1&1\end{bmatrix}\begin{bmatrix}x\\y\\z\end{bmatrix}=\begin{bmatrix}7\\8\\3\end{bmatrix}$
	- ✏Solution: 
		- 1️⃣ Change to augmented form.
			- $\left[\begin{array}{ccc|c}9&3&4&7\\4&3&4&8\\1&1&1&3\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$ 
		- 2️⃣ Switching the 1st and 3rd rows. 
			- $\left[\begin{array}{ccc|c}1&1&1&3\\4&3&4&8\\9&3&4&7\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
		- 3️⃣ $\text{row}_3=\text{row}_3-9\text{row}_1$
			- $\left[\begin{array}{ccc|c}1&1&1&3\\4&3&4&8\\0&-6&-5&-20\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
		- 4️⃣ $\text{row}_2=\text{row}_2-4\text{row}_1$
			- $\left[\begin{array}{ccc|c}1&1&1&3\\0&-1&0&-4\\0&-6&-5&-20\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
		- 5️⃣ $\text{row}_3=\text{row}_3+(-6)\text{row}_2$
			- $\left[\begin{array}{ccc|c}1&1&1&3\\0&-1&0&-4\\0&0&-5&4\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
		- 6️⃣ Restore back to normal matrix.
			- $\begin{bmatrix}1&1&1\\0&-1&0\\0&0&-5\end{bmatrix}\begin{bmatrix}x\\y\\z\end{bmatrix}=\begin{bmatrix}3\\-4\\4\end{bmatrix}$
		- 7️⃣ Solve it.
			- $x=-1/5, y=4, z=-4/5$


- 📩 classic example of Gaussian elimination 1 ^2da661
	- 💬Question: Solve the equations with 3 unknown:
		- $\begin{align}\begin{cases}x&+2y&+z&=2\\3x&+8y&+z&=12\\&4y&+z&=2\end{cases}\end{align}$
	- 🏹Strategy: In this example, we don't introduce the augmented matrix in the first place. Instead, we focus on the main part($A$ to $U$).
	- ✏Solution:
		- 1️⃣ Change to matrix format.
			- $\begin{align}Ax&=b\\\begin{bmatrix}1&2&1\\3&8&1\\0&4&1\end{bmatrix}\begin{bmatrix}x\\y\\z\end{bmatrix}&=\begin{bmatrix}2\\12\\2\end{bmatrix}\end{align}$
		- 2️⃣ Eliminate all the values below the pivot on 1st row. The ingredients are row2 and row1.
			- $\begin{align}\begin{bmatrix}\underline{1}&2&1\\3&8&1\\0&4&1\end{bmatrix}\xrightarrow{\text{row}_2 - 3\text{row}_1}\begin{bmatrix}\underline{1}&2&1\\0&2&-2\\0&4&1\end{bmatrix}\end{align}$
		- 3️⃣ Eliminate all the values below the pivot on the 2nd row. The ingredients are row3 and row2.
			- $\begin{align}\begin{bmatrix}\underline{1}&2&1\\0&\underline{2}&-2\\0&4&1\end{bmatrix}\xrightarrow{\text{row}_3-2\text{row}_2}\begin{bmatrix}\underline{1}&2&1\\0&\underline{2}&-2\\0&0&\underline{5}\end{bmatrix}\end{align}$
		- 4️⃣ Bring back the $b$ and [[augmented matrix]]. Because we want to make step2️⃣ and step3️⃣ more intuitive, so we don't take $b$ into account for a moment. In the end , we can add the right hand side $b$ back to the above logic. This step is called **back substitution** and the matrix in the following format called **augmented matrix**.
			- $\begin{align}\left[\begin{array}{c|c}A&b\end{array}\right]=\left[\begin{array}{ccc|c}1&2&1&2\\3&8&1&12\\0&4&1&2\end{array}\right]\to\left[\begin{array}{ccc|c}1&2&1&2\\0&2&-2&6\\0&4&1&2\end{array}\right]\to\left[\begin{array}{ccc|c}1&2&1&2\\0&2&-2&6\\0&0&5&-10\end{array}\right]\end{align}$
		- 5️⃣  Convert matrix to equation.
			- $\begin{align}\begin{cases}x&+2y&+z&=2\\&2y&-2z&=6\\&&5z&=-10\end{cases}\end{align}$
		- 6️⃣ Solve it.
			- $x=2, y=1, z=-2$






🗂
📨
📂

# 🗿Socratic Method
- **💬Question**: why exchanging the row does not affect the unknown vector?
	- for example 
		- from this one $\left[\begin{array}{ccc|c}9&3&4&7\\4&3&4&8\\1&1&1&3\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
		- to this one $\left[\begin{array}{ccc|c}1&1&1&3\\4&3&4&8\\9&3&4&7\end{array}\right]\begin{bmatrix}x\\y\\z\end{bmatrix}$
- **🗣Answer**: 
	- Because changing the row order is merely changing the order of the equations.
- **✍Argument**:
	- - The effect is changing this
	- $\begin{align}\begin{cases}9x&+3y&+4z&=7\\4x&+3y&+4z&=8\\x&+y&+z&=3\end{cases}\end{align}$
	- to 
		- $\begin{align}\begin{cases}x&+y&+z&=3\\4x&+3y&+4z&=8\\9x&+3y&+4z&=7\end{cases}\end{align}$
- **📜Key Takeaway**:
	- The order may affect the matrix $A$ but it will not affect the "**system**" of linear equation.
___
- **💬Question**: Should I be cautious on the order of subtraction? Like which row subtract which row?
	- $\begin{align}\begin{bmatrix}\underline{1}&2&1\\0&\underline{2}&-2\\0&4&1\end{bmatrix}\xrightarrow{\text{row}_3-2\text{row}_2}\begin{bmatrix}\underline{1}&2&1\\0&\underline{2}&-2\\0&0&\underline{5}\end{bmatrix}\end{align}$
- **🗣Answer**: I personally think this is 2 problems.
	- What is the objective of this operation?
	- Why does this operation work?
- **✍Argument**:
	- Remember our objective is to reduce certain coefficients to $0$. And in this case, it aims to make $a_{3,4}$ as $0$.
	- The reason why this work can be referred to the essence of "**system** linear equation". The result of the operation $\text{row}_3-2\text{row}_2$ is merely asking *this* system to produce another equation. It is still from the system! Therefore, intuitively, I would like to think $\text{row}_3-2\text{row}_2$ as reassigning $\text{row}_3$. Something like [[parameter#^956ff9|this function]] acts in [[pass-by-value]].
	- 
	 ```cpp
	int num = 3;
	num = incre_value(num);
	```
- **📜Key Takeaway**: Elimination is like reassigning. $\text{row}_3=\text{row}_3-2\text{row}_2$



# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized


