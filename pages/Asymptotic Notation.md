# 📝Definition
- Asymptotic notations are the mathematical notations used to describe the running time of an [[Algorithm]] when the input tends towards a particular value or a limiting value.

# 🏷(Sub)Categories
We use the following symbols as asymptotic notation.
- [[Mathematical Symbol#^e5de0ee81ea94f06|$\Omicron$]] - upper bounds
- [[Mathematical Symbol#^f00a3b8036b6ee85|$\Omega$]] - Lower bounds
- [[Mathematical Symbol#^301f09c6811faf5f|$\Theta$]] - tight bounds
- [[Mathematical Symbol#^5ae9856c32d66ea3|$\in$]] - is
- $=$ - order

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.
- 📌an example of Asymptotic Notation
    - For the following equations
        - $T(n)=\Omicron(n^{100})$
        - $T(n)=\Omega(n^3)$
        - $T(n)=\Theta(n^3)$
        
    - It literally means
        - $T(n)$ grows asymptotically **no faster** than $n^{100}$
        - $T(n)$ grows asymptotically **no slower** than $n^3$
        - $T(n)$ grows asymptotically **as fast as** $n^3$
        
- 📌Asymptotic Notation Exercise
    - Exercise 1
        - 📄 **Question**:
            - Find a simple, tight asymptotic bound for $\Big(\begin{matrix}n\\6006\end{matrix}\Big)$.
            
        - ✏**Solution:**
            - Definition yields $n(n-1)...(n-6005)$ in the numerator (a degree 6006 polynomial) and 6006! in the denominator (constant with respect to $n$). So:
              $$
              \Big(\begin{matrix}n\\6006\end{matrix}\Big)=\Theta(n^{6006})
              $$
            
    - Exercise 2
        - 📄 **Question**:
            - Find a simple, tight asymptotic bound for $\log_{6006}\Big((\log(n^{\sqrt{n}}))^2\Big)$
            
        - ✏**Solution:**
            - First, we have rules for exponent and logarithm rules:
              $$
              \begin{align}
              \log ab&=\log a+\log b\\
              \log(a^b)&=b\log a\\
              \log_ab&=\log b/\log a
              \end{align}
              $$
              Therefore, we have:
              $$
              \begin{align}
              \log_{6006}\Big((\log(n^{\sqrt{n}}))^2\Big) &=\\
              &=\frac{\log(\log(n^{\sqrt{n}})^2)}
              {\log6006}
              \\
              &=\frac{2\log(\log(n^{\sqrt{n}}))}
              {\log6006}
              \\
              &=\frac{2}
              {\log6006}\log(\log(n^{\sqrt{n}}))
              \\
              &=\frac{2}
              {\log6006}\log(\sqrt{n}\log(n))
              \\
              &\approx\log(\sqrt{n}\log(n))
              \\
              &\approx\Theta(\log n^{1/2}+\log\log n)
              \\
              &\approx\Theta(\log n)
              \end{align}
              $$
            - For $\approx$, we should know:
              $$
              \frac{2}{\log6006}=\frac{2}{3.77}\approx1
              \\
              \log\log n\approx0
              \\
              \log n^{1/2}=\frac{1}{2}\log n\approx\log n
              $$
            
    - Exercise 3
        - 📄 **Question**:
            - Show that $2^{n+1}\in\Theta(2^n)$, but that $2^{2^{n+1}}\not\in\Omicron(2^{2^n})$
            
        - ✏**Solution:**
            - $\Theta$, tight bound, **as fast as**
            - $\Omicron$, upper bound, **no faster than**
            - Therefore, we have to prove
            - ​	A. $2^{n+1}$ **can** grow faster **or** slower than $2^n$:
                - Because $2^{n+1}=2\cdot2^n$, therefore $2^{n+1}$ bigger than $2^n$
                
            - ​	B. $2^{2^{n+1}}$ **MUST** grow faster than $2^{2^n}$:
                - Because $2^{2^{n+1}}=2^{2^n}\cdot2^2$, therefore $2^{2^{n+1}}$ bigger than $2^{2^n}$
                
    - Exercise 4
        - 📄 **Question**:
            - Show that $(\log n)^a=\Omicron(n^b)$ for all positive constants $a$ and $b$.
            
        - ✏**Solution:**
            - $\Omicron$, upper bound, **no faster than**
            - Therefore, to prove this, we have to say $(\log n)^a<n^b$ is always true. That said, if $n$ approaches $\infin$, this is true.
            - Goal of proof:
              $$
              \frac{n^b}{(\log n)^a} \to\infin\quad,\text{as } n\to\infin
              $$
              To prove:
              $$
              \begin{align}
              \lim_{n\to\infin}\log(\frac{n^b}{(\log n)^a})&=\lim_{n\to\infin}(b\log n-a\log\log n)\\
              &=\lim_{x\to\infin}(bx-a\log x)\\
              &=\infin
              \end{align}
              $$
            
    - Exercise 5
        - 📄 **Question**:
            - Show that $(\log n)^{\log n}=\Omega(n)$
            
        - ✏**Solution:**
            - Since $m^m=\Omega(2^m)$, so setting $n=2^m$ completes the proof.
            
    - Exercise 6
        - 📄 **Question**:
            - Show that $(6n)!\not\in\Theta(n!)$, but that $\log((6n)!)\in\Theta(\log(n!))$
            
        - ✏**Solution:**
            - Sterling's approximation:
              $$
              n!=\sqrt{2\pi n}\Big(\frac{n}{e}\Big)^n\Bigg(1+\Theta(\frac{1}{n})\Bigg)
              $$
              Substituting in $6n$ gives an expression that is at least $6^{6n}$ larger than the original. But taking the logarithm of Sterling’s gives $\log(n!) = \Theta(n \log n)$, and substituting in $6n$ yields only constant additional factors.
            
# 🧠Intuition  
Find an intuitive way of understanding this concept.

# 🧮Expression  
$$
\begin{align}
f(x)&=
\end{align}
$$

# 📈Diagram  
![name](../assets/name.png){:height 300, :width 300}

# ✒Descriptive Explanation  
A narrative... a descriptive words subject on the concept... 描述性解释…

# 👑Importance
No matter good or bad, this subject plays an important role...

# 🌓Complement  
What is the complement of this subject? e.g. vector-covector, constructor-destructor

# 📏Proof   
To prove something...

# 🤳Applicability  
What are the situations in which this subject can be applied?

# 🧪Composition  
What kind of stuffs composite this subject?

# ⚖Laws  
The laws related to this math concepts.

# 🎯Intent  
A short description what does this thing do?

# 🌱Related Elements  
The closest pattern to current one, what are their differences?

# 🚀Benefit / Pros
 A scenario that illustrates the benefit this object provides.

# ⌨Sample Code
 Code fragments

# 🔎Implementation
 The code or technical stuffs implement this.

# 🕳Pitfalls / Cons
Be aware of the pitfalls when using this stuffs... (especially considering edge cases)

# 📋Prerequisite
Some techniques and objects only work under certain condition.

# ⛈Characteristics / Properties
What...

# 🐍Algorithm
Algorithm relates to this stuff..

# 🥼Expert's Advice
See what experts addressed.

# 🧱Structure
Any other hierarchical issues?
