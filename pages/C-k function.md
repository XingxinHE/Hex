---
aliases: [C-0 function, C-1 function, C-2 function]
tags:
  - FunctionalAnalysis
  - mathematics
---

https://mathworld.wolfram.com/C-kFunction.html

# 🧠Intuition
A function with $k$ [[continuity|continuous]] [[derivative]]s is called a $C^k$ [[function]].

# 📝Definition

## real-valued function
Let $k$ be a nonnegative [[integer]]. A [[real-valued function]] $f : U \to \mathbb{R}^3$ is said to be $C^k$ at $p \in U$ if its [[partial derivative]]s 
$$
\frac{\partial^j f}{\partial x^{i_1}\dots\partial x^{i_j}}
$$
of all orders $j\leq k$ exist and are [[continuity|continuous]] at $p$.

## vector-valued function
A [[vector-valued function]] $f:U\to\mathbb{R}^m$ is said to be $C^k$ at $p$ if all of its component functions $f^1,\dots,f^m$ are $C^k$ at $p$. We say that $f : U \to \mathbb{R}^m$ is $C^k$ on $U$ if it is $C^k$ at every point in $U$. 


# 🏷Categories
## 🔖$C^0$ function
### 📝Description
The most common $C^k$ space is $C^0$, the space of [[continuity|continuous]] [[function]]s.

### 🗃Example
Let $f : \mathbb{R}\to\mathbb{R}$ be $f (x) = x^{1/3}$. Then
$$
f'(x)=
\begin{cases}
\frac{1}{3}x^{-2/3}\quad& \text{for }x\neq0\\
\text{undefined}\quad&\text{for }x=0
\end{cases}
$$
Thus the function is $C^0$ but not $C^1$ at $x=0$.



## 🔖$C^1$ function
### 📝Description
$C^1$ is the space of [[continuity|continuously]] [[differentiable]] functions.

### 🗃Example
Let $g : \mathbb{R}\to\mathbb{R}$ be defined by
$$
g (x) =\int_0^x f(t)dt=\int_0^x t^{1/3}dt= \frac{3}{4}x^{4/3}.
$$Then $g'(x)=f(x)=x^{1/3}$, so $g(x)$ is $C^1$ but not $C^2$ at $x=0$.



🔖
🔖






# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized