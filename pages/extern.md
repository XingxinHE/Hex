- # 😎Quick Digest -> `extern`
	- ## 📝Definition
	  The name is the essence of this topic.
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 😲Intuitive Explanation
	  The `extern` means the following is just declaration, please ignore the parameter name. It does not have any relationships with others.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
		- example on how `extern` used in header files
			- compile-error❌
			  ``` c++
			  const int seq_cnt = 6;
			  const vector<int>* (*seq_array[seq_cnt])(int);  //❌ERROR
			  //It is not right... 
			  //Since the `seq_cnt` as 6 will be passed in the function declaration.
			  //While the declaration is merely declaration.
			  ```
			- `extern` can help✅
			  
			  ``` c++
			  const int seq_cnt = 6;
			  extern const vector<int>* (*seq_array[seq_cnt])(int);
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
	- ## 🥼Expert's Advice
	- ## 🧱Structure
	  Any other hierarchical issues?