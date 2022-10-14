alias:: simplices

- ✒Notation
	- | Singular单数 | Plural复数 |
	  | ------------ | ---------- |
	  | Simplex      | Simplicies |
- # 📝Definition
	- (Geometric Definition) A ***k-simplex*** is the convex hull of *k+1* affinely-independent points, which also named ***vertices***.
- # 📈Diagram
	- (intuitive) From left to right, a *k-simplex* is a point, line segment, triangle, a tetrahedron...  Most of the time, we study $k\leq3$ .
	- ![name](../assets/k_simplex.png){:height 300, :width 500}
- # 🧠Intuition
	- The relation between $k$ and number of vertices
		- | k-simplex | How many vertices? | Image |
		  | ---- | ---- | ---- |
		  | 0-simplex | 1 = 0 + 1 | ![name](../assets/0_simplex.png){:height 50, :width 50} |
		  | 1-simplex | 2 = 1 + 1 | ![name](../assets/1_simplex.png){:height 100, :width 100} |
		  | 2-simplex | 3 = 2 + 1 | ![name](../assets/2_simplex.png){:height 100, :width 100} |
		  | 3-simplex | 4 = 3 + 1 | ![name](../assets/3_simplex.png){:height 100, :width 100} |
- # 🏷Categories
	- ## Probability Simplex
		- 📝Definition
			- The *standard n-simplex* is the collection of points which is also known as ***probability simplex***.
		- 🧠Intuition
			- Probability Simplex is just an alias for $n$-simplex since it can be used in probability...
		- 📈Diagram
			- ![name](../assets/Probability_Simplex.png){:height 200, :width 200}
			- The above diagram is a *2-simplex* which lies in $\mathbb{R}^3$. Imagine all the possibilities of this simplex... No matter how, they all lie in the triangle $\sigma$ above. Therefore, it is called **probability simplex**.
- # 🧬Related Elements
	- [[Simplicial Complex]]
- # 🛠Analogy
	- Research shows connecting what already know to new concepts and ideas sharpens their focus and deepens their understanding.
	- 📌==Simplex== and ==Simplicial Complex== in Rhino and PyTorch
	  id:: 6348ad24-5fee-4b6f-838b-64d71ff6df08
		- | Discrete Differential Geometry | Rhino/Grasshopper Software | PyTorch Geometric                                            |
		  | ------------------------------ | -------------------------- | ------------------------------------------------------------ |
		  | 0-simplex                      | A point                    | ```x = torch.tensor([0,0,0], dtype=torch.float)```           |
		  | 1-simplex                      | An edge                    | ```edge_index = torch.tensor([[0, 1], [1, 0]], dtype=torch.long)``` |
		  | 2-simplex                      | A triangle                 | /                                                            |
		  | Abstract Simplicial Complex    | NA.                        | ```torch_geometric.data.Data```                              |
		  | Geometric Simplicial Complex   | `Rhino.Geometry.Mesh`      | `read_ply` or `read_obj`                                     |
		- 可以把0-simplex, 1-simplex和2-simplex理解为构建几何世界的基本元素，(只有一个点才是0-simplex，2个点是simplicial complex)。而把基本元素拼凑起来才是Mesh。
- # 🗃Example
	- 📌Small quiz on simplices
		- 💬Question: What are all the simplices?
		- 📈Diagram
			- ![name](../assets/simplices.png){:height 200, :width 200}
		- ✏Answer: {6,7,9} {7,10,8} {2,3} {3,4} {4,5} {0} {1} {6,7} {7,9} {9,6} {7,8} {8,10} {10,7} {2} {3} {4} {5} {6} {7} {8} {9} {10} - simply write down all the **vertices**, **edges** and **faces**.
	- {{embed ((ec6b335c-c89b-49d0-b5d2-86520b26e5d9))}}
	- {{embed ((63477037-0c5c-4886-9751-b67f7aa1de7b))}}