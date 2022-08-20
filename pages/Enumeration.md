alias:: enum

- # 😎Quick Digest -> enum
	- ## 📝Definition
	  An enum (an enumeration) is a very simple [[user-defined]] type, specifying its set of values (its *enumerators*) as symbolic constants.
	- ## 🎯Intent
	  An enumeration is **useful** whenever we need a set of related named integer constants. That happens all the time when we try to represent sets of alternatives (`up`, `down`; `yes`, `no`, `maybe`; `on`, `off`; ) or distinctive values (`red`, `blue`, `green`, `yellow`, `maroon`, `crimson`, `black`)
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
		- C++ `enum` has 2 categories.
			- scoped `enum`. 👈✅prefer
			  id:: 6314c5b0-cbef-46b6-9790-a12c63648f4a
			- unscoped("plain") `enum`
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
		- For C++, “plain” `enum`s are less strict than `enum class`es. Their enumerators can “**pollute**” the scope in which their enumerator is defined.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- C++ `enum`
			- scoped `enum` uses `enum class` keywords
				- ``` c++
				  enum class Month {
				  	jan=1, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec
				  };
				  ```
			- unscoped `enum`
				- ``` c++
				  enum Month { // note: no “class”
				  	jan=1, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec
				  };
				  ```
			- 📌comparison of **scoped** `enum` and **unscoped** `enum` in C++
				- ``` c++
				  //scoped enum (recommend👍)
				  
				  Month m = Month::feb;	// ✅explicit identify the scope by using `::`
				  Month m2 = feb; 		// ❌error: feb is not in scope
				  m = 7; 					// ❌error: can’t assign an int to a Month
				  int n = m; 				// ❌error: can’t assign a Month to an int		👈KEY difference
				  Month mm = Month(7); 	// convert int to Month (unchecked)
				  ```
				- ``` c++
				  //unscoped enum (not recommend👎)
				  
				  Month m = feb; 			// 🆗OK: feb in scope
				  Month m2 = Month::feb;  // 🆗also OK
				  m = 7; 					// ❌error: can’t assign an int to a Month
				  int n = m; 				// 🆗OK: we can assign a Month to an int		👈KEY difference
				  Month mm = Month(7); 	// convert int to Month (unchecked)
				  ```
				- Similarly, having an enumeration value convert to `int` can be a convenience (it saves us from being explicit when we want a conversion to `int`), but occasionally it leads to surprises😲. 
				  ``` c++
				  void my_code(Month m)
				  {
				      if (m==17) do_something(); // 🤔huh: 17th month?
				      if (m==monday) do_something_else(); // huh: compare month to Monday? 🤔 maybe wrong or right... I don't know...
				  }
				  ```
				  We can benefit the rule that scoped `enum` doesn't allow enumerator convert to `int` directly.
				-
		- C# `enum`
			- ``` c#
			  enum Season
			  {
			      Spring,
			      Summer,
			      Autumn,
			      Winter
			  }
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