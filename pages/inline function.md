- # 😎Quick Digest -> `inline` Functions
	- ## 📝Definition
	  An `inline` function represents a request to the compiler to expand the function at each call point. With an `inline` function, the compiler replaces the function call with a copy of the code to be executed.
	- ## 🎯Intent
	  To reduce the function call overhead.
	- ## 😲Intuitive Explanation
	  假设一个大方法里面有很多小方法，这些小方法实际上非常小。<u>数据转换过程所占用的时间</u>大于<u>方法运行本身所占用的时间</u>要多，因此才要用`inline` 函数。
	- ## 🥼Expert's Advice
	  See what experts addressed.
		- Bjarne on `inline` function,
			- An `inline` function is only consisted **no more than one or two expressions**.
	- ## 🤳Applicability
	  `inline` function only suits to **small** function.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🎭Analogy
	  The analogy of C++  `inline`  function in C# are  `Action<>`  and  `Func<>` .
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