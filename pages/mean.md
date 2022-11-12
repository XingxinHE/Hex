---
aliases: [expected value, expectation value]
---


# 📝Definition
## mean
There are several statistical quantities called means.
| mean                      | value                                  | abbreviations |
| ------------------------- | -------------------------------------- | ------------- |
| harmonic mean             | $\frac{2ab}{a+b}$                      | H             |
| geometric mean            | $\sqrt{ab}$                            | G             |
| arithmetic-geometric mean | $\frac{(a+b)\pi}{4K(\frac{a-b}{a+b})}$ | AGM           |
| arithmetic mean           | $\frac{a+b}{2}$                        | A             |
| root-mean-square          | $\sqrt{\frac{a^2+b^2}{2}}$             | RMS           |

When applied to two elements $a$ and $b$ with $0<a\leq b$, these means satisfy
$$
H(a,b)\leq G(a,b)\leq AGM(a,b)\leq A(a,b)\leq RMS(a,b)
$$
> [!NOTE]
> Normally, we refer arithmetic mean as [[average]].

## Expected Value
Given a [[probability density function|probability distribution]] $p(x)$ such that
$$
\int _{-\infty }^{\infty } p(x)\,  dx =1
$$
, the expected value, $E$ , also known as the mean.

> [!tip] Tip
> Note that the expected value is completely analogous to [[centroid|center of mass]]. Here we do not need to divide by the total integral of the probability distribution since the integral $\int _{-\infty }^{\infty } p(x)\,  dx$ is normalized to be equal to $1$.



# 🧬Related Elements
The following subjects are related to "mean."
- [[median]]
- [[mode]]
## [[mean]], [[median]], [[mode]]
The comparison is the following.
- mean: the sum of all values divided by the number of values
- median: the value in the middle of the ordered list of values
- mode: the value that occurs most frequently
