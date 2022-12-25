---
aliases: []
tags:
  - unknown
---


# 📝Definition
The Peano's Axioms are the followings.
- **🗡Axiom 1** ^5e34d0
	- $0$ is a natural number.
- **🗡Axiom 2** ^2d36c7
	- If $n$ is a natural number, then $n\mathbin{++}$ is also a natural number.
- **🗡Axiom 3** ^cf1c3f
	- $0$ is not the *[[successor]]* of any natural number; i.e., we have $n\mathbin{++} \neq 0$ for every natural number $n$.
- **🗡Axiom 4** ^5d2983
	- Different natural numbers must have different successors; i.e., if $n, m$ are natural numbers and $n \neq m$, then $n\mathbin{++} \neq m\mathbin{++}$. Equivalently, if $n\mathbin{++} = m\mathbin{++}$, then we must have $n = m$.
- **🗡Axiom 5** ^acd61d
	- Let $P(n)$ be any property pertaining to a natural number $n$. Suppose that $P(0)$ is true, and suppose that whenever $P(n)$ is true, $P(n\mathbin{++})$ is also true. Then $P(n)$ is true for every natural number $n$.
	- This is also known as [[Principle of Mathematical Induction]].

> [!note]
> The last axiom should technically be called **an axiom schema** rather than an axiom - it is a template for producing an (infinite) number of axioms, rather than being a single axiom in its own right.


# 🎯Intent
To rigorously define what ==**is**== [[natural number]].

# 🗿Socratic Method
To fully understand the Peano's Axioms, I will explain in a Socratic method by accompanying Q&A and notes.
___
We first start by a slightly informal definition of natural number.
- **📝Definition 1**
	- A natural number is any element of the set $\mathbb{N}:=\{0,1,2,3,4,\dots\}$
___
Then
- **💬Question**: How would you define this natural number system?
- **🗣Answer**:
	- The number is in a incrementing pattern, I would see it in this way.
		- $\mathbb{N}:=\{0,0\mathbin{++},(0\mathbin{++})\mathbin{++},((0\mathbin{++})\mathbin{++})\mathbin{++},(((0\mathbin{++})\mathbin{++})\mathbin{++})\mathbin{++},\dots\}$
	- And on and...
- **📜Key Takeaway**:
	- So the key elements here are twofolds.
		- $0$.  (which exactly is [[Peano's Axioms#^5e34d0|the 1st axiom]])
		- [[increment operation]]  (which exactly is [[Peano's Axioms#^2d36c7|the 2nd axiom]])
___
We can practice a bit using the 1st, 2nd axioms. We do a [[proposition]]-[[proof]].
- **📏Proposition 1**
	- $3$ is a natural number.
- **✍Proof 1**
	- By [[Peano's Axioms#^5e34d0|the 1st axiom]], $0$ is a natural number.
	- By [[Peano's Axioms#^2d36c7|the 2nd axiom]] 3 times, we got $0\mathbin{++}=1, 1\mathbin{++}=2, 2\mathbin{++}=3$  $\quad\Box$
___
We keep asking in Socratic method.
- **💬Question**: How do you know when you add up something and will not go back to $0$?
	- e.g. When $3\mathbin{++}=0$.
- **🗣Answer**:
	- The question seems silly but it is not. In analogy, a computer will [[overflow]] its [[memory]] and the number will wrap around back to $0$!!
	- In the meantime, setting up an infinite loop on $0,1,2,3$ does obey the 1st and 2nd axioms!
	- Therefore, we need to make another axiom to cut the infinite loop!
- **✍Argument**:
- **📜Key Takeaway**:
	- By [[Peano's Axioms#^cf1c3f|the 3rd axiom]], we can cut the [[infinite loop]].
___
Now we do another proposition-proof.
- **📏Proposition 2** ^223c59
	- $4$ is not equal to $0$.
- **📃Note**: Don't laugh! We have to forget everything as we are learning number theory!
- **✍Proof 2**
	- By definition, $3\mathbin{++}=4$
	- This is kind of like [[backpropagation]], we prove $3$ is a natural number by using [[Peano's Axioms#^5e34d0|the 1st axiom]], [[Peano's Axioms#^2d36c7|the 2nd axiom]].
	- By [[Peano's Axioms#^cf1c3f|the 3rd axiom]], we knew $3\neq0$.
	- Therefore $4\neq0$. $\quad\Box$
___
One more Socratic method.
- **💬Question**: What if our number system has a "ceiling"?
	- e.g. The [[interval]] of this number system is $[0,3]$ let' say. Then the following is true. $0\mathbin{++}=1,\quad 1\mathbin{++}=2,\quad 2\mathbin{++}=3,\quad 3\mathbin{++}=3,\quad 4\mathbin{++}=3,\quad 5\mathbin{++}=3, \dots$
- **🗣Answer**:
	- This is very similar in [[Error-Handling]] on out of range situation that assign the biggest value to it.
- **📜Key Takeaway**:
	- By [[Peano's Axioms#^5d2983|the 4th axiom]], we can break the limitation of "ceiling".
___
- **📏Proposition 3**
	- $6$ is not equal to $2$.
- **✍Proof 3**
	- Let's do a [[proof by contradiction]] this time.
	- Suppose $6=2$.
	- Then $5\mathbin{++}=1\mathbin{++}$
	- Since we are doing contradiction, we anti-[[Peano's Axioms#^5d2983|the 4th axiom]] and got $5=1$
	- Then $4\mathbin{++}=1\mathbin{++}$
	- Then $4=0$ which contradictory to [[Peano's Axioms#^223c59|our previous proposition.]]  $\quad\Box$
___
- **💬Question**: What if our number system has a "half number"?
	- e.g. $\mathbb{N}:=\{0,0.5,1,1.5,2,2.5,\dots\}$
- **🗣Answer**:
	- Because we are dealing with the natural number first, $0.5$ should not be in our system at all! It is [[posteriori]].
	- This number system does not violate 1-4 axioms. The intention for us is to set up everything from $0$ and then incrementing so on...
- **📜Key Takeaway**:
	- By [[Peano's Axioms#^acd61d|the 5th axiom]], we can not only "inherit" the number but also the "property".


# 🧠Intuition
Find an intuitive way of understanding this concept.

# 🗃Example
Example is the most straightforward way to understand a mathematical concept.

# 🌱Related Elements
The closest pattern to current one, what are their differences?


# 🍂Unorganized