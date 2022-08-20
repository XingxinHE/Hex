- # 😎Quick Digest
	- ## 📝Definition and Classification
	  A `constexpr` symbolic constant must be given a value that is known at [[compile-time]].
	- ## 🎯Intent
	   A short description what does this pattern do?
	- ## 🧠Intuition
	  `constexpr` is "conster" than [[const]].
	- ## 🚀Benefit
	   Help [[run-time]] computation into [[compile-time]] computation which let software run faster.
	- ## ⌨Sample Code
		- On Initialization
		  
		  ``` c++
		  int n = 42;
		  constexpr int max = n; //❌ERROR. non-constant initializer
		  constexpr int min = 2; //✅OK. constant init
		  ```
	- ## 🏷(Sub)Categories
	  With `constexpr` keyword, there are few products.
		- `constexpr` function. A function which will be evaluated in compile-time and to avoid having the same calculation done millions of times at run time.
		- `constexpr` variable
	- ## ⌨Sample Code
	   Code fragments
		- example of `constexpr` function
			- Suppose you have the function
			  
			  ``` c++
			  constexpr double xscale = 10; // scaling factors
			  constexpr double yscale = 0.8;
			  
			  //✋the function
			  constexpr Point scale(Point p) { return {xscale*p.x,yscale*p.y}; };
			  ```
			- How you use it.
			  
			  ``` c++
			  void user(Point p1)
			  {
			      Point p2 {10,10};
			      Point p3 = scale(p1); // ✅OK: p3 == {100,8}; `p3` is not declared with `constexpr` and its run-time evaluation is fine
			      constexpr Point p4 = scale(p2); // ✅OK. p4 == {100,8}.  `p4` is declared with `constexpr` and its calculation can all be handled in compile-time
			      constexpr Point p5 = scale(p1); // ❌error: scale (p1) is not a constant and not with const expression
			      // expression
			      constexpr Point p6 = scale(p2); // ✅OK. p6 == {100,8} same with p4
			      // . . .
			  }
			  ```
	- ## 🙋‍♂️Related Elements
	   The closest pattern to current one, what are their differences?
	- ## 🧱Structure
	   A graphical representation of this design pattern.
	- ## 🤳Applicability
	   What are the situations in which the design pattern can be applied?
	- ## 🤼Participants
	   The participated classes and/or objects and their responsibility.
	- ## 🤝Collaborations
	   How the participants work together?
	- ## 📈Consequences
	   The trade-off and results.
	- ## 🔎Implementation
	   What pitfalls, hints, or techniques should be aware of implementing the pattern?
	- ## 🤔Known Issues
	   Examples