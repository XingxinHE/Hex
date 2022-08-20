- # 😎Quick Digest -> Undefined Behavior
	- ## 📝Definition
	  The name is the essence of this topic.
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 😲Intuitive Explanation
	  you can't reliably predict what will happen at [[run-time]].
	- ## 😷Symptoms
	  The program will behave erratically:
		- sometime running normally
		- other times crashing
		- other times produce incorrect results
	- ## ⌨Sample Code
		- 2 examples of code with undefined behavior
		  id:: 63082850-6985-44f0-9172-349283801310
		  
		  ``` c++
		  
		  int *p = 0;		//p is a null pointer
		  std::cout << *p;	//dereferencing a null pointer yields undefined behavior
		  
		  char name[] = "Darla";  //name is an array of size 6(including the last null)
		  char c = name[10];		//referring to an invalid array index yields undefined behavior
		  ```
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  xxx
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?
	- ## 🧱Structure
	  Any other hierarchical issues?