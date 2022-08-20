- # 😎Quick Digest -> title
	- ## 📝Definition
	  `double` is short for "double-precision" [[Floating Point]].
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
		- 📌⚠pitfall on numeric literal on [[narrowing]]
			- Suppose you are converting degrees Celsius to degree Fahrenheit: $f=9/5*c+32$. It involves [[integral type]]
			- Bad code
			  
			  ``` c++
			  double dc;
			  cin >> dc;
			  double df = 9/5*dc+32; // ❌beware!
			  ```
			- Good code
			  
			  ``` c++
			  double dc;
			  cin >> dc;
			  double df = 9.0/5*dc+32; // ✅better
			  ```
	- ## 🙋‍♂️Related Elements
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?