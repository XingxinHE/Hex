- 📝Definition
	- In general,
		- 📝Definition
			- The word "surface" can be used to denote an $(n-1)$-dimensional submanifold of an $n$-dimensional [[manifold]] .
	- In most common sense in #Mathematics ,
		- 📝Definition
			- The most common and straightforward use of the word is to denote a two-dimensional [submanifold](https://mathworld.wolfram.com/Submanifold.html) of three-dimensional [Euclidean space](https://mathworld.wolfram.com/EuclideanSpace.html).
	- In #[[Computer Graphics]],
		- 📝Definition⭐
			- The common definition of a *surface* in the context of computer graphics application is "an [orientable](((634ff995-0c5f-4c6d-bcb4-cb0669206cba))) [[Continuous]] 2D [[manifold]] embedded in $\mathbb{R}^3$.
- 🎨Representation
	- 🔭Overview
		- From a high level point of view, there are 2 major classes of surface representations:
			- parametric representation
			- implicit representation
	- 🎯Intent
		- Why does representation matter? For each specific problem in [[Geometry Processing]], we can identify a characteristic set of operations by which the computation is dominated, and hence we have to choose an appropriate representation that supports the efficient implementation of these operation.
	- 🌓Comparison
		- > ==**Note⚠**==: Both parametric and implicit representation have their particular strengths and weakness, such that for each geometric problem the better suited one should be chosen.
	- parametric representation
		- 📝Definition
			- Parametric surfaces are defined by a vector-valued parameterization function $f$ that maps a 2D parameter domain $\Omega$ to the surface $S$.
				- $$
				  f: \Omega\to S
				  $$
				- $\Omega$: the 2D parameter domain that $\Omega\subset\mathbb{R}^2$
				- $S$: the surface that $S=f(\Omega)\subset\mathbb{R}^3$.
		- 🕳Pitfalls / Cons
			- For more complex shapes, a single function is not enough to define a surface.
		- 🏹Strategy
		  id:: 6356141c-da11-4804-9162-3945ae8e9b8e
			- To solve the constraint of "a single function can't define a surface", the function domain is usually split into smaller sub-regions and an individual function(surface patch) is defined for each segment.
			- > ==**Note⚠**==: In this piecewise  definition, each function needs to approximate the given shape only **locally**, while the **global** approximation tolerance is controlled by the size and number of segments. The mathematical challenge is to guarantee a consistent transition from each patch to its neighboring ones. (That's why [[triangle mesh]] comes in)
		- 🗃Example
			- Define [[curve]] in parametric representation
				- $$
				  f: \Omega\to C \text{ with }\Omega=[a,b]\subset\mathbb{R}
				  $$
				- $C$: a planar curve.
			- Define a [[unit circle]] in parametric representation
				- $$
				  f:[0,2\pi]\to\mathbb{R}^2,\quad t\mapsto\begin{pmatrix}\cos t\\\sin t\end{pmatrix}
				  $$
	- implicit representation
		- 📝Definition
			- Implicit (or volumetric) surface representation is defined to be the zero set of a scalar-valued function $F$
				- $$
				  F:\mathbb{R}^3\to\mathbb{R},\text{ i.e., }S=\{x\in\mathbb{R}^3|F(x)=0\}
				  $$
		- 🏹Strategy
			- The analogy of implicit representation on ["segmentation"](((6356141c-da11-4804-9162-3945ae8e9b8e))) is hexahedral [[voxel]]s or tetrahedral cells.
		- 🗃Example
			- Define [[curve]] in implicit representation
				- $$
				  C=\{x\in\mathbb{R}^2|F(x)=0\}\text{ with }F:\mathbb{R}^2\to\mathbb{R}
				  $$
				- $C$: a planar curve.
			- Define a [[unit circle]] in implicit representation
				- $$
				  F: \mathbb{R}^2\to\mathbb{R},\quad(x,y)\mapsto\sqrt{x^2+y^2}-1
				  $$