# 📝Definition
A [[Continuity|continuous]] distribution is a nonnegative function $w(x)$ that approximates the discrete distribution. The area under a continuous distribution measures the probability that an event occurs.
$$
P(a < x < b) = \frac{\int _a^b w(x)\,  dx}{\int _{-\infty }^{\infty } w(x)\,  dx}
$$
For commonly used distributions, it is common to rescale the function. Since
$$
\int _{-\infty }^{\infty } w(x)\,  dx =C
$$
is a finite constant, we define a new function
$$
p(x) = \frac{w(x)}{C}
$$
This new function $p(x)$ had the property that
$$
\int _{-\infty }^{\infty } p(x)\,  dx =1
$$
> [!NOTE] Note
> The new function is also called [[probability density function]] whose probability in total is 1.
