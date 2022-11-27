# 🧾 Cheat Sheet
**📌 Properties**
$$
\begin{align}
\text{(i)}\quad&\frac{d}{dx}(c) = 0\\
\text{(ii)}\quad&(cf)' = cf'(x)\\
\text{(iii)}\quad&(f\pm g)'= f'(x) + g'(x)\\
\text{(iv)}\quad&(fg)' = f'g + fg'\\
\text{(v)}\quad&\left(\frac{f}{g}\right)' = \frac{f'g-fg'}{g^2}\\
\text{(vi)}\quad&\frac{d}{dx}\left([f(x)]^n\right) = n[f(x)]^{n-1}f'(x)\\
\text{(vii)}\quad&\frac{d}{dx}(f(g(x)) = f'(g(x))g'(x)\\
\text{(viii)}\quad&[f^{-1}]'(x) = \frac{1}{f'(f^{-1}(x))}\\
\end{align}
$$

**📌 Common Derivative**
$$
\begin{align}
\text{(i)}\quad&\frac{d}{dx}(x) = 1\\
\text{(ii)}\quad&\frac{d}{dx}(|x|) = sign(x)\\
\text{(iii)}\quad&\frac{d}{dx}(e^x) = e^x$      \\
\text{(iv)}\quad&\frac{d}{dx}(a^x) = a^x\ln(a)\\
\text{(v)}\quad&\frac{d}{dx}(\frac{1}{x}) = -\frac{1}{x^2}\\
\text{(vi)}\quad&\frac{d}{dx}\sqrt{x} = \frac{1}{2\sqrt{x}}\\
\text{(vii)}\quad&\frac{d}{dx}(\ln(f(x))) = \frac{f'(x)}{f(x)} = \frac{1}{x} \ \textit{if} \ f(x) = x\\
\text{(viii)}\quad&\frac{d}{dx}(\ln|x|) = \frac{1}{x},\ x\neq0\\
\text{(ix)}\quad&\frac{d}{dx}(\log_{a}(x)) = \frac{1}{xln(a)},\ x>0\\
\text{(x)}\quad&\frac{d}{dx}(\sin(x)) = \cos(x)\\
\text{(xi)}\quad&\frac{d}{dx}(\cos(x)) = -\sin(x)\\
\text{(xii)}\quad&\frac{d}{dx}(\tan(x)) = \sec^2(x) = \tan^2(x)+1\\
\text{(xiii)}\quad&\frac{d}{dx}(\cot(x)) = -\csc^2(x)\\
\text{(xiv)}\quad&\frac{d}{dx}(\sec(x)) = \sec(x)\tan(x)\\
\text{(xv)}\quad&\frac{d}{dx}(\csc(x)) = -\csc(x)\cot(x)\\
\text{(xvi)}\quad&\frac{d}{dx}(\sin^{-1}(x)) = \frac{1}{\sqrt{1-x^2}}\\
\text{(xvii)}\quad&\frac{d}{dx}(\cos^{-1}(x)) = -\frac{1}{\sqrt{1-x^2}}\\
\text{(xviii)}\quad&\frac{d}{dx}(\tan^{-1}(x)) = \frac{1}{1+x^2}\\
\text{(xix)}\quad&\frac{d}{dx}(\sinh(x)) = \cosh(x)\\
\text{(xx)}\quad&\frac{d}{dx}(\cosh(x)) = \sinh(x)\\
\text{(xxi)}\quad&\frac{d}{dx}(\tanh(x)) = \frac{1}{\cosh(x)} = 1-\tanh^2(x)\\
\text{(xxii)}\quad&\frac{d}{dx}(\sinh^{-1}(x)) = \frac{1}{\sqrt{x^2+1}}\\
\text{(xxiii)}\quad&\frac{d}{dx}(\cosh^{-1}(x)) = \frac{1}{\sqrt{x^2-1}}\\
\text{(xxiv)}\quad&\frac{d}{dx}(\tanh^{-1}(x)) = \frac{1}{\sqrt{1-x^2}}\\
\end{align}
$$

# 📝Definition
- The **derivative** of a function $f(x)$ at a point $x=a$ is defined to be:
  $$
  f'(a)=\lim_{b\to a}\frac{f(b)-f(a)}{b-a}
  $$
  There is also an alternative definition:
  $$
  f'(a)=\lim_{h\to0}\frac{f(a+h)-f(a)}{h}
  $$
- 📌Delta Notation$\Delta$ of Derivative
    - We change the notation from:
      $$
      f'(x)=\lim_{b\to x}\frac{f(b)-f(x)}{b-x}\\
      $$
    - to:
      $$
      f'(x)=\lim_{\Delta x\to0}\frac{f(x+\Delta x)-f(x)}{\Delta x}\\
      $$
    
# 🧠Intuition
- We care about the <u>derivative</u> of $f(x)$ at $x=a$ is <u>instant rate of change</u> of $f(x)$ at $x=a$. See the magic of "instant" [[Limit#^e75639e62ab26e7a|here]]
- 📌3 Main Interpretation of Derivative ^c9a25148f62eaeda
    - physical -  **instantaneous** rate of change.
    - geometrical - the **slope** of the tangent line.
    - sensitive - the **sensitivity** of a function to small changes.
    

# 🌓Complement
- [[Antiderivative]]

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.
- 📌Example throwing pumpkin using derivative
    - Question:
        - Suppose there is a guy throwing pumpkin from a $100$ foot roof top, and the distance in terms of time measured is the following
        - $f(t)=100+20t+-5t^2$
        - Find the the average velocity between $t=0$ and $t=1$
        - Find the instantaneous velocity at $t=1$
        
    - Graph:
      ![name](../assets/throwing_pumpkin.svg){:height 300, :width 300}
    - Solution:
        - For average velocity, we don't have to use derivative.
            - $$
              \begin{align}
              \text{average velocity}&=\frac{f(1)-f(0)}{1-0}\\
              &=\frac{100+20\times1-5\times1^2-(100+20\times0-5\times0^2)}{1}\\
              &=15\text{m/s}
              \end{align}
              $$
            
        - For instantaneous velocity, we have to use derivative.
            - $$
              \begin{align}
              \text{instantaneous velocity}&=f'(1)\\&=\lim_{b\to1}\frac{f(b)-f(1)}{b-1}\\
              &=\lim_{b\to1}\frac{100+20b-5b^2-(100+20-5)}{b-1}\\
              &=\lim_{b\to1}\frac{20b-5b^2-15}{b-1}\\
              &=\lim_{b\to1}\frac{-5(b^2-4b+3)}{b-1}\\
              &=\lim_{b\to1}\frac{-5(b-1)(b-3)}{b-1}\\
              &=\lim_{b\to1}\frac{-5\cancel{(b-1)}(b-3)}{\cancel{b-1}}\\&=-5\times(-2)=10\text{ m/s}
              \end{align}
              $$
            
- 📌Example of derivative on a graph
    - ![name](../assets/images_u1der2_tangentlines.svg){:height 250, :width 250}
    - The following are the derivatives:
      $$
      \begin{align}
      f'(-1)&=DNE\\
      f'(0)&=0\\
      f'(1)&=DNE\\
      f'(2)&=DNE\\
      f'(3)&=1/3\\
      \end{align}
      $$
    
