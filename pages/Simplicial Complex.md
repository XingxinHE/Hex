alias:: (Abstract) Simplicial Complex, (Geometric) Simplicial Complex

- 🧠Intuition
	- Simplicial Complex = a bunch of [[simplices]].
- 📝Definition
	- ==(Geometric) Simplicial Complex==
	  A (***geometric***) simplicial complex is a *collection* of simplices where (a) the *intersection* of any two simplices is a simplex, and every face of (b) every simplex in the complex is also in the complex.
	- ==(Abstract) Simplicial Complex==
	  Let $S$ be a collection of sets. If for each set $\sigma\in S$ all subsets of $\sigma$ are contained in $S$, then $S$ is an *abstract simplicial complex*. A set $\sigma\in S$ of size $k+1$ is an (***abstract***) simplicial complex.
	- ![name](../assets/simplicial_complex.png){:height 200, :width 600}
		- 💡You can see these two as
			- the left is *with* coordinates and the right is *without* coordinates in the perspective of [torch_geometric.data.Data](https://pytorch-geometric.readthedocs.io/en/latest/modules/data.html#torch_geometric.data.Data).
			- the left as "**fabrication**" which requires everything lines up while the right as "**connectivity**" only.