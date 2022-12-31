---
aliases: [quadratic function, quadratic formula]
---

# 📝Definition
- A quadratic equation is a second-order [[polynomial equation]] in a single variable $x$
  $$
  ax^2+bx+c=0, 	
  $$
  with $a\neq0$. Because it is a second-order polynomial equation, the fundamental theorem of algebra guarantees that it has two solutions. These solutions may be both real, or both complex.

# 🧠Intuition
Find an intuitive way of understanding this concept.

# ✒Notation
### Quadratic Formula
The formula giving the [[Root]]s of a quadratic equation
$$
\begin{align}
x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
\end{align}
$$

# ⛈Characteristics / Properties
- 📌Discriminant
    - $$
      \Delta = b^2-4ac
      $$
    - The discriminant is relevant to the amount of roots.
        - $\Delta>0$, 2 roots.
        - $\Delta=0$, 1 root
        - $\Delta<0$, no roots
        
# 📈Diagram
![name](../assets/name.png)

# 🏷(Sub)Categories
- 📌Monic Quadratic ^7566d53828e105d9
    - The monic quadratic is a quadratic with [[polynomial#🌈Properties#🟠Leading coefficient|leading coefficient]] equal to 1.
    - ❌ not a monic quadratic => $2x^2-3x+10$
    - ✅ is a monic quadratic => $x^2-\frac{3}{2}x+5$
    
# 💫Support Operation
- 📌Completing the Square
    - It is a technique to solve a quadratic equation.
    - Question
        - To solve $2x^2-3x+10$
        
    - Solution
        - Step 1. Change to [[#^7566d53828e105d9|monic quadratic]]
            - $$
              2x^2-3x+10=2(x^2-\frac{3}{2}x+5)
              $$
            
        - Step 2. Think about completing the square of $\frac{3}{2}$
            - $$
              2(x^2-\frac{3}{2}x+5)=2((x^2-\frac{3}{2}x+\frac{9}{16})+5-\frac{9}{16})
              $$
            
        - Step 3.
            - $$
              2(x^2-\frac{3}{2}x+\frac{9}{16}+5-\frac{9}{16})=2\bigg((x-\frac{3}{4})^2+\frac{71}{16}\bigg)
              $$
            