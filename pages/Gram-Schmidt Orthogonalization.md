- 🎯Intent
	- Big picture of Gram-Schmidt Orthogonalization: it **alternates coordinate systems.**
- 📝Definition
	- Given a nonorthogonal set of $n$ [[linearly independent]] [[vector]]s $\Beta=\{e_1,e_2,...,e_n\}$, this algorithm produces an orthogonal set $\Beta'=\{e_1',e_2',...,e_n'\}$ such that
		- $$
		  e_i'\cdot e_j'=0, \text{whenever }i\neq j
		  $$
- 🐍Algorithm
	- A. set $e_1'=e_1$
	- B. Begin with index $i=2$
	- C. Subtract the projection of $e_i$ onto the vector $e_1',e_2',...,e_{i-1}'$ from $e_i$ and store the result in $e_i'$. That is
		- $$
		  e_i'=e_i-\sum_{k=1}^{i-1}\frac{e_i\cdot e_k'}{e_k'^2}e_k'
		  $$
	- D. If $i<n$, $i++$, back to step C.
- ⌨Sample Code
	- C++
		- Eigen
			- TODO make the following algorithm as template method
			- ``` c++
			  std::vector<Eigen::Vector3d> GramSchimitOrtho(std::vector<Eigen::Vector3d> input_vectors)
			  {
			  	std::vector<Eigen::Vector3d> ortho_vectors;
			  
			  	int amount = input_vectors.size();
			  	Eigen::Vector3d q1 = input_vectors[0];
			  	ortho_vectors.push_back(q1);
			  	for (int i = 1; i < amount; i++)
			  	{
			  		Eigen::Vector3d rhs;
			  		rhs.setZero();
			  		for (int j = 0; j < i; j++)
			  		{
			  			rhs = rhs + (input_vectors[i].dot(ortho_vectors[j].normalized()) * (ortho_vectors[j].normalized()));
			  		}
			  
			  		ortho_vectors.push_back(input_vectors[i] - rhs);
			  	}
			  
			  	return ortho_vectors;
			  }
			  ```