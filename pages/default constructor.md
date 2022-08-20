- # 😎Quick Digest -> Default Constructor
	- ## 📝Definition
	  A default constructor is one that can be called without any arguments. Such a constructor either has no parameters or has a default value for every parameter.
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 😲Intuitive Explanation
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
		- Code on is/is-not a default constructor
		  
		  ``` c++
		  class A
		  {
		  public:
		    A();		//a default constructor.✅
		  };
		  
		  class B
		  {
		  public:
		    explicit B(int x = 0, bool b = true);		//a default constructor✅
		  };
		  
		  class C
		  {
		  public:
		    explicit C(int x);		//❌NOT a default constructor
		  };
		  
		  ```
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
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?
	- ## 🧱Structure
	  Any other hierarchical issues?