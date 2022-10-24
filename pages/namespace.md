- ## 📝Definition
	- The language mechanism for such grouping of declarations is a namespace. Like organize classes, functions, data, and types into an identifiable and named part of a program without defining a type.
- 🚀Benefit / Pros
	- In short, it can prevent duplicated method or class names. For example
	- ``` c#
	  Rhino.Geometry.Circle;
	  CGM.Basics.Circle;
	  ```
	  ⚠ class library can be split into a number of assemblies!
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