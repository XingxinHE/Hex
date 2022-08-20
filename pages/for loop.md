- # 😎Quick Digest -> title
	- ## 📝Definition
	  In programming, there 2 ways of for loop in general.
		- traditional for loop
		- range for loop
	- ## ⌨Sample Code
	   Code fragments
		- traditional for loop
			- C++
				- iterating using index
					- ``` c++
					  // 1.Counting from 1 to 100
					  for (int i = 1; i <= 100; i++);
					  
					  // 2.Counting by sevens starting at 0 until the number has more than two digits
					  for (int i = 0; i < 100; i += 7);
					    
					  // 3.Counting backward by twos from 100 to 0
					  for (int i = 100; i >= 0; i -= 2);
					  ```
		- range for loop
			- C++
				- the `foreach.h` is deprecated. Use the `for ( for-range-declaration : expression )` syntax.
				- ``` c++
				  vector<int> v = {5, 7, 9, 4, 6, 8};
				  for (int x : v) // for each x in v
				  {
				    cout << x << '\n';
				  }
				  ```
			- C#
				- ``` c#
				  var fibNumbers = new List<int> { 0, 1, 1, 2, 3, 5, 8, 13 };
				  foreach (int element in fibNumbers)
				  {
				      Console.Write($"{element} ");
				  }
				  ```
			- JavaScript
				- ``` javascript
				    let result = '';
				    for (const i in obj) {
				      result += `${objName}.${i} = ${obj[i]}<br>`;
				    }
				  ```
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
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
	   The closest element to current one, what are their differences?
	- ## 📋Prerequisite
	  Some techniques and objects only work under certain condition.
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?