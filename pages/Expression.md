- # 😎Quick Digest -> expression
	- ## 📝Definition
	  The name is the essence of this topic.
	- ## 🎯Intent
	   A short description what does this thing do?
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
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
		- 📌Avoid complicated expressions
		  id:: 63145dc9-507f-476b-a516-23ec9b831747
			- The **RULE**: if you change the value of a variable in an expression, don’t read or write it twice in that same expression.
			- ``` c++
			  v[i] = ++i; 					 // ❌don’t: undefined order of evaluation
			  v[++i] = i; 					 // ❌don’t: undefined order of evaluation
			  int x = ++i + ++i;  			 // ❌don’t: undefined order of evaluation
			  cout << ++i << ' ' << i << '\n'; // ❌don’t: undefined order of evaluation
			  f(++i,++i); 					 // ❌don’t: undefined order of evaluation
			  ```
			- The preceding code is bad in portability. Regarding various compilers, some work while some don't. Note in particular that `=` (assignment) is considered just another operator in an expression, so there is no guarantee that the left-hand side of an assignment is evaluated before the right-hand side.
			- **Fun Fact**😅... I used to think this is kind of cool...
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