# 📝Definition
$$
p(t) = a e^{-a t}, \quad 0 \leq t < \infty\qquad \text{(and }p(t) = 0, \quad t<0\text{)},
$$
where
- $p(t)$ is an [[Exponential Function|exponential function]].
- the [[mean|expected value]] is $1/a$.

> [!NOTE] Note
> Note that $\int _0^{\infty } a e^{-a t} \,  dt =1$, so this is a [[probability density function|probability distribution]]. 


# 🎯Intent
The exponential distribution is used to compute the [[probability]] of a “waiting time" between events, such as the arrival of a bus, the decay of a radioactive particle, or the time between phone calls during business hours.

# 🗃Example
- 📌exponential distribution
	- 💬Question:
		- Suppose that during business hours, your business receives a phone call, on average, every 2 minutes. The distribution for phone calls is given by $p(t) = \frac{1}{2} e^{-t/2}$.
		- Question 1
			- What is the probability that you get a phone call in the first 3 minutes of your day?
		- Question 2
			- What is the probability that you don't get a phone call for the first 3 minutes of your day?
	- 🏹Strategy:
		- What is $t$? What is the unit of it?
	- ✏Solution:
		- Solution on question 1
			- Relatively easy, just plug the minute.
			- $$P(0<t<3) = \int _0^3 \frac{1}{2}e^{-t/2} = 1-e^{-3/2} \approx .78$$
		- Solution on question 2
			- That's also easy, just take the opposite.
			- $$P(t>3) =1-P(0<t<3) = 1-.78 = .22$$


- 📌Exponential distributions 1 ^ac60dc
	- 💬Question:
		- Suppose that the expected value of the length of time between auto accidents on the Massachusetts Turnpike is 10 hours. If we assume the distribution of times between accidents is exponential, estimate the probability that there are no accidents for 24 hours.
	- 🏹Strategy:
		- Think about the relation between [[mean|expected value]] and exponential distribution
	- ✏Solution:
		- Write down the formula of exponential distribution
			- $$p(t) = ae^{-at}, t\geq 0$$
		- The expected value of exponential distribution is
			- $$\frac{1}{a}$$
		- Therefore we have
			- $$\begin{align}\frac{1}{a}&=10\\a&=\frac{1}{10}\end{align}$$
		- The exponential distribution formula is that
			- $$p(t) = (0.1) e^{-(0.1)t}.$$
		- Now we compute the probability.
			- Straight forward way calculating
				- $$\begin{align}P(t>24)&=\int _{24}^{\infty } (0.1) e^{-(0.1)t} \, dt\\&=-e^{-(0.1)t}\, |_{24}^{\infty}\\&=e^{-2.4} \approx 0.09\end{align}$$
			- Calculate $1-P(t<24)$ instead
				- $$\begin{align}1-P(t<24)&=1-\int _{0}^{24} (0.1) e^{-(0.1)t} \, dt\\&\approx1-0.91=0.09\end{align}$$


- 📌Exponential distributions 2 ^8ec66b
	- 💬Question:
		- Suppose that while the coffee shop in MIT lobby 7 is open, the expected time between sales is 4 minutes, and the distribution for time between sales is exponential.
		- Question 1
			- What is the probability that the time between successive sales is greater than 2 minutes?
		- Question 2
			- What is the probability that the time between successive sales is less than 4 minutes?
	- 🏹Strategy:
		- Use [[mean|expected value]] to have $a$
	- ✏Solution:
		- Solution on question 1
			- Since expected time is 4 min
				- then $a=\frac{1}{4}$
			- Write down the exponential distribution
				- $$p(t) = ae^{-at}, t\geq 0$$
			- So the distribution is
				- $$p(t) = (0.25) e^{-(0.25)t}.$$
			- Now we compute the probabilities:
				- greater than 2 mins
					- $$\begin{align}P(t>2)&=\int _{2}^{\infty } (0.25) e^{-(0.25)t} \, dt\\&=-e^{-(0.25)t}\, |_{2}^{\infty}\\&=e^{-0.5} \approx 0.61\end{align}$$
				- less than 4 mins
					- $$\begin{align}P(t<4)&=\int _{0}^{4} (0.25) e^{-(0.25)t} \, dt\\&=-e^{-(0.25)t}\, |_{0}^{4}\\&=1-e^{-1} \approx 0.63\end{align}$$


