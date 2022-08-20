- # 😎Quick Digest -> namespace
	- ## 📝Definition
	  The language mechanism for such grouping of declarations is a namespace. Like organize classes, functions, data, and types into an identifiable and named part of a program without defining a type.
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
		- 📌Don't put a `using` directive in a [[header file]]
			- So important!! Never do that!
			- ``` c++
			  //Shape.h
			  #include <string>
			  using namespace std;
			  // Hyped...😎 feeling awesome feeling cool getting rid of `std::` prefix
			  ```
			- ``` c++
			  //Shape.cpp
			  
			  #include "Shape.h"
			  
			  //of course client are happy in here without using `std::string`🙄
			  ```
			- ``` c++
			  //main.cpp
			  #include "Shape.h"
			  #include "Rectangle.h"
			  
			  //But!!❌ The problem is here!! The `using` directives pollutes others!! High possibility to have naming clash!!😡
			  ```
			-
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