alias:: raw pointer

- # 😎Quick Digest -> pointer
	- ## 📝Definition
	  A pointer is a variable that stores the memory address of an object.
	- ## 🎯Intent
	   A short description what does this thing do?
		- Pointers are used extensively in both C and C++ for three main purposes:
			- to allocate new objects on the heap
			- to pass functions to other functions
			- to iterate over elements in arrays or other data structures
	- ## 🧠Intuition
	  A variable which points to something.
	- ## 🚀Benefit / Pro
	  A *pointer* introduces a level of **indirection** to a program. Rather than <u>manipulate an object directly</u>😑, we <u>manipulate a pointer that holds the address of an object</u>😍.
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
		- In C++, there are 2 main categories.
			- raw pointer
			- [[Smart Pointer]]
	- ## ⌨Sample Code
		- sample code on C++ raw pointer
		  
		  ``` c++
		  int ival = 1024;
		  int* pi;             // pi is a pointer to an object of type int
		  &ival;               // evaluates to the address of ival by using `&`
		  pi = &ival;          // pass the address of ival to pi
		  ```
		- sample on different style of C++ raw pointer
			- ``` c++
			  int* pi = &ival;
			  int *pi = &ival;
			  ```
			- I personally favor the second version which seeing that the `*` affects the declarator-id directly.
			- ``` c++
			  // pi is a pointer to int
			  // pt2 is an int
			  int* pi, pi2;
			  
			  // pi3 is a pointer to int
			  // pi4 is a pointer to int
			  int* pi3, * pi4;
			  ```
			- Use `T *p` rather than ~~`T* p`~~
		- example on guarding against dereferencing a null pointer
		  id:: 63107a40-7df6-42ef-8c1c-9581169b1eff
			- ``` c++
			  // safe check
			  if (pi && *pi!=1024)
			  {
			      *pi = 1024;
			  }
			  
			  // modern check null pointer
			  if (nullptr != pi && *pi!=1024)
			  {
			      *pi = 1024;
			  }
			  ```
	- ## 🌓Complement
		- [[Reference]]
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
		- 📌nullness of pointer
			- In C++, there are 3 things representing the nullness.
				- integral `0`
				- `NULL`
				- `nullptr` literal
			- Use `nullptr` rather than others. Because it kills the ambiguity of overloading function with pointers and integral type.
			  
			  ``` c++
			  // 3 overloading function of f
			  void f(int);
			  void f(bool);
			  void f(void*);
			  
			  f(0);  //🙁call f(int), not f(void*)
			  f(NULL);  //🙁might not compile, but typically calls f(int). Never calls f(void*)
			  f(nullptr);  //😊call f(void*) overload
			  ```
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases).
		- Pitfall on undefined behavior
			- Description
				- dereference a null C/C++ raw pointer will cause [[Undefined Behavior]] like [this](((63082850-6985-44f0-9172-349283801310)))
			- Solution
				- Therefore, to [guard against dereferencing a null pointer](((63107a40-7df6-42ef-8c1c-9581169b1eff))), we must assure if its address value is zero/null before using...
			- Exception
				- But there is no need to check reference since reference must be initialized at the beginning.
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?
	- ## 🥼Expert's Advice
		- Lippman had words to beginner "Be patient when you are learning pointer. The initial **complexity** of using a pointer comes from its <u>confusing syntax</u>".🤣
	- ## 🧱Structure
	  Any other hierarchical issues?