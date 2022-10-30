# Weierstrass Approximation Theorem
- 🧠Intuition
    - This theorem essentially states: "Every [[continuous]] function on $[a, b]$ is almost a [[polynomial]]."
    
- 📝Definition
    - If $f\in C([a, b])$, there exists a sequence of polynomials $\{P_n\}$ such that
        - $$
          P_n\to f\quad\text{uniformly on }[a,b]
          $$
        
- 📏Proof
    - 🏹Strategy
        - The idea of the proof is to choose a suitable sequence of polynomials $\{Q_n\}_n$ such that $Q_n$ behaves like a [[Dirac delta function]] as $n \to \infty$.
        - Then, the sequence of polynomials $P_n(x) = \int_0^1 Q_n(x-t)f(t)\,\mathrm dt$ converges to $f(x)$ as $n\to \infty$.
        
    - Notice that we only need to consider $a = 0$ and $b=1$, with $f(0) = f(1) = 0$.
    - If we prove this case, then for a general
        - $$
          \tilde{f}\in C([0,1])
          $$
        
    - $\exists$(exists) a sequence of polynomials
        - $$
          P_n(x) \to \tilde{f}(x) - \tilde{f}(0) - x(\tilde{f}(1) -  \tilde{f}(0)) \text{~~uniformly.}
          $$
        
    - Hence
        - $$
          \tilde{P}_n(x)= P_n(x) + \tilde{f}(0) + x(\tilde{f}(1) - \tilde{f}(0))\to \tilde{f}(x) \text{~~uniformly.}
          $$
        