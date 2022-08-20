- # 😎Quick Digest -> Operator overloading
	- ## 📝Definition
	  The name is the essence of this topic.
		- In C++, there are 2 ways of operator overloading.
			- <u>Method-based style</u>
			- <u>Free function style</u>
		- In JavaScript,
			- It doesn't support Operator overloading.
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
		- 📌Overload operator ONLY when you have to
			- operator overloading provides such convenience but!! It is generally a good idea not to define operators for a type unless you are really **certain** that it **makes a big positive change** to your code.
	- ## 🙋‍♂️Related Elements
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
		- For C++ operator overloading, an overloaded operator **must** have **at least one** [[user-defined]] type as operand.
			- ``` c++
			  int operator+(int,int); // ❌error: you can’t overload built-in +
			  Vector operator+(const Vector&, const Vector &); // OK
			  Vector operator+=(const Vector&, int); // OK
			  ```
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?