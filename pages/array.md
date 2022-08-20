- # 😎Quick Digest -> Array
	- ## 📝Definition
	  The name is the essence of this topic.
		- In mathematics,
			- An array is a "list of lists" with the length of each level of list the same. The size (sometimes called the "shape") of a $d$-dimensional array is then indicated as $\underbrace{m×n×...×p}_{d}$. The most common type of array encountered is the two-dimensional $m×n$ rectangular array having $m$ columns and $n$ rows. If $m=n$, a square array results.
		- In C#,
			- The language designers wrap the mathematical concept into [[data structure]] [Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/) which supports single-dimensional, multidimensional or jagged.
		- In C/C++,
			- we often refer to the data structure which is a fixed-length and single-dimensional. Due to the legacy reason, we have 2 forms of array.
				- C-Style array (👎 not recommend, see the [reason](((630f0c9c-63b8-4986-bb3c-b05ae794dd66))))
				- modern C++ `std::array` (👍 recommend.)
	- ## 🏷(Sub)Categories
		- What are the sub objects of this subject?
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 😲Intuitive Explanation
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit / Pros
	   A scenario that illustrates the benefit this object provides.
		- For `std::array`,
			- It does not degenerate to a pointer when passed to a function and does know its size.
	- ## 🕳Pitfalls / Cons
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
		- For C-Style array, this is the cons
		  id:: 630f0c9c-63b8-4986-bb3c-b05ae794dd66
			- the size is fixed
			- The array does not explicitly specify the length of an array. Therefore, we often accompany an integer to track the size.
			- does not support insert and remove operation
			- array does not have bound-checking
	- ## ⌨Sample Code
	   Code fragments
		- C-Style array code example
			- ``` c++
			  // (1)init an array
			  int seq_size = 6;
			  int elem_seq[seq_size] = {
			      1, 2, 3,
			      4, 5, 6
			  };
			  
			  // (2)init an array
			  int elem_seq[] = {
			    1, 2, 3,
			    4, 5, 6
			  };
			  
			  // (3)declared but not initialized
			  int* elem_seq = new int[3];
			  cout << elem_seq[0] << endl;    // 2395876
			  cout << elem_seq[1] << endl;    // -197630894
			  
			  // (4)declared and initialized, not slow in general but a bit slower than (3)
			  int* elem_seq = new int[3]();   //👈 the`()`
			  cout << elem_seq[0] << endl;    // 0
			  cout << elem_seq[1] << endl;    // 0
			  ```
- ## 🌓Complement
  What is the complement of this subject? e.g. vector-covector, constructor-destructor
- ## 🤳Applicability
   What are the situations in which this subject can be applied?
- ## 🧪Composition
  What kind of stuffs composite this subject?
- ## 🔎Implementation
   The code or technical stuffs implement this.
- ## 🧬Related Elements
	- In C++,
		- 📌an array is also a [[pointer]]
			- ```c++
			  //The followings are the same!
			  array[2];
			  *(array + 2);
			  ```
			- If you are a C# programmer, you would say what the heck?? 😨😨 That's because an <u>array is a pointer which records the 1st address of that array</u>. Therefore, they are the same.
- ## 📋Prerequisite
  Some techniques and objects only work under certain condition.
- ## 🥼Expert's Advice
- ## 🧱Structure
  Any other hierarchical issues?