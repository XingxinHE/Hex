alias:: pass-by-const-reference, pass-by-reference-to-const

- # 😎Quick Digest -> pass-by-reference
	- ## 📝Definition
	  Pass by reference typically means pass the argument by reference.
		- In C++,
			- we use [[&]] in a method signature to indicate pass by reference.
			- Particularly, there is a sub-domain which has different name but is the same thing.
				- pass-by-const-reference
				- pass-by-reference-to-const
		- In C#,
			- we use `ref` keyword to indicate pass [[Value Type]] variables by reference
			- for [[Reference Type]] variables, it is pass by reference by nature in C#.
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 😲Intuitive Explanation
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
		- In C++,
			- pass-by-reference on [[user-defined]] class object is more efficient.
	- ## ⌨Sample Code
	   Code fragments
		- example of "pass-by-const-reference" and "pass-reference-to-const"
			- ```c++
			  //pass-by-const-reference
			  void print(const vector<int> &v)
			  ```
			- ``` c++
			  //pass-by-reference-to-const
			  void print(vector<int> const &v);
			  ```
	- ## 🌓Complement
	  [[pass-by-value]]
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
	- ## 🥼Expert's Advice
		- Lippman address "I recommend *not* passing built-in types by reference. The reference mechanism is primarily intended to support the passing of class objects as parameters to functions."
	- ## 🕳Pitfalls
	  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
		- In C++,
			- 📌 `&` only modify the variable it applies to
				- ``` c++
				  // ❌ Although the values is passed by reference.
				  // The `values` does not change since it takes out the
				  // elem as value, and increment the elem
				  void func1(vector<int> &values)
				  {
				          for(int elem : values)  //👈there is no `&` here. So no modification on `values`
				          {
				                  elem++;
				          }
				  }
				  
				  // ✅ It does change! Since it is sliced with `int &elem`
				  // to indicate we slice the reference out of `values`
				  void func2(vector<int> &values)
				  {
				          for(int &elem : values)
				          {
				                  elem++;
				          }
				  }
				  
				  // ✅ It does change! Since `values` is passed by reference,
				  // and we are modifying the `values` itself
				  void func3(vector<int> &values)
				  {
				          for(int i = 0; i < values.size(); i++)
				          {
				                  values[i]++;  //👈because we refer to `values` itself
				          }
				  }
				  ```
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?
		- 📌⭐Our rule of thumb of choosing "pass-by-value", "pass-by-reference", "pass-by-const-reference" in C++
		  id:: 63144c90-cf63-4e2c-8cc6-e2c8be6b003d
			- Use pass-by-value to pass very small objects. e.g. 1~2 `int` or 1~2 `double`
			- Use pass-by-const-reference to pass large objects that you don’t need to modify.
			- Return a result rather than modifying an object through a reference argument.
				- ``` c++
				  int incr1(int a) { return a+1; } // return the new value as the result
				  void incr2(int& a) { ++a; } // modify object passed as reference
				  int x = 7;
				  
				  x = incr1(x); // 😉pretty obvious
				  incr2(x); //😶pretty obscure
				  ```
			- Use pass-by-reference only when you have to. e.g. modify few objects in 1 function
				- ``` c++
				  void larger(vector<int>& v1, vector<int>& v2)
				    // make each element in v1 the larger of the corresponding
				    // elements in v1 and v2;
				    // similarly, make each element of v2 the smaller
				  {
				    if (v1.size()!=v2.size()) error("larger(): different sizes");
				    for (int i=0; i<v1.size(); ++i)
				    if (v1[i]<v2[i])
				    swap(v1[i],v2[i]);
				  }
				  ```
				- It is usually **best to avoid functions that modify several objects**. In theory, there are always alternatives, such as returning a class object holding several values.
	- ## 🧱Structure
	  Any other hierarchical issues?