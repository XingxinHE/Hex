---
aliases: []
tags:
  - ComputationalGeometry
  - geometry
---


# 📝Definition
Implicit (or volumetric) surface representation is the following. Surface $S$ is defined to be the zero-level set of a scalar-valued function $F$.
$$
F:\mathbb{R}^3\to\mathbb{R},\text{ i.e., }S=\{x\in\mathbb{R}^3|F(x)=0\}
$$
> [!tip] Key Takeaway
> The aim of function $F$ is to map all points in space to a [[scalar]] value.

# 🎯Intent
The basic concept of *implicit* or *volumetric* representations for geometric models is to **characterize** the whole embedding space of an object by classifying each 3D point to lie either **inside, outside**, or exactly **on** the surface $S$ that bounds a solid object.

> [!tip] Key Takeaway
> From the word "characterize", we understand *implicit surface representation* is good for [[mesh reconstruction]].

# 🗃Example
**📂Define [[curve]] in implicit representation**
$$
C=\{x\in\mathbb{R}^2|F(x)=0\}\text{ with }F:\mathbb{R}^2\to\mathbb{R}
$$
- $C$: a planar curve.

**📂Define a [[unit circle]] in implicit representation**
$$
F: \mathbb{R}^2\to\mathbb{R},\quad(x,y)\mapsto\sqrt{x^2+y^2}-1
$$

# 💫Operation
## 🌠designate point inside, on, outside
By convention, the function values of $F$ designate points
- **inside** the object with **negative** value
- **outside** the object with **positive** value.
- **exactly on** the surface with the [[level set|zero-level set]] [[isosurface]] $S$ contains the points, a.k.a. **equals the constant**

🔮
☄
🌌
🥏
🌀


# ⛈Characteristics
## ☁ No holes
An implicit surface does not have any [[genus|holes]] as long as the defining function $F$ is [[Continuity|continuous]]. 


## 🌧 No self-intersections
Since an implicit surface is a [[level set]] of a potential function, geometric self-intersections **cannot** occur.

🌨
🌩
⛅
🌤
🌪
🌥
🌦


# 🤳Applicability
## [[constructive solid geometry]]

As a consequence, geometric inside/outside queries simplify to function
evaluations of F and checking the sign of the resulting value. This makes
implicit representations well suited for constructive solid geometry (CSG),
where complex objects are constructed by Boolean operations applied to
geometric primitives


# 🍂Unorganized


Instead we will first convert the point cloud sampling representation into a an implicit surface representation: where the unknown surface is defined as the level-set of some function $g: \mathbf{R}^3 \Rightarrow \mathbf{R}$ mapping all points in space to a scalar value. For example, we may define the surface $\partial \mathbf{S}$ of some solid, volumetric shape $\mathbf{S}$ to be all points $\mathbf{x} \in \mathbf{R}^3$ such that $g(x) = {\sigma}$, where we may arbitrarily set ${\sigma}=\frac12$.