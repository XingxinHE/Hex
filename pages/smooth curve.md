---
aliases: [curve, differentiable curve]
tags:
  - AnalyticGeometry
  - DifferentialGeometry
---


# 📝Definition
**📄Definition - smooth curve**
A smooth curve is a [[curve]] which is a smooth function, where the word "curve" is interpreted in the #AnalyticGeometry  context. In particular, a smooth curve is a [[continuity|continuous]] [[function|mapping]] $f$ from a $1$-dimensional space to an $n$-dimensional space which on its [[domain]] has continuous [[derivative]]s up to a desired order.
___
**📃Definition - differentiable curve**
A parametrized differentiable curve is a [[differentiable]] [[function|map]] $\alpha: I \to \mathbb{R}^3$ of an open [[interval]] $I = (a, b)$ of the real line $\mathbb{R}$ into $\mathbb{R}^3$.




> [!info] Remark
> When discussing curves from the standpoint of analytic geometry, care must be exhibited to maintain the important distinction between the curve itself and its [[range|image]] within its [[codomain]].
> 
> 
> For example, the curves $\gamma_i:[0,1]\to\mathbb{R}, i=1,2$, defined, respectively, by
> $\gamma_1(t)=t$ and $\gamma_2(t)=t$.
> These 2 are unique as curves even though both functions have the [[interval]] $[0,1]$ as their image in $\mathbb{R}$. This distinction is especially important due the fact that unique curves may possess drastically different geometric behavior in terms of self-intersection, etc., despite having identical images.
> 
> See example [[smooth curve#^c20ba3]]



# 📈Diagram
![|300](../assets/smooth_curve_R2.png)


# 🧠Intuition
Find an intuitive way of understanding this concept.



# 🌈Properties
## 🔴differentiable
### 📝Description
The word differentiable in the definition means that $\alpha$ is a correspondence which maps each $t \in I$ into a point $\alpha(t) = (x(t ), y(t ), z(t)) \in \mathbb{R}^3$ in such a way that the functions $x(t ), y(t ), z(t)$ are differentiable.

> [!info] Remark
> The $\alpha(t)$ here is a [[vector-valued function]]. Usually, $\alpha(t)$ can also be seen as a [[position vector]] since the output is a vector in $\mathbb{R}^3$.

## 🟠parameter
### 📝Definition
The $t$ of $\alpha(t)$ is the ==parameter== of the curve.

## 🟡1st derivative
### 📝Description
If we denote by $x'(t)$ the first [[derivative]] of $x$ at the point $t$ and use similar notations for the functions $y$ and $z$, the vector $(x'(t ), y'(t ), z'(t)) = \alpha'(t) \in \mathbb{R}^3$ is called the [[tangent vector]] (or [[velocity vector]]) of the curve $\alpha$ at $t$ .

> [!info] Remark
> The difference between tangent vector and velocity vector is their semantics.
> - tangent vector orients to the "geometry" sense.
> - velocity vector orients to the "physics" sense.

## 🟢trace
### 📝Definition
The [[range|image]] set $\alpha(I ) \subset \mathbb{R}^3$ is called the ==trace== of the curve $\alpha$. Often denoted as:
$$
C=\alpha(I):=\{\alpha(t):t\in I\}
$$

> [!info] Remark
> We should carefully distinguish a parametrized curve itself and its trace. They look the same but it is different!
> - parametrized curve: it is a map and "parameterization"
> - trace: it is a subset of $\mathbb{R}^3$.
> 
> See the example for clarification. [[smooth curve#^c20ba3]]


## 🔵parameterization
### 📝Description
The curve $\alpha$ sometimes is called a **parameterization** of $C$, where $C$ is  [[smooth curve#🌈Properties#🟢trace]].


## 🟣arc length
The arc length of a curve see [[arc length]].

# ⛈Characteristics
## ☁regular
See [[smooth regular curve]]

## 🌧change of orientation
### 📝Description
Given the curve $\alpha$ parametrized by [[arc length]] $s \in (a, b)$, we may consider the curve $\beta$ defined in $(−b,−a)$ by $\beta(−s) = \alpha(s)$, which has the same [[smooth curve#🌈Properties#🟢trace|trace]] as the first one but is described in the opposite direction. We say, then, that these two curves differ by a *change of orientation*.


## 🌨injective not required
### 📝Description
The differentiable curve $\alpha$ is not required to [[injective function|injective]].

### 🧠Intuition
It simply means a curve can be self-intersect.

### 🗃Example
Suppose a curve $\alpha(t)=(t^3-4t, t^2-4)$. Take $t_{1,2}=\pm2$, then $\alpha(t_1)=\alpha(t_2)=(0,0)$.
![|300](../assets/intersect_curve.svg)
> [!info] Remark
> The curve has direction. Suppose $t\in\{-\infty, \infty\}$.
> - when $t$ goes from $-\infty\to0$, $x=t^3-4t$ is negative, $y=t^2-4$ is positive. Therefore the curve goes from the 2nd [[quadrant]].
> - when $t$ goes from $0\to\infty$, $x=t^3-4t$ is positive, $y=t^2-4$ is positive. Therefore the curve goes towards the 1st [[quadrant]].


🌩
⛅
🌤
🌪
🌥
🌦

# 💫Operation
## 🌠reparameterization
### 📝Definition
A reparameterization of $\alpha : I \to\mathbb{R}^n$ is a smooth map $\beta : J \to\mathbb{R}^n$ of form $\beta = \alpha\circ\sigma$  where $\sigma: J \to I$ is a [[diffeomorphism]]. 
> [!info] Remark
> That $\sigma$ is a [[diffeomorphism]] means $\sigma$ is [[injective function|one-to-one]] and [[surjective function|onto]] (so there is an inverse map $\sigma^{−1} : J \to I$) and that $\sigma' (t) \neq 0$ for $t \in I$ (so that the map $\sigma^{−1}$ is also smooth).

### 🧠Intuition
If $\beta$ is a reparameterization of $\alpha$, then the maps $\alpha$ and $\beta$ have the **same trace** $C$. The idea of the definition is that we should think of $\alpha$ and $\beta$ as ==different ways of describing the same curve== $C$. However do Carmo avoids giving a precise definition of an (unparameterized) curve.

### 🗃Example
- 📁smooth curve reparameterization example
	- The circle $C = \{(x, y) \in \mathbb{R}^2: x^2 + y^2 = 1\}$ is the trace of the parameterized curve $\alpha : \mathbb{R}\to \mathbb{R}^2$ defined by
		- $$\alpha(\theta)=(\cos\theta,\sin\theta)=(\cos(\theta+2\pi),\sin(\theta+2\pi)).$$
	- Defined a map $\beta:\mathbb{R}\to\mathbb{R}^2$ by
		- $$\beta(t)=\left(\frac{1-t^2}{1+t^2},\frac{2t}{1+t^2}\right).$$
	- This map is a reparameterization of the restriction of $\alpha$ to the open interval $(-\pi, \pi)$ as follows:
		- $$\begin{align}(\cos(2\phi),\sin(2\phi))&=\left(\frac{\cos^2\phi-\sin^2\phi}{\cos^2\phi+\sin^2\phi},\frac{2\sin\phi\cos\phi}{\cos^2\phi+\sin^2\phi}\right)\\&=\left(\frac{1-\tan^2\phi}{1+\tan^2\phi},\frac{2\tan\phi}{1+\tan^2\phi}\right).\end{align}$$
	- Take $2\phi=\theta, t=\tan\phi=\tan(\theta/2)$, and we get $\alpha=\beta\circ\sigma$ where $\sigma:(-\pi,\pi)\to\mathbb{R}$ is defined by $\sigma(\theta)=\tan(\theta/2)$. The common trace of (the restriction of) $\alpha$ and the map $\beta$ is the punctured circle $C\textbackslash (−1, 0)$  .
	- This particular reparameterization is called the [[Weierstrass substitution]] or half angle substitution. It is one of the main techniques used to evaluate integrals in calculus.



🔮
☄
🌌
🥏
🌀


# 🗃Example
- 📁 helix
	- A [[helix]] is a differentiable curve.

- 📩 not a differentiable curve example ^665e91
	- The map $\alpha:\mathbb{R}\to \mathbb{R}^2$ given by $\alpha(t) = (t, |t|), t \in\mathbb{R}$, is not a parametrized differentiable curve, since $|t|$ is not differentiable at $t = 0$.
	- See the graph. 
		- ![|300](../assets/not_a_smooth_curve.svg)
		- Hint. There is a [[singularity|singular point]] at $t=0$ called [[cusp]].



- 🗂
- 📨
- 📂

- 📁smooth curve example ^c20ba3
	- 💬Question: What is the difference of the two distinct parametrized curves
		- $$\begin{align}\alpha(t)&=(\cos t,\sin t),\\\beta(t)&=(\cos 2t,\sin 2t)\end{align}$$ where $t\in(0-\epsilon, 2\pi+\epsilon), \epsilon>0$?
	- 🗣Answer:
		- They have the same trace which is a circle $x^2+y^2=1$.
		- But the velocity vector of the second curve is the double of the first one.
		- Their ==parameter== is different!
		- See the 1st derivative of a same point has different length.
			- ![|200](../assets/trace_is_not_map.svg)


# 🏷Categories
## 🔖special kind of curve
### 📝Description
It can happen that the parameter $t$ is already the [[arc length]] measured from some point. In this case, $ds/dt = 1 = |\alpha'(t)|$. That is, the [[velocity vector]] has constant length equal to 1.

Conversely, if $|\alpha'(t)|\equiv1$, then
$$
s=\int_{t_0}^tdt=t-t_0
$$
i.e., the $t$ is the arc length of $\alpha$ measured from some point.

#TODO I feel like this curve is special and maybe defined? I am not sure.

> [!info] Remark
> The map $\alpha$ is said to be parameterized by arc length if and only if its tangent vector always has length one.

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized