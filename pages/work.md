# 📝Definition
In #physics  , work is the [[energy]] transferred to or from an object via the application of [[force]] along a displacement.
# 📏Unit
#Newton-meters $N\cdot m$

# 💫Operation
## Force to Work
### 📝Definition
A common example of mechanical work is when a [[force]] is applied over a distance. This force applied to the object transfers [[energy]] in the form of kinetic or potential energy. In this case, the formula for work is given by
$$
W = \int F \, dx.
$$
### 🗃Example
📌Work practice 1 ^9ccbf2
- 💬Question:
	- Consider a spring. According to [[Hooke's law]], the force $F$ exerted by the spring is given by $F=-kx$, where $k>0$ is a positive constant, known as the spring constant, and $x$ is the displacement from the position at rest $(x=0)$. A force of $2000$ lbf moves an extremely stiff spring $1/2$ inch (in) away from the resting position. How many foot-pounds (ft$\cdot$lbf) of work $W$ would be done in stretching it $6$ inches from rest? (Note there are 12 inches in 1 foot.)
- 📈Diagram:
	- ![name|200](../assets/images_applications3-spring.svg)
- 🏹Strategy:
	- Find the $k$ first!
- ✏Solution:
	- To find $k$, substitute into Hooke's law:
		- $$2,000 = k\cdot (1/2) \implies k = 4000 \textrm{ lbf/in}.$$
	- To find the work $W$ required to extend the spring by 6 inches, we use the formula $F=kx=4000x$ to find:
		- $$W = \int _0^6 F\, dx = \left. \int _0^6 4000x\, dx = 2000x^2\  \right|_0^6 =72,000\  \text{in}\cdot \text{ lbf} = 6,000\  \text{ft}\cdot \text{lbf}.$$

### 🕹Quiz


- 📌3A-8
	- 💬Question: A heavy metal 2 pound bucket initially is filled with 10 pounds of paint. Immediately after it is filled, it is pulled up at a steady rate to the top of a building 30 feet high. While being pulled, the paint leaks out through a hole in the pail at a steady rate so that by the time it reaches the top, 1/5 of the paint has leaked out.
		- Question 1: Let $w(h)$ be the weight of the bucket at height $h$. First find $w(h)$.
		- Question 2: Use the answer above to find the work. How many foot-pounds of work $W$ were done pulling the bucket to the top of the building?
	- 🏹Strategy: for application quiz, first draw the diagram!!
	- ✏Solution:
		- Draw the scenario in the diagram
			- ![name|300](../assets/paint_work_integration.svg)
		- Let $w(h)$ be th weight of pail and paint at height $h$. Then we know
			- $$w(0)=12, \quad w(30)=10$$
		- since the pulling and leakage both occur at a constant rate, then the rate is
			- $$\frac{10-12}{30}=-\frac{1}{15}$$
		- Now we have the equation of weight and height
			- $$w(h)=12-\frac1{15}h$$
		- Recall the work formula
			- $$W = \int F \, dx.$$
		- Finally we can calculate the work from ground zero to 30 inches.
			- $$W= \int _0^{30} W(h)\text{ }dh = \int _0^{30} (12 -\frac{h}{15})\text{ }dh =\left.12h-\frac{h^2}{30}\right|_0^{30} = 330\text{ft-lbs.}$$

- 📌3A (14)
	- 💬Question: Two point-particles having respective masses $m_1$ and $m_2$ are at $d$ units distance. Recall that the force between two point particles is given by the [[Newton's law of universal gravitation]].
		- $$F = \frac{G m_1 m_2}{r^2},$$ where $r$ is the distance between 2 particles.
		- Question 1: How much work is required to move them $n$ times as far apart (i.e., to distance $nd$)?
		- Question 2: What is the work $W$ to move them infinitely far apart?
	- ✏Solution:
		- Suppose they are currently $x$ unit apart, then the force can be expressed as
			- $$\frac{G\, m_1m_2}{x^2}$$
		- The distance of the work is from $d$ to $nd$
		- (Answer to question 1)Then the work can be computed as
			- $$\displaystyle\begin{align}\text{work}\  &=\  \int _d^{nd} \frac{G\, m_1m_2}{x^2}\, dx \\&=-\frac{G\, m_1m_2}{x}\biggr ]_{d}^{nd}\\&=-G\, m_1m_2\biggl (\frac1{nd}-\frac1d\biggr )\\&=\frac{G\, m_1m_2}d\biggl (\frac{n-1}n\biggr ).\end{align}$$
		- (Answer to question 2) the limit $n\to \infty$ is $\frac{G\, m_1m_2}d$




# 🧬Related Elements
## work-heat-enery
Work, [[heat]], and [[energy]] have the same units, but we typically measure them differently.
- work - $N\cdot m$
- heat - $\text{cal}$
- energy - $J$
[[James Joule]] recognized and measured the relationship between heat energy and mechanical work.
$$
1 \text{cal} =4.186 \text{ J} = 4.186 \text{ N}\cdot \text{m}.
$$
