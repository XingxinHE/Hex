---
aliases: []
tags:
  - ComputationalGeometry
  - geometry
---


# 📝Definition
Implicit (or volumetric) surface representation is defined to be the zero set of a scalar-valued function $F$.
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

# ⛈Characteristics
## ☁ No holes
An implicit surface does not have any [[genus|holes]] as long as the defining function $F$ is [[Continuity|continuous]]. 


## 🌧 No self-intersections
Since an implicit surface is a level set of a potential function, geometric self-intersections **cannot** occur.

🌨
🌩
⛅
🌤
🌪
🌥
🌦

# 🍂Unorganized
By convention, negative function values of F designate points inside the object and positive value points outside the object.
The zero-level isosurface S contains the points exactly on the surface, separating the inside from the outside. 