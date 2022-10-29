alias:: uniform initialization

- ## 📝Definition
- ## 🧠Intuition
	- “Uniform initialization” is an idea.
	- “Braced initialization” is a syntactic construct.
- ## 🚀Benefit / Pros
	- In C++
		- `{}` - initializers do not allow [[narrowing]] conversions (and that is usually a good thing) and allow explicit constructors (which is fine, we’re intentionally initializing a new variable).
		- `{}` initialization can be used for nearly all initialization; other forms of initialization can’t.
		- immune to C++'s [most vexing parse](((630f1d55-88a6-48b8-9d86-9ad1db187eaa)))
- ## 🔗Supplement Links
	- [ES.23: Prefer the {}-initializer syntax](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#es23-prefer-the--initializer-syntax)
- ## 🥼Expert's Advice
	- By Scott Meyer,
		- To Class Author
			- Be careful the [pitfalls](((630f2733-1234-4c42-9f66-dbcc5fce8464))) especially when your class current/future has `std::initializer_list`.
		- To Class Client
			- Don't be addicted to only one initialization syntax. Both technique have their pros and cons.
		- To Template Author
			- This is super challenging! Please refer to pitfalls as well. And the "Item 7" in Effective Modern C++.
- ## ⌨Sample Code
	- In C++,
		- use `{}` to initialize built-in data type
		  
		  ``` c++
		  int k {10};
		  ```
		- `{}` initialization prevents narrowing
		  id:: 630eca65-19f9-43ab-a15c-788af07093ab
		  ``` c++
		  int x {7.9};   // ❌error: `{}` init prevent narrowing, from floating point to integral
		  int y = 7.9;   // OK: `=` init does not prevent narrowing. y becomes 7. Hope for a compiler warning
		  int z = gsl::narrow_cast<int>(7.9);  // OK: you asked for it
		  ```
		- `{}` initialization apply on different cases
		  
		  ``` c++
		  // initialized vector
		  auto p = new vector<int> {1, 2, 3, 4, 5};
		  
		  // member initializer (e.g., m might be a pair)
		  D::D(int a, int b)
		    :m{a, b}			//👈
		  {   
		      // ...
		  };
		  
		  // initialize variable
		  X var {};
		  
		  // default initializer for a data member
		  struct S
		  {
		      int m {7};   //👈
		      // ...
		  };
		  ```
		- for [[STL]]⭐, the `{}` initialization and [[() - initialization syntax]] have their own convention
		  id:: 63085b45-18f8-4319-a9b8-af232df71776
			- {{embed ((630eca65-d6aa-4f27-8a7a-2d9a70dcd498))}}
- ## 🕳Pitfalls / Cons
	- In C++,
		- 📌mix the use of [[auto]] and `{}` initialization should be cautious
		  id:: 630eca65-e79b-412a-a191-fd422dc43db1
			- ``` c++
			  auto x1 {7};        // x1 is an int with the value 7
			  auto x2 = {7};      // x2 is an initializer_list<int> with an element 7
			  
			  auto x11 {7, 8};    // ❌error: two initializers
			  auto x22 = {7, 8};  // x22 is an initializer_list<int> with elements 7 and 8
			  ```
			- Therefore, Use  `={...}`  if you really want an  `std::initializer_list<T>`
		- 📌Warning on [[Constructor]] having `std::initializer_list`
		  id:: 630f2733-1234-4c42-9f66-dbcc5fce8464
			- Similar to the [last pitfall](((630eca65-e79b-412a-a191-fd422dc43db1))), this also applies to [[Designing Class]].
			- Remember one rule - "Calls using the braced initialization syntax strongly prefer the overloads taking `std::initializer_lists`"
			- The pitfall can be explained by following examples.
				- example 1
					- Context Brief
					  ``` c++
					  class Widget
					  {
					  public:
					    Widget(int i, bool b);
					    Widget(int i, double d);
					    Widget(std::initializer_list<bool> il); // element type is bool 👈pay attention here
					    … // no implicit conversion funcs
					  };
					  ```
					- Pitfall occurs
						- If I call the following code.
						  
						  ``` c++
						  Widget w{10, 5.0}; // ❌error! requires narrowing conversions
						  ```
						- Very interesting!! Because `std::initializer_lists` has privilege and therefore the constructor with `std::initializer_lists` prevails!
							- ❌not call `Widget(int i, bool b);`
							- ❌not call `Widget(int i, double d);`
							- ✅call `Widget(std::initializer_list<bool> il);`
						- By calling the 3rd constructor, `10, 5.0` now need to go through type conversion. In this case, it is [[narrowing conversion]]. Therefore it is a compile-error!
					- How to solve this?
						- By using [[() - initialization syntax]] can solve that!
						- By calling
						  
						  ``` c++
						  Widget w(10, 5.0); // ✅
						  ```
						- This will result
							- ❌not call `Widget(int i, bool b);`
							- ✅call `Widget(int i, double d);`
							- ❌not call `Widget(std::initializer_list<bool> il);`
				- example 2
					- The last example is not that bad since the compiler helps you. The worst case is the logic error is hiding underneath...
					- Context Brief
					  
					  ``` c++
					  class Widget
					  {
					  public:
					    Widget(int i, bool b);
					    Widget(int i, double d);
					    Widget(std::initializer_list<long double> il); // element type is double 👈pay attention here
					    … // no implicit conversion funcs
					  };
					  ```
					- Pitfall occurs
						- When you call the following...
						  
						  ``` c++
						  Widget w{10, 5.0};
						  ```
						- Because `std::initializer_lists` has privilege and therefore the constructor with `std::initializer_lists` prevails!
							- ❌not call `Widget(int i, bool b);`
							- ❌not call `Widget(int i, double d);`
							- ✅call `Widget(std::initializer_list<long double> il);`
						- It won't have compile-error. But this is SUPER BAD! Imagine you have different implementation regarding different constructors... And imagine this is how the engine works in rocket science... The result can be horrible.
					- How to solve this?
						- Similar to the last solution.
		- 📌pay attention to use `{}` init when encountering [[explicit]] keyword
			- `{}`  accepts  `explicit`  constructors
			- `={}`  does not accepts `explicit` constructor
			- ``` c++
			  struct Z { explicit Z() {} };
			  
			  Z z1{};     // ✅OK: direct initialization, so we use explicit constructor
			  Z z2 = {};  // ❌error: copy initialization, so we cannot use the explicit constructor
			  ```
			- Use plain  `{}` -initialization unless you specifically want to disable explicit constructors.