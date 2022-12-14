---
aliases: [Local Minima, local minimizer]
---

#minimum

- ![[extremum#Org Graph of Extremum]]

# 📝Definition
- $f$ has a local minimum at $x=a$ if $f(a)\leq f(x)$ for all $x$ "near $a$" (within some small distance of $a$).
- A point $x^∗$ is a local minimizer if there is a neighborhood $N$ of $x^∗$ such that $f(x^∗) ≤ f(x)$for all $x ∈ N$.

# 🧠Intuition
- Find an intuitive way of understanding this concept.

# 📈Diagram
- diagram of local minima
  ![local minima](../assets/local_minima.svg) ^8c46566653a3b380

# 🏷(Sub)Categories
## Weak local minimizer
- 📝Definition
    - copy definition from local minimizer, + when $N$​ is an open set that contains $x^*$​​ , e.g. $N=[0,2], x^*=2$​
    
- 🗃Example
    - $f(x)=2$​, where every point is a weak local minimizer
    
## Strict/Strong local minimizer
- 📝Definition
    - A point $x^∗$​​ is a strict local minimizer if there is a neighborhood $N$​​ of $x^∗$​​ such that $f(x^∗) < f(x)$​​for all $x ∈ N$ with $x\neq x^*$​​​.
    
- 🗃Example
    - 📌$f(x)=(x-2)^2$
        - ![name](../assets/strict_local_minimizer.png){:height 200, :width 200}
        
## Isolated local minimizer
- 🧠Intuition
    - isolated local minimizer $\subset$​​ strict local minimizer
    
- 🗃Example
    - 📌$f(x)=x^4cos(1/x)+2x^4$
        - ![name](../assets/Isolated_local_minimizer_1.png){:height 200, :width 200}
          ![name](../assets/Isolated_local_minimizer_2.png){:height 200, :width 200}
          ![name](../assets/Isolated_local_minimizer_3.png){:height 200, :width 200}
        - Nothing special in the beginning, but if we zoom in around 0, we can notice that the curve **oscillates** very much!! Therefore, if we think about $x_j\to0$, there are infinite points are local minimizer whose value=0. Therefore $j\to\infin$​, there are many many **strict local minimizers** but NONE of them are **isolated local minimizer**.
        
# 🐍Algorithm
- 📌Goal - Recognizing a local minimum
    - Intent
        - How to recognize a local minimum without examining all the points?
        
    - Description
        - In particular, if $f$ is twice continuously differentiable, we may be able to tell that $x^∗$ is a [[local minimizer]] (and possibly a strict local minimizer) by examining just the gradient $\nabla f(x^∗)$ and the Hessian $\nabla^2 f(x^∗)$.
        
    - Strategy or Theorem
        - The [[#^73ecf3aaa45f9292|theorems]] related to elementary [[Calculus]] , provide the foundations for [[Unconstrained Optimization]] algorithms. In one way or another, **all algorithms seek a point where** $\nabla f(·)$ vanishes.
      -
      
# ⚖Theorem
- 📌Theorems Related to Local Minimum ^73ecf3aaa45f9292
    - 📌 [[Taylor Theorem]]
    - 📌First-Order Necessary Conditions
        - This is the theorem [[First Derivative Test]] based on.
        - If $x^∗$ is a **local minimizer** and $f$ is [[continuously]] [[differentiable]] in an open neighborhood of $x^∗$, then we have:
            - $$
              \nabla f(x^∗) = 0
              $$
            
        - Fun fact: the point $x^*$ are also called [[Stationary Point]].
        
    - 📌Second-Order Necessary Conditions
        - This is the theorem [[Second Derivative Test]] based on.
        - $x^∗$ is a **local minimizer** of $f$ and $\nabla^2 f$ exists and is [[Continuous]] in an open neighborhood of $x^*$​, then we have
            - $$
              \nabla f(x^∗) = 0 \text{ and }∇^2 f(x^∗) \text{ is positive semidefinite}
              $$
            
    - 📌Second-Order Sufficient Conditions
        - $\nabla^2 f$ is **continuous** in an open neighborhood of $x^∗$ and that $∇ f(x^∗)= 0$ and $∇^2 f(x^∗)$​ is **positive definite**, then we have:
            - $$
              x^∗ \text{ is a strict local minimizer of }f
              $$
            
    - 📌Theorem 2.5
        - When $f$ is [[Convex Function]] , then we have:
            - $$
              \text{any local minimizer }x^∗ \text{ is a global minimizer of }f
              $$
            
        - if in addition $f$ is [[differentiable]] , then we have:
            - $$
              \text{any stationary point } x^∗\text{ is a global minimizer of }f
              $$
            