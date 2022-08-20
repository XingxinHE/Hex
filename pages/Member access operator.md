- # 😎Quick Digest -> Member access operators
	- ## 📝Definition
	  The name is the essence of this topic.
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
		- In C++, there are 2 kinds of member access operators of `struct`, `union`, and `class`.
			- `.`
			- `->`
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
		- In C++,
			- `->` is a <u>shorthand</u> for **dereference and then access**.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- example of different member access operator in C++
			- syntax difference
			  ``` c++
			  struct Date
			  {
			    int month;
			    int day;
			  };
			  
			  // `.` operator. non-poitner
			  Date d1;
			  d1.month = 4;
			  d1.day = 21;
			  // `->` operator. pointer
			  Date* d2;
			  d2->month = 4;
			  d2->day = 20;
			  ```
			- mechanism difference. The main difference is that the later one ***will not be deleted automatically by the garbage collection***!!
			  
			  ``` c++
			  // non-poitner
			  void foo1()
			  {
			      Date d1;
			      d1.month = 4;
			      d1.day = 21;
			      ...
			      
			      // d1 will be thrown away once out of this scope
			  }
			  
			  // pointer
			  void foo2()
			  {
			      Date* d2;
			      d2->month = 4;
			      d2->day = 20;
			      ...
			      
			      // d2 will be thrown away but what d2 points to will NOT be thrown away!
			  }
			  
			  ```
			- the Interchangeability of `.` and `->`
			  
			  ``` c++
			  // The followings are the same!
			  d2->month = 4;
			  (*d2).month = 4;
			  ```
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
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