- # 😎Quick Digest -> Model of Computation
	- ## 📝Definition
	  The name is the essence of this topic.
	- ## 🎯Intent
		- For [[Algorithm]],
			- To **precisely calculate** the resources used by an algorithm, we need to model how long a computer takes to perform basic operations.
	- ## 🏷(Sub)Categories
	  There are several model to measure [[Computation]]
		- 📌Word-RAM
			- Definition
				- In reality, the interaction between CPU and RAM can be very **complicated**. Therefore in MIT algorithm class, the lecturers coined Word-RAM😁. A Word-RAM processor can perform basic binary operations on two machine words in constant time.
			- Example
				- $w$-bits Word-RAM allows you to read and write from at most $2^w$ addresses in memory.
				- $4$-bits Word-RAM allows you to read and write from at most $16$ addresses in memory. Like:
				  | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   | 11   | 12   | 13   | 14   | 15   | 16   |
				  | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
				  | V    | J    | O    | T    | R    | B    | L    | R    | E    | S    | V    | Z    | P    | O    | M    | B    |
			- Prerequisite
				- for $w$
					- With information provided above, suppose we need to read $n$ words, what is the **minimum** bits of this Word-RAM?
					- $$
					  \begin{align}
					  2^w &> n\\w&>\log_2(n)
					  \end{align}
					  $$
				- for the assumption on operation of processor
					- Normally, we suppose the processor supports many **constant time operations** on a $\Omicron(1)$ number of words (integers):
						- **integer arithmetic**: $(+, -, *, /, \%)$
						- **logical operators**: $(\&\&, ||, !, ==, <, >, <=, =>)$
						- **bitwise arithmetic**: $(\&, |, <<, >>, ...)$
						- **read & write**: Given word $a$, can read word at address $a$, write word to address $a$
	- ## 🗃Example  
	  Example is the most straightforward way to understand a mathematical concept.
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
	- ## 🙋‍♂️Related Elements
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
	- ## 🐍Algorithm
	  Algorithm relates to this stuff..
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?