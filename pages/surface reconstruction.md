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

**✏Solution**
- Let's start with 2 assumptions:
	- 1️⃣ we know how to compute the $\nabla g$ at each node location $\mathbf{x}_{i,j,k}$ on the regular grid.
	- 2️⃣ the sample points $\mathbf{P}$ all lie at grid nodes. meaning:
		- $\exists \mathbf{x}_{i,j,k} = \mathbf{p}_{\ell}$
- However, these assumptions are not realistics and we have to "relax" a bit.
- We make another logical induction.
	- If our points $\mathbf{P}$ lie at grid points, then our corresponding normals $\mathbf{N}$ also live at grid points.
- By introducing the vector, we now have ==3== objects.
	- 1️⃣the gradient of function $g$
	- 2️⃣the surface normal
	- 3️⃣zero gradient away from the surface
- We link the preceding 3 objects in equations.
	- $$\nabla g(\mathbf{x}_{i,j,k})=\mathbf{v}_{i,j,k}:=\begin{cases}\mathbf{n}_{\ell}\quad&\text{if }\exists\mathbf{p}_{\ell}=\mathbf{x}_{i,j,k}\\\begin{pmatrix}0\\0\\0\end{pmatrix}\quad&\text{otherwises.}\end{cases}$$
	- > [!tip]
	   > This is a [[vector-valued function]].
	    > The gradients, normals, and zero-vectors are 3-dimensional. (e.g. $\nabla g\in\mathbb{R}^3$)
- From here, we try to recall our objective from the beginning.
	- Our objective: the value of $g$ for each grid node.
	- Right now: 3 equations for each grid node
- Therefore, the preceding equations are over determined.
- Hence, we turn this problem into optimization which minizes the error of the equation:
	- $$\lVert\nabla g(\mathbf{x}_{i,j,k})-\mathbf{v}_{i,j,k}\rVert^2$$
	- this is the error for ==1== grid node
- We will treat the error of each grid location equally by minimizing the sum over all grid locations.
	- $$\min_{g}\sum_i\sum_j\sum_k\frac{1}{2}\lVert\nabla g(\mathbf{x}_{i,j,k})-\mathbf{v}_{i,j,k}\rVert^2$$
	- 。。
- Since we are working on [[regular grid]] and we can take advantage from that:
	- > [!tip]
	  > [[finite difference method]] is a good fit to approximate the gradient $\nabla g$ on the grid.
- Now the relevant stuffs are all set. Then we turn to $g$.
	- > [!question]
	  > What is $g$ exactly? How we can compute it?
	- We can compute the approximation of the $x,y,z$ components of $\nabla g$ via a [[Sparse Matrix]] multiplication of a "gradient matrix" $\mathbf{G}$ and our unknown grid values $\mathbf{g}$.
- The minimization problem now turns to
	- $$\min_{g}\frac{1}{2}\lVert\mathbf{Gg}-\mathbf{v}\rVert^2$$
	- or equivalently expanding to $$\min_{g}\frac{1}{2}\mathbf{g}^T\mathbf{G}^T\mathbf{Gg}-\mathbf{g}^T\mathbf{G}^T\mathbf{v}+\text{constant}$$
- This is a quadratic "energy" function of variables of $\mathbf{g}$, its minimum occurs when an infinitesmal change in $\mathbf{g}$ produces no change in the energy.
	- $$\frac{\partial}{\partial g}\frac{1}{2}\mathbf{g}^T\mathbf{G}^T\mathbf{Gg}-\mathbf{g}^T\mathbf{G}^T\mathbf{v}=0$$
- Applying this derivative gives us a sparse system of linear equations:
	- $$\mathbf{G}^T\mathbf{Gg}=\mathbf{G}^T\mathbf{v}$$
- We can solve this by sparse solver.





# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized

