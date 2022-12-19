---
aliases: []
tags:
  - GeometryProcessing
---


# 📝Definition

![|300](../assets/Mesh_reconstruction.gif)

# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🐍Algorithm
## 🐊Poisson Surface Reconstruction
This is the algorithm defined in [[📄Poisson Surface Reconstruction]].

**📝Definition**
This method states that the [[indicator function]], a function that determines which points in space belong to the surface of the shape, can actually be computed from the sampled points.

**🧠Intuition**
The key concept is that [[gradient]] of the indicator function
- $=0$, where it is *==not at== the sampled points*
- $=$ the inward surface normal, where it is *==at== the sampled points*.


**✒Notation**
More formally, suppose the collection of sampled points from the surface is denoted by $S$, each point in the space by $p_{i}$, and the corresponding normal at that point by $n_{i}$.

Then the gradient of the indicator function is defined as
$$
\triangledown g={\begin{cases}{\textbf {n}}_{i},&\forall p_{i}\in S\\0,&{\text{otherwise}}\end{cases}}
$$

**🏹Strategy**
> [!tip] tips
> The task of reconstruction then becomes a [[calculus of variations|variational problem]].

Here is a hint, since the gradient of the indicator function is $0$ when that is NOT the surface. Therefore, this is an optimization problem!! Find the function and optimize it until its gradient reaches $0$!!


**✏Solution**
To find the indicator function $\chi$ of the surface
- 1️⃣ the function $\chi$ must minimize $\lVert \triangledown \chi -{\textbf {V}}\rVert$
	-  $\textbf {V}$ is the [[vector field]] defined by the samples.
- 2️⃣ View the minimizer $\chi$ as a solution of [[Poisson's equation]] since it is a variational problem.
- 3️⃣ Have a good approximation of $\chi$ and $\sigma$ 
	- $(x,y,z)$ denotes the points
	- $\chi (x,y,z)=\sigma$ denotes the surface to be reconstructed
- 4️⃣ Use the [[Marching Cubes Algorithm]] to construct a [[triangle mesh]] from the function $\chi$


> [!info]
> Sometimes the indicator refers to infinitesimally [[mollifier]] (smoothed) indicator function.




# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized

