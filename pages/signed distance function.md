---
aliases: [oriented distance function]
tags:
  - function
  - geometry
  - mathematics
---


# 📝Definition
The signed distance function is the orthogonal distance of a given point $x$ to the boundary of a set $\Omega$ in a metric space, with the sign determined by whether or not $x$ is in the interior of $\Omega$.

# ✒Notation
If $\Omega$ is a subset of a metric space $X$ with metric $d$, then the signed distance function $f$ is defined by
$$
f(x)=\begin{cases}
d(x,\partial\Omega)\quad&\text{if }x\in\Omega\\
-d(x,\partial\Omega)\quad&\text{if }x\in\Omega^c
\end{cases}
$$
- $\partial\Omega$ denotes the boundary of $\Omega$
For any $x\in X$, 
$$
d(x,\partial\Omega):=\inf_{y\in \partial\Omega}d(x,y)
$$
- $\inf$ denotes the [[infimum]].



# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🧀Applicability

## 🍞[[implicit surface representation]]
In addition to inside/outside queries, signed distance function also **simplifies** distance computations to simple function evaluations, which can be used to compute and control the global error for
- mesh processing algorithms
- collision detection computations

🥐
🥖
🥨
🥯
🥞
🧇



# 🌱Related Elements
The closest pattern to current one, what are their differences?




# 🍂Unorganized

