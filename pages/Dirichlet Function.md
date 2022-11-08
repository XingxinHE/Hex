# 📝Definition
Let $c$ and $d\neq c$ be real numbers (usually taken as $c=1$ and $d=0$). The Dirichlet function is defined by
$$
D(x)=
\begin{cases}
c\quad\text{for $x$ rational}\\
d\quad\text{for $x$ irrational}
\end{cases}
$$
and is [[Discontinuity|discontinuous]] everywhere.
The Dirichlet function can be written analytically as
$$
D(x)=\lim_{m\to\infty}\lim_{n\to\infty}\cos^{2n}{(m!\pi x)}
$$
# 📈Diagram
![name|300](../assets/DirichletFunction_1000.svg)
Because the Dirichlet function cannot be plotted without producing a solid blend of lines, a modified version, sometimes itself known as the Dirichlet function (Bruckner _et al._ 2008), Thomae function (Beanland _et al._ 2009), or small Riemann function (Ballone 2010, p. 11), can be defined as
$$
D_M(x)=
\begin{cases}
0&\quad\text{for $x$ irrational}\\
1/b&\quad\text{for $x=a/b$ ,a reduced fraction}
\end{cases}
$$