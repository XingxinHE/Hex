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

# ✒Notation
The implicit function $F$ for a given surface $S$ is *not uniquely determined* since, e.g., any scalar multiple $\lambda F$ yields the same zero-set. However, the most common and most natural representation is the so-called [[signed distance function]].
$$
f(x)=\begin{cases}
d(x,\partial\Omega)\quad&\text{if }x\in\Omega\\
-d(x,\partial\Omega)\quad&\text{if }x\in\Omega^c
\end{cases}
$$
It maps each 3D point $x$ to its signed distance $d(x)$ from the surface $S$:
- the **absolute value** $|d(x)|$ measures the **distance** of $x$ to $S$
- the **sign** indicates whether the point $x$ is inside or outside of the solid bounded by $S$.

# 🌓Complement
[[parametric surface representation]]

# 🎯Intent
The basic concept of *implicit* or *volumetric* representations for geometric models is to **characterize** the whole embedding space of an object by classifying each 3D point to lie either **inside, outside**, or exactly **on** the surface $S$ that bounds a solid object.

> [!tip] Key Takeaway
> From the word "characterize", we understand *implicit surface representation* is good for [[surface reconstruction]].

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
The following operations are all related to the values of $F$.

## 🌠designate point inside, on, outside
By convention, the function values of $F$ could be used as an operation to designate points
- **inside** the object with **negative** value
- **outside** the object with **positive** value.
- **exactly on** the surface with the [[level set|zero-level set]] [[isosurface]] $S$ contains the points, a.k.a. **equals the constant**

## 🔮deformation
Implicit surfaces can be deformed by tuning the function values of $F$ locally.
- value **decreasing** (= *growing*)
- value **increasing** (= *shrinking*)

> [!Hint] Hint
> Since the structure of $F$ (e.g., the voxel grid) is independent from the topology of the level-set surface, we can easily change the surface topology and connectivity.



# ⛈Characteristics
## ☁ No holes
An implicit surface does not have any [[genus|holes]] as long as the defining function $F$ is [[continuity|continuous]]. 


## 🌧 No self-intersections
Since an implicit surface is a [[level set]] of a potential function, geometric self-intersections **cannot** occur.




# 🧀Applicability
## 🍞[[constructive solid geometry]]
**Because🚩**:
The geometric inside/outside queries can be simplified to function evaluations of $F$ and checking the sign of the resulting value.

**Therefore✔️**:
This makes implicit representations well suited for constructive solid geometry (CSG), where complex objects are constructed by Boolean operations applied to geometric primitives.


# 🩹Cons
There are shortages for implicit surface.
**1️⃣Points generation**
Hard to generate sample points on an implicit surface
**2️⃣[[geodesic]]**
Hard to find geodesic neighborhoods.
**3️⃣[[rendering]]**
Relatively difficult to render the surface.
**4️⃣[[texture mapping]]**
It is very difficult to consistently paste textures onto evolving implicit surfaces since it does not provide any means of parameterization.

# 🎶 Data Structures
The most common spatial data structures for implicit surface representations are
- regular grids
- adaptive data structures



# 🌱Related Elements
![[indicator function#🌱Related Elements#🍎indicator function vs. implicit surface representation implicit surface functions vs. signed distance function]]



# 🍂Unorganized


