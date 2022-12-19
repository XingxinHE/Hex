# 📝Definition
- Parametric surfaces are defined by a vector-valued parameterization function $f$ that maps a 2D parameter domain $\Omega$ to the surface $S$.
	- $$
	  f: \Omega\to S
	  $$
	- $\Omega$: the 2D parameter domain that $\Omega\subset\mathbb{R}^2$
	- $S$: the surface that $S=f(\Omega)\subset\mathbb{R}^3$.

> [!caution] caution
> Generating a parametric surface parameterization $f$ can be very complex, since the parameter domain $\Omega$ has to match the topological and metric structure of the surface $S$.



# 🚀Benefit / Pros
Enables the reduction of many 3D problems on the surface $S$ to 2D problems in the parameter domain $\Omega$

# 🩹Cons
The weak points are
- [[surface#💫Operation#Modification]]
- [[surface#💫Operation#Query]]
Because not only the parameterization but also the domain $\Omega$ has to be adjusted accordingly.

# 🗃Example
- Define [[curve]] in parametric representation
	- $$
	  f: \Omega\to C \text{ with }\Omega=[a,b]\subset\mathbb{R}
	  $$
	- $C$: a planar curve.
	
- Define a [[unit circle]] in parametric representation
	- $$
	  f:[0,2\pi]\to\mathbb{R}^2,\quad t\mapsto\begin{pmatrix}\cos t\\\sin t\end{pmatrix}
	  $$

# 🌓Complement
[[implicit surface representation]]

