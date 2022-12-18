
# 📝Definition
If a function $f(x)$ <u>approaches</u> some value $L$ as $x$ approaches $a$ from <u>both</u> *the right and the left*, then the limit of $f(x)$ exists and equals $L$.
# 🧪Composition
Limit is a limit only both of the following exist:
- [[Right-hand limit]]
- [[Left-hand limit]]

# 🧠Intuition
Find an intuitive way of understanding this concept.
- 📌Magic of Limit by adding $\lim_{b\to a}$ ^e75639e62ab26e7a
    - Math is amazing, [[Derivative#^c9a25148f62eaeda|these different interpretation]] somehow are correlated altogether!! If we were speaking in the philosophy of "limit", everything is different and fun!
    - $$
      \begin{align}
      \text{geometric: }&  &\text{slope of secant line}\quad&\text{---}\lim_{b\to a}\text{-->} &\text{slope of tangent line}\\
      \text{symbolic: }&   &\frac{f(b)-f(a)}{b-a}\quad&\text{---}\lim_{b\to a}\text{-->} &f'(a)\\
      \text{physical: }&   &\text{average rate of change}\quad&\text{---}\lim_{b\to a}\text{-->} &\text{instantaneous rate of change}\\
      \end{align}
      $$
    
# 🧮Expression
If
$$
\lim_{x\to a^+}f(x)=\lim_{x\to a^-}f(x)=L
$$
then
$$
\lim_{x\to a}f(x)=L
$$
Alternatively,
$$
f(x)\to L \quad \text{as} \quad x\to a
$$
Remember that $x$ is <u>approaching</u> $a$ but does **not equal** $a$.
# 📈Diagram
📌One table summarize limit

| Index | Right-hand limit | Left-hand limit | R & L                                        | Example                                                      | Image                                          |
| ----- | ---------------- | --------------- | -------------------------------------------- | ------------------------------------------------------------ | ---------------------------------------------- |
| 1     | exist✔           | exist✔          | $=$✔exist and equal                          | $f(x)=x^2$<br>looks at $x=0$                                 | ![name](../assets/image-20220203104207473.png) |
| 2     | exist✔           | exist✔          | $\neq$❌exist but not equal                   | $f(x) = \frac{\sqrt{(3-5x+x^3+x^2)}}{(x-1)}$<br>looks at $x=1$ | ![name](../assets/image-20220203110211830.png) |
| 3     | not exist❌       | not exist❌      | ❌$L$&$R$ both blows up to $\pm\infty$        | $f(x)=\frac{1}{x}$<br>looks at $x=0$                         | ![name](../assets/image-20220203104105031.png) |
| 4     | not exist❌       | not exist❌      | ❌oscillates and never settle down to a value | $f(x)=\sin(13/x)$<br>looks at $x=0$                          | ![name](../assets/image-20220203113840991.png) |
    
# 🤳Applicability
There are many application taking advantages from limit.
- To do an asymptotics, you can see here
    - ((63076a15-0dee-48d0-9112-fe2b1af3d855))
    
# ⚖Laws
Suppose:
$$
\lim_{x\to a}f(x)=L,\quad \lim_{x\to a}g(x)=M
$$
Then we get the following Limit Laws:
- 📌Limit Law for Addition
  $$
  \lim_{x\to a}[f(x)+g(x)]=L+M
  $$
- 📌Limit Law for Subtraction
  $$
  \lim_{x\to a}[f(x)-g(x)]=L-M
  $$
- 📌Limit Law for Multiplication
  $$
  \lim_{x\to a}[f(x)\cdot g(x)]=L\cdot M
  $$
- 📌Limit Law for Division ^edbac3c2139a3386
    - For:
      $$
      \lim_{x\to a}\frac{f(x)}{g(x)}
      $$
    - If:
      $$
      \lim_{x\to a}f(x)=L\quad\text{and } \lim_{x\to a}g(x)=M
      $$
    - then:
        - Case 1: If $M\neq0,\text{then }\lim_{x\to a}\frac{f(x)}{g(x)}=\frac{L}{M}$ ^7cc15ec71cb09eeb
        - Case 2: If $M=0,\text{but }L\neq0,\text{then }\lim_{x\to a}\frac{f(x)}{g(x)}$ [[DNE]] ^49b7957ba6801a3f
        - Case 3: If both $M=0$ and $L=0$ ^3acaa316f6d58634
            - then $\lim_{x\to a}\frac{f(x)}{g(x)}$ might be exist, or it might not exist. There are 2 strategies to solve this in general:
                - Use [[Factorization]]. More work is necessary to determine whether the last type of limit exists, and what it is if it does exist.
                - Use [[L'Hôpital's Rule]] to solve.
                
# 🗃Example
- 📌example covering [[DNE]], [[Left-hand limit]], and [[Right-hand limit]]. ^eb759c09775a3ef2
    - the graph is the following
      ![name](../assets/images_u0lim1_estlimits.svg){:height 256, :width 456}
    - identify the continuity at $x=-2, x=1, x=3$.
    - for $x=-2$
        - left-hand limit is
          $$
          \lim_{x\to(-2)^-}f(x)=3
          $$
        - right-hand limit is
          $$
          \lim_{x\to(-2)^+}f(x)=1
          $$
        - therefore the left and right limit don't match, it is
          $$
          \lim_{x\to(-2)}f(x)=DNE
          $$
        - but at this point, $f(-2)$ exist, the blue dot is solid
          $$
          f(-2)=2
          $$
        
    - for $x=1$
        - left-hand limit is
          $$
          \lim_{x\to1^-}f(x)=2
          $$
        - right-hand limit is
          $$
          \lim_{x\to1^+}f(x)=2
          $$
        - therefore the left and right limit matched, and it is
          $$
          \lim_{x\to1}f(x)=2
          $$
        - but at this point, $f(1)=DNE$ , the blue dot is hollow
          $$
          f(1)=DNE
          $$
        
    - for $x=3$
        - left-hand limit is
          $$
          \lim_{x\to3^-}f(x)=DNE
          $$
        - right-hand limit is
          $$
          \lim_{x\to3^+}f(x)=1
          $$
        - therefore the left and right limit don't match, and it is
          $$
          \lim_{x\to3}f(x)=DNE
          $$
        - but at this point, $f(3)=1$, the blue dot is solid.
          $$
          f(3)=1
          $$
        
- 📌example that [[Left-hand limit]] and [[Right-hand limit]] do not have to agree ^ce329b5cb925a1c0
    - The following function demonstrates the left-hand limit and right-hand limit may not be equal at $x=1$.
    - $$
      f(x) = \frac{\sqrt{(3-5x+x^3+x^2)}}{(x-1)}
      $$
    - To calculate the limit, we can approaches the value as follow.
        - from left
          $$
          L\begin{cases}x=0\\x=0.5\\x=0.9\\x=0.99\end{cases}
          $$
        - from right
          $$
          R\begin{cases}x=2\\x=1.5\\x=1.1\\x=1.01\end{cases}
          $$
        - therefore the left and right don't agree
        
    - Here it is a diagram
      ![image.png](../assets/image_1661521873219_0.png){:height 105, :width 165}
    
- 📌example of [[Floor Function]], which has very interesting characteristics on limit
    - here is the diagram
      ![floor function](../assets/floor_function.svg){:height 105, :width 165}
    - the limit is quite fun
      $$
      \begin{align}
      \lim_{x\to2^-}\lfloor x\rfloor&=1\\
      \lim_{x\to2^+}\lfloor x\rfloor&=2\\
      \lim_{x\to2}\lfloor x\rfloor&=DNE\\
      \lfloor2\rfloor&=2
      \end{align}
      $$
    
- 📌example of using smart [[algebraic]] trick to solve limit ^2ee5612e3aaaf388
    - Solve the limit of
      $$
      \lim_{x\to1}\frac{x^{10}-1}{x^2-1}
      $$
    - Solution
        - the limit is with [[indeterminate form]] when $x=1, \frac{x^{10}-1}{x^2-1}=\frac{0}{0}$
        - the trick is divide $x-1$ on numerator and denominator and we got
        - $$
          \lim_{x\to1}\frac{x^{10}-1}{x^2-1}=\lim_{x\to1}\frac{(x^{10}-1)/(x-1)}{(x^2-1)/(x-1)}
          $$
        - see the numerator first
            - let $f(x)=x^{10}-1$, therefore $f(1)=0$
            - hence the numerator can be written like so
            - $$
              \frac{x^{10}-1-0}{x-1}=\frac{f(x)-f(1)}{(x-1)}
              $$
            - and this is exactly the definition of $f'(1)$
            - we know that $f'(x)=10x^9$, and so $f'(1)=10$
            
        - similarly, we can see the denominator
            - let $g(x)=x^2-1$
            - ...
            - $g'(x)=2x$
            
        - combine all the information we can have
          $$
          \lim_{x\to1}\frac{x^{10}-1}{x^2-1}=\lim_{x\to1}\frac{(x^{10}-1)/(x-1)}{(x^2-1)/(x-1)}=\lim_{x\to1}\frac{f'(x)}{g'(x)}=\lim_{x\to1}\frac{10x^9}{2x}=\frac{10}{2}=5
          $$
        
- 📌example using [[#Laws|limit laws]] to calculate the limit
    - Suppose that we have 3 functions:
      $$
      \begin{align}
      \lim_{x\to-1}f(x)&=0\\
      \lim_{x\to-1}g(x)&=17\\
      \lim_{x\to-1}h(x)&=0
      \end{align}
      $$
    - Then we have:
      $$
      \begin{align}
      \lim_{x\to-1}g(x)h(x)&=0\\
      \lim_{x\to-1}\frac{g(x)}{f(x)}&=DNE\\
      \lim_{x\to-1}f(x)+g(x)+h(x)&=17\\
      \lim_{x\to-1}\frac{f(x)}{h(x)}&=\text{Cannot be determined based on the information given}\\
      \lim_{x\to-1}\frac{f(x)+h(x)}{g(x)}&=0
      \end{align}
      $$
    
- 📌example on solving the cases of [[#^edbac3c2139a3386|limit law division]]
    - example on solving [[#^7cc15ec71cb09eeb|case 1]]
        - $$
          \begin{align}
          \lim_{x\to2}\frac{1/x+x^2}{x-3}&=\frac{4.5}{-1}=-4.5\quad\text{(Case 1)}\\
          \end{align}
          $$
        
    - example on solving [[#^49b7957ba6801a3f|case 2]]
        - $$
          \begin{align}
          \lim_{x\to0^+}\frac{2\cos x+1}{x^2+x}&=\frac{2\times1+1}{0+0} = DNE\quad\text{(Case 2)}\\
          \end{align}
          $$
        
    - example on solving [[#^3acaa316f6d58634|case 3]], here using [[L'Hôpital's Rule]] is much simpler. But we use [[Factorization]] for learning purpose.
        - example 1
          $$
          \begin{align}
          \lim_{x\to2}\frac{12/x-3x}{2-3x+x^2}&=-6\quad\text{(Case 3, elaborate👇)}\\
          &=\lim_{x\to2}\frac{x(12/x-3x)}{x(2-3x+x^2)}\\
          &=\lim_{x\to2}\frac{12-3x^2}{x(x^2-3x+2)}\\
          &=\lim_{x\to2}-\frac{3x^2-12}{x(x^2-3x+2)}\\
          &=\lim_{x\to2}-\frac{3(x^2-4)}{x(x^2-3x+2)}\\
          &=\lim_{x\to2}-\frac{3(x+2)(x-2)}{x(x-1)(x-2)}\\
          &=\lim_{x\to2}-\frac{3(x+2)\cancel{(x-2)}}{x(x-1)\cancel{(x-2)}}\\
          &=\lim_{x\to2}-\frac{3(2+2)}{2(2-1)}=-6
          \end{align}
          $$
        - example 2
          $$
          \begin{align}
          \lim_{x\to3}\frac{2x^2-10x+12}{x^3-6x^2+9x}&=\lim_{x\to3}\frac{2(x^2-5x+6)}{x(x^2-6x+9)}\\
          &=\lim_{x\to3}\frac{2(x-2)(x-3)}{x(x-3)^2}\\
          &=\lim_{x\to3}\frac{2(x-2)}{x(x-3)}\\
          &=\lim_{x\to3}\frac{2(3-2)}{3(3-3)}\\
          &=\lim_{x\to3}\frac{2\times1}{0}\\
          \text{therefore, the result is }DNE
          \end{align}
          $$
        - example 3
          $$
          \begin{align}
          \lim_{x\to0}\frac{3x^3+x^2}{x^3+x^2+x}&=\lim_{x\to0}\frac{x^2(3x+1)}{x^2(x+1+\frac{1}{x})}\\
          &=\lim_{x\to0}\frac{3x+1}{x+1+\frac{1}{x}}\\
          &=\lim_{x\to0}\frac{3\times0+1}{0+1+\frac{1}{0}}\\
          &=\lim_{x\to0}\frac{1}{1+\infin}\\
          &=\text{because denominator is + infinity, therefore the whole is 0}\\
          &=0
          \end{align}
          $$
        - example 4
          $$
          \begin{align}
          \lim_{x\to-1}\frac{2x^2+7x+5}{x+1} &= \lim_{x\to-1}\frac{2(x^2+\frac{7}{2}x+\frac{5}{2})}{x+1}\\
          &= \lim_{x\to-1}\frac{2(x+1)(x+\frac{5}{2})}{x+1}\\
          &= \lim_{x\to-1}\frac{2\cancel{(x+1)}(x+\frac{5}{2})}{\cancel{x+1}}\\
          &= \lim_{x\to-1}2(-1+\frac{5}{2})=3\\
          \end{align}
          $$
        

# 🌱Related Elements
 The closest pattern to current one, what are their differences?
- ![[Continuity#^94aefd834de51c3c]]
# 🧾 Cheat Sheet
**📌 Limit Properties**
Assume that $\lim_{x \to x_0}f(x)$ and $\lim_{x \to x_0}g(x)$ exists and that $c\in\mathbb{R}$, then:
$$
\begin{align}
\text{(i)}\quad&\displaystyle\lim_{x \to x_0}[cf(x)] = c\lim_{x \to x_0}f(x)\\
\text{(ii)}\quad&\displaystyle\lim_{x \to x_0}[f(x) \pm g(x)] = \lim_{x \to x_0}f(x) \pm \lim_{x \to x_0} g(x)\\
\text{(iii)}\quad&\displaystyle\lim_{x \to x_0}[f(x)g(x)] = \lim_{x \to x_0}f(x) \lim_{x \to x_0}g(x)\\
\text{(iv)}\quad&\displaystyle\lim_{x \to x_0}\left[\frac{f(x)}{g(x)}\right] = \frac{\displaystyle\lim_{x \to x_0}f(x)}{\displaystyle\lim_{x \to x_0}g(x)}, \lim_{x \to x_0}g(x) \neq 0\\
\text{(v)}\quad&\displaystyle\lim_{x \to x_0}[f(x)]^n = \left[\lim_{x \to x_0}f(x)\right]^n\\
\text{(vi)}\quad&\displaystyle\lim_{x \to x_0}\left[\sqrt[n]{f(x)}\right] = \sqrt[n]{\lim_{x \to x_0}f(x)}\\
\text{(vii)}\quad&\displaystyle\lim_{x \to x_0}x = x_0\\
\end{align}
$$
**📌 Chain Rule**
Let $f$ and $g$ be continuous, and given $\lim_{x \to x_0}f(g(x))$ of composed function we can solve $\lim_{x \to x_0}g(x) = y_0$, then:
$$\lim_{x \to x_0}f(g(x)) = \lim_{y \to y_0}f(y)$$
**📌 Exponential Rule**
Let $f$ and $g$ be continuous, where $\lim_{x\to x_0}f(x) = f(x_0) > 0$ and $\lim_{x\to x_0}g(x) = g(x_0)$ (where both limits exists), then:

$$\lim_{x \to x_0}f(x)^{g(x)} = f(x_0)^{g(x_0)}$$

**📌 Root Trick**
$$
\lim_{x \to x_0} \sqrt{f}-g = \lim_{x \to x_0} \sqrt{f}- g \cdot \frac{\sqrt{f}+g}{\sqrt{f}+g}
$$

**📌 E-Log Trick**
$$
\lim_{x \to x_0}f^g = \lim_{x \to x_0}e^{g\ln(f)}
$$

**📌 Important Limits**
$$
\begin{align}
\text{(i)}\quad&\displaystyle\lim_{n \to \infty}\left(1 + \frac{x}{n}\right)^n = e^x\\
\text{(ii)}\quad&\displaystyle\lim_{n \to 0} \frac{a^n-1}{n} = \ln(a)\\
\text{(iii)}\quad&\displaystyle\lim_{n \to \infty} \ln(n) = \infty\\
\text{(iv)}\quad&\displaystyle\lim_{n \to \infty} \frac{\log_{a}(1+n)}{n} = \frac{1}{\ln(a)}\\
\text{(v)}\quad&\displaystyle\lim_{n \to 0} \frac{\log_{a}(1+n)}{n} = \frac{1}{\ln(a)}\\
\text{(vi)}\quad&\displaystyle\lim_{n \to 0} \frac{\sin(n)}{n} = 1\\
\text{(vii)}\quad&\displaystyle\lim_{n \to 0} \frac{1-\cos(n)}{n} = 0\\
\text{(viii)}\quad&\displaystyle\lim_{n \to 0} \frac{1-\cos(n)}{n^2} = \frac{1}{2}\\
\text{(ix)}\quad&\displaystyle\lim_{n \to 0} \frac{\tan(n)}{n} = 1\\
\text{(x)}\quad&\displaystyle\lim_{n \to \infty} \frac{n!}{n^n} = 0\\
\text{(xi)}\quad&\displaystyle\lim_{n \to 0} \frac{e^n-1}{n} = 1\\
\text{(xii)}\quad&\displaystyle\lim_{n \to \infty} \sqrt[n]{n!} = \infty\\
\text{(xiii)}\quad&\displaystyle\lim_{n \to \infty} \sqrt[n]{n} = 1\\
\end{align}
$$
