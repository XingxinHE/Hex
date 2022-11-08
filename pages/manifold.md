- 📝Definition
    - The name is the essence of this topic.
    - ![[Simplicial Complex#^1807d510e51c4830]]
    
- 🚀Benefit / Pros
    - In a nutshell, it is neat ingredient for **datastructure** which is easy to process and comfortable to access its "neighbor".
    
- 🌓Complement
    - [[Nonmanifold]]
    
- 🧠Intuition
    - Digest Manifold and Nonmanifold intuitively ^c9b554e7ecde4207
        - ![name](../assets/manifold_nonmanifold.png){:height 200, :width 400}
          Apparently, the left is manifold for it can be sampled any point with a cartesian $xy$ plane while the right can't. The "funky" and "chaotic" shape is not manifold.
        - ![name](../assets/manifold_nonmanifold1.png){:height 200, :width 400}
          Nonmanifold is marked with red. Others are manifold.
        
    - Digest Manifold and Nonmanifold intuitively
        - ![name](../assets/manifold_vs_nonmanifold.png){:height 150, :width 150}
        - The [[manifold]] is the boundary surface of a non-degenerate 3D solid where "*non-degenerate*" means that the solid does not have any infinitely thin parts or features such that the surface properly separates the "interior" and "exterior" of the solid.
        - Top left is with a degenerate/ [[Nonmanifold]] vertex, which is fixed in top right.
        - Bottom left is with a degenerate/ [[Nonmanifold]] edge, which is fixed in bottom right.
        
- 🏷(Sub)Categories
    - Manifold Triangle Mesh ($k=2$, [[simplicial 2-complexes]] ) ^69e2c532a6ef8467
        - 👑Importance
            - Manifold triangle mesh is of enormous importance in geometric processing and modeling.
            
        - 📝Definition
            - Requirements for a triangle mesh is manifold:
            - | simplex            | requirement                                                  | Image                                                        |
              | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
              | edges              | every edge is contained in **exactly** **2** triangles       | ![name](../assets/manifold_mesh_edge.png){:height 150, :width 150} |
              | edges(boundary)    | just **1** along the **boundary**                            | ![name](../assets/manifold_mesh_edge_boundary.png){:height 150, :width 150} |
              | vertices           | every vertex is contained in **a single “loop”** of triangles | ![name](../assets/manifold_mesh_vertices.png){:height 150, :width 150} |
              | vertices(boundary) | **a single “fan”** along the **boundary**                    | ![name](../assets/manifold_mesh_vertices_boundary.png){:height 150, :width 150} |
            
- 💫Support Operation
    - Complexity on manifold check
        - Question:
            - How hard is it to check if a given simplicial complex is manifold?
            
        - Answer
            - ($k=1$) trivial—is it a loop?
            - ($k=2$) trivial—is each link a loop?
            - ($k=3$) is each link a 2-sphere? Just check if $V-E+F = 2$ ( [Euler’s Characteristic](((634e3b2d-a1b3-4803-9236-d18373f2c133)))  )
            - ($k=4$) is each link a 3-sphere? …Well, it’s known to be in NP! [S. Schleimer 2004]
            
- ⛈Characteristics / Properties
    - Local Manifoldness
        - 📝Definition
            - A [[Continuous]] parametric surface is locally manifold at a [[Surface]] point $p$ if, for every other surface point $q$ within **a sufficiently small** sphere of radius $\delta$ around $p$, the corresponding [[pre-image]] is contained in a circle of some radius $\epsilon=O(\epsilon)$ around the pre-image of $p$.
            - A more intuitive way to express this condition is to say that the surface patch that lies within a sufficiently small $\epsilon$-sphere around $p$ is topologically equivalent ([[Homeomorphic]]) to a disk.
            - > ==**Note⚠**==: Since this second definition does not require a parameterization, it applies to implicit representations as well.
            
        - 📈Diagram
            - ![name](../assets/manifold_nonmanifold.png){:height 200, :width 400}
              A great diagram illustrates the idea of "sufficiently small".
            