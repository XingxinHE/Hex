---
aliases: [Indefinite Integral]
---

# 📝Definition
- Definition 1
    - An **antiderivative** of $f(x)$ is any function $F(x)$ such that
        - $$
          F'(x)\,  = f(x)
          $$
        
    - In other words, an antiderivative of a function $f(x)$ is another function whose derivative is $f(x)$.
    
- Definition 2
    - Given a function $f(x)$, the **indefinite integra**l or the **antiderivative** of $f(x)$ is denoted $\int f(x)dx$. It is the family of functions
        - $$
          \int f(x) \, dx \,  = F(x) + C
          $$
        - where $F(x)$ is any antiderivative of $f(x)$, that is $F'(x)=f(x)$, and $C$ is any constant.
        
    - We call $\int$ the **integral sign**, $f(x)$ the **integrand**, and $C$ the **constant of integration**. Since there could be infinite $C$, therefore there is no only one antiderivative of such a function. Hence, this is the reason of phrase "*indefinite*". On the other hand, the constant is **the only ambiguity** of the indefinite integral due to the MVT, which guarantees that any two antiderivatives of the same function can **differ only** by a constant.
    
# 🌓Complement
- ![[Differential Equation#Differential Equation vs Antiderivative]]
- ![[definite integral#Indefinite Integral vs Definite Integral]]

# ⚖Laws
- Properties
    - $$
      \begin{align}
      \int k \,  f (x) \,  dx \, &= \, \   k \int \,  f(x) \, dx\\
      \int \left( f(x)+g(x) \right)\,  dx &=\   \int f(x)\,  dx +\int g(x)\,  dx
      \end{align}
      $$
    
- 📌Integrals of powers ^320f6a5fb26863db
    - The indefinite integral of $x^p$ for any real number $p$.
        - $$
          \int \,  x^p\  dx \,  \, = \qquad \begin{cases}  \displaystyle \frac{x^{p+1}}{p+1} +C &  \text{if } p \neq -1 \\ \ln \left(|x|\right)+C &  \text{if } p = -1. \end{cases}
          $$
        - Few words on when $p=-1$. We can notice that $p$ can't be $-1$ in the first expression. Then we might need to consider when $x^p=x^{-1}$. The reason why there is an absolute value is that although the [[Function#^bdaa359665a4eb20|domain]] of $\ln{(x)}$ should greater than $0$, the domain of $x^{-1}$ does not have that constraint! Therefore, we have it like $\ln{(\lvert x\rvert)}$.
        
- Method of substitution
    - The method of substitution is the integration analogue of the chain rule. It is **tailored** for the differential notation.
    - If
        - $$
          \begin{align}
          g(x)dx=f(u(x)) \, u'(x) dx,
          \end{align}
          $$
        
    - that is, the integrand $g(x)$ can be seen as the result of a chain rule, then
        - $$
          \begin{align}
          \int g(x)dx&=\int f(u(x))\,  u'(x)\,  dx\\
          &=\int f(u)du\\
          &=F(u(x))+C
          \end{align}
          $$
        
# ⛈Characteristics / Properties
- 📌Uniqueness
    - Theorem
        - $$
          \text{If $F'=G'$, then $F(x)=G(x)+C$}
          $$
        
    - Proof
        - If
            - $$
              F'=G'
              $$
            
        - Then
            - $$
              (F-G)'=F'-G'=0
              $$
            
        - Using the MVT, hence we have
            - $$
              F(x)-G(x)=C
              $$
            
# 🧬Related Elements
- 📌 [[MVT]] plays an important role in the definition of antiderivatives
    - Recall MVT, we know
        - $$
          F'(x)=0\quad\text{then $F(x)$ MUST be constant.}
          $$
        
    - With MVT guarantee, **ALL** antiderivative of $f(x)=0$ must be constant.
    
# 🕳Pitfalls / Cons
- 📌Derivative with a discontinuity
    - Conclusion:
    - Question:
        - Define a piece-wise function $g(x)$ by
        - $$
          \begin{align}
          g(x)&=\frac{1}{x}\quad\text{when }x>0\\
          g(x)&=\frac{1}{x}+2\quad\text{when }x<0
          \end{align}
          $$
        - Compute the $g'(x)$ and explain.
        
    - Graph:
      ![name](../assets/antiderivative_discontinuity.svg){:height 300, :width 300}
    - Solution:
        - When $x<0$,
            - $$
              g'(x)=\frac{d}{dx}(\frac{1}{x})=-\frac{1}{x^2}
              $$
            
        - When $x>0$,
            - $$
              g'(x)=\frac{d}{dx}(\frac{1}{x}+2)=-\frac{1}{x^2}
              $$
            
        - So
            - $$
              g'(x)=-\frac{1}{x^2}\quad\text{for all }x\neq0
              $$
            
        - We know
            - $$
              \int -\frac{1}{x^2}dx=\frac{1}{x}+C
              $$
            
        - That's the key!! But if we consider $x$ to be positive and negative at the same time, **the two constants don't necessarily have to agree**. You can have the same situation that you had before, where one side can shift up and down independently of the other, because there's that is [[Discontinuity]] at $0$ there.
        
# 🖨 Cheat Sheet
- 📌Common Integral
    - $$
      \begin{align}
      \int \,  x^p\  dx \,  \, &= \qquad \begin{cases}  \displaystyle \frac{x^{p+1}}{p+1} +C &  \text{if } p \neq -1 \\ \ln \left(|x|\right)+C &  \text{if } p = -1. \end{cases}\\
      \int e^x \,  dx&=e^x+C\\
      \int \cos (x) \,  dx&=\sin (x)+C\\
      \int \frac{1}{1+x^2} \,  dx&=\arcsin(x)+C \text{ or } -\arccos{x}+C\\
      \int \sec (x)\tan (x) \,  dx&= \sec{x}+C\\
      \int \sec ^2(\theta ) d\theta &= \tan{\theta}+C\\
      \int \frac{-1}{x}\,  dx&=-\ln{\lvert x\rvert}+C
      \end{align}
      $$
    
# 🗃Example
- 📌an example of antiderivative
    - If $f(x)=0$, then which of the following functions are antiderivatives of $f(x)$?
        - ✅$F(x)=0$
        - ❌$F(x)=x$
        - ✅$F(x)=-7$
        - ✅$F(x)=\frac{1}{2}$
        - ❌$F(x)=\frac{1}{x}$
        
    - Since the derivative of above selected functions are $0$.
    
- 📌example of notation between antiderivative and [[Differential]]
    - Question
        - Let $dF$ be the differential of the function $F(x)$, then $\int dF=?$
        
    - Solution
        - Since
            - $$
              \begin{align}
              dF&=F'(x)dx,\\ \int dF&=\int F'(x)dx
              \end{align}
              $$
            
        - Now, $F(x)$ is an antiderivative of $F'(x)$, so
            - $$
              \int F'(x)\, dx = F(x)+C \, \, \text{where}\, \,  C \, \, \text{is any real number.}
              $$
            
        - Note that while $F(x)$ is AN antiderivative, it is not the most general form of the antiderivatives of $F'(x)$ and so is not the correct answer.
        
- 📌example of ==units== of antiderivative
    - Consider the differential equation $\frac{dx}{dt} = f(t)$, where $x$ has units of meters, and $t$ has units of seconds.
        - $\int f(t) dt$ - meters
            - The functions $x=\int f(t) dt$ are the solution curves to the differential equation $\frac{dx}{dt} = f(t)$. Thus $\int f(t) dt$ must have the same units as $x$, which are meters.
            
        - $dt$ - seconds
            - The symbol $dt$ stands for the infinitesimal version of $\Delta t$, which is a tiny bit of $t$, thus it has the same units as $t$, which is seconds.
            
        - $f(t)dt$ - meters
            - The differential quantity $f(t)dt=dx$, so $f(t)dt$ has the same units as $dx$, which is a little bit of $x$, and must have units of meters.
            
- 📌example of ==integrals of powers==
    - use the rule of integrals of powers
    - $$
      \begin{align}
      \int x^{\frac{2}{3}} \,  dx&=\frac{ 3x^{\frac{5}{3}}}{5}+C\\
      \int \left(\sqrt{x}\right)^3 \,  dx &= \int x^{\frac{3}{2}} \,  dx=\frac{2x^{\frac{5}{2}}}{5}+C\\
      \int \frac{3}{x} \,  dx&=3 \ln (|x|) +C.
      \end{align}
      $$
    
- 📌example of ==integral of constant multiples of functions==
    - $$
      \begin{align}
      \int \frac{1}{2} (2x)^6 \  dx\  &=\  \int 2^5 x^6 \  dx\\
      &=2^5\int x^6 \  dx\\
      &= \frac{2^5}{7} x^7 +C .
      \end{align}
      $$
    
- 📌example of ==integral of sums of functions==
    - $$
      \begin{align}
      \int \left( \frac{-3}{x}-\frac{1}{x^{3}}\right)\,  dx &= \int \frac{-3}{x}-\int\frac{1}{x^{3}} dx\\
      &= -3 \ln |x|+\frac{x^{-2}}{2}+C.
      \end{align}
      $$
    
- 📌example of ==integral of quotient==
    - $$
      \begin{align}
      \int \frac{x^2+\sqrt{x}}{x^2} \,  dx &= \int 1+ x^{-\frac{3}{2}}\,  dx\\
      &=x - 2 x^{-\frac{1}{2}}+C
      \end{align}
      $$
    
- 📌example of ==integral of chain rule==
    - $$
      \begin{align}
      \int e^{6x}dx\\
      \text{Take a guess, the integral is } e^{6x}\\
      (e^{6x})'&=e^{6x}\cdot6\\
      \text{then we fix the coefficient}\\
      (\frac{1}{6}e^{6x})'&=e^{6x}\frac{1}{6}\cdot6\\
      \text{therefore, we have}\\
      \int e^{6x}dx&=\frac{1}{6}e^{6x}+C
      \end{align}
      $$
    - $$
      \begin{align}
      \int \frac{1}{3x+1}\\
      \text{Take a guess, the integral is } \ln(\lvert3x+1\rvert)\\
      (\ln(\lvert3x+1\rvert))'&=\frac{3}{3x+1}\\
      \text{then we fix the coefficient}\\
      (\frac{1}{3}\ln(\lvert3x+1\rvert))'&=\frac{1}{3x+1}\\
      \text{therefore, we have}\\
      \int \frac{1}{3x+1}&=\frac{1}{3}\ln(\lvert3x+1\rvert)+C
      \end{align}
      $$
    
- 📌Example ==using method of substitution==
    - $$
      \begin{align}
      \int x^3(x^4+2)^5dx&=?\\
      \text{let }u&=x^4+2\\
      \text{differential of the function gives }\\
      du&=(x^4+2)'dx\\
      du&=4x^3dx\\
      \frac{du}{4}&=x^3dx\\
      \text{therefore we can make the integral as the following}\\
      \int x^3(x^4+2)^5dx&=\int (x^4+2)^5x^3dx&= \int\underbrace{ u^5}_{(x^4+2)^5} \underbrace{\frac{1}{3}du}_{x^3dx}\\
      &=\frac{1}{4} \int u^5du\\
      &=\frac{1}{24}u^6+C
      \end{align}
      $$
    - $$
      \begin{align}
      \int \frac{2x^3-3x^2}{(x^4-2x^3-7)^3}\, dx &=?\\
      \text{let }u&=x^4-2x^3-7\\
      du&=(4x^3-6x^2)dx\\
      \text{then substitute we have}\\
      \int \frac{2x^3-3x^2}{(x^4-2x^3-7)^3}\, dx &= \int \frac{1}{2}u^{-3}du\\
      \int \frac{2x^3-3x^2}{(x^4-2x^3-7)^3}\, dx &=\frac{-1}{4u^2}+C\\
      &=\frac{-1}{4(x^4-2x^3-7)^2}+C.
      \end{align}
      $$
    
- 📌example of ==integral of logarithmic function==
    - Let us use substitutions for the following integral.
    - $$
      \int \frac{dx}{x\ln{x}}
      $$
    - Let $u=\ln{x}$
    - Then $du=\frac{dx}{x}$
    - $$
      \begin{align}
      \int \frac{dx}{x\ln{x}}&=\int \frac{1}{\ln{x}}\frac{dx}{x}\\
      &=\int\frac{du}{u}\\ 
      &=\ln{u}+C\\
      &=\ln{\ln{x}}+C\\
      &=\ln\lvert\ln{x} \rvert+C
      \end{align}
      $$
    
- 📌example of ==integral of trigonometry function==
    - Let us compare using two different substitutions for the following integral.
    - $$
      \begin{align}
      \int \sec ^2(y) \tan (y)\,  dy
      \end{align}
      $$
    - First, let $u=\tan(y)$. Then $du=\sec^2(y)dy$
    - This gives
        - $$
          \int \sec ^2(y) \tan (y)\,  dy =\frac{1}{2}\tan^2(y)+C
          $$
        
    - Alternatively, let $u=\sec(y)$. Then $du=\sec(y)\tan(y)dy$
    - This gives
        - $$
          \int \sec ^2(y) \tan (y)\,  dy =\frac{1}{2}\sec^2(y)+C
          $$
        
- 📌example of integral of harder problems!
    - Example 1
        - Question
            - $$
              \int \frac{1}{9y^2+6 y +1} \, dy \, =\,?
              $$
            
        - Solution
            - $$
              \begin{align}
              \int \frac{1}{9y^2+6 y +1} \, dy \, &=\int \frac{1}{\left( 3y+1\right)^2} \, dy\\
              \text{If we let $u=3y+1$, then $du=3dy$. This gives}\\
              \int \frac{1}{\left( 3y+1\right)^2} \, dy &= \int \frac{1}{u^2} \frac{du}{3}\\
              &=-\frac{1}{3u}+C\\
              &=-\frac{1}{3(3y+1)}+C.
              \end{align}
              $$
            
    - Example 2 - comparing similar integrals
        - Question
            - $$
              \begin{align}
              \int \frac{1}{1+4v^2} \, dv &=\,?\\
              \int \frac{v}{1+4v^2} \, dv &=\,?
              \end{align}
              $$
            
        - Solution
            - $$
              \begin{align}
              \int \frac{1}{1+4v^2} dv&=\frac{1}{2}\arctan (2v) +C\\
              \int \frac{v}{1+4v^2} dv&=\frac{1}{8}\ln |1+4v^2|+C\\
              &=\frac{1}{8}\ln (1+4v^2)+C
              \end{align}
              $$
            
    - Example 3 - comparing similar integrals
        - Question
            - $$
              \begin{align}
              \int \frac{1}{\sqrt{9-\frac{9v^2}{4}}} dv \, &=\,?\\
              \int \frac{v}{\sqrt{9-\frac{9v^2}{4}}}\, dv \, &=\,?
              \end{align}
              $$
            
        - Solution
            - $$
              \begin{align}
              \int \frac{1}{\sqrt{9-\frac{9v^2}{4}}} dv \, &=\frac{2}{3} \arcsin \left(\frac{v}{2}\right) +C\\
              \int \frac{v}{\sqrt{9-\frac{9v^2}{4}}}\, dv \, &=\frac{4}{9}\sqrt{9-\frac{9v^2}{4}} +C
              \end{align}
              $$
            
# 🗑Unorganized
