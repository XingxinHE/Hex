alias:: recursive

- # 😎Quick Digest -> Recursion
	- ## 📝Definition
	  Recursion is defined as any solution technique in which <u>large problems</u> are solved by <u>reducing them to smaller problems</u> ***of the same form***.
	- ## 🎯Intent
	  Using recursion makes it possible to solve complex programs in <u>simple and profoundly elegant</u> ways.
	- ## 🥼Expert's Advice
	  See what experts addressed.
		- 📌How to learn recursion? -by Robert Erics
			- First of all, learning how to use recursion can be difficult🙁. But! you should develop the <u>intuition</u> necessary to make recursion seem as natural as all the other control structures.
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- 📌Recursive paradigm
			- The recursive function is more or less like the following:
			- ```
			  if (test for simple case)
			  {
			    Compute a simple solution without using recursion.
			  }
			  else
			  {
			    Break the problem down into subproblems of the same form.
			    Solve each of the subproblems by calling this function recursively.
			    Reassemble the subproblem solutions into a solution for the whole.
			  }
			  ```
			- Because the solution depends on dividing hard problems into simpler instances of the same problem, recursive solutions of this form are often called **divide-and-conquer** algorithms.
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor.
		- [[iterative]]
			- Iterative and recursive strategies are <u>often seen as opposites</u> because they can be used to solve the same problem in rather different ways.
			- However, sometimes we will use iterative strategy in recursive strategy.
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
		- 📌When you should use recursion?
			- When you are faced with a task that exceeds your own capacity, the answer lies in delegating part of the work to others.
		- 📌How to judge whether the problem can be solved by recursion?
			- You must be able to **identify simple cases** for which the answer is easily determined.
			- You must be able to **identify a recursive decomposition** that allows you to break any complex instance of the problem into simpler problems of the same form.
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
	- ## 🙋‍♂️Related Elements
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
	- ## 🧱Structure
	  Any other hierarchical issues?