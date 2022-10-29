- # 😎Quick Digest -> Declaration
	- ## 📝Definition and Classification
	  A declaration tells compilers about the name and type of something but it **omits** some details.
	- ## 🎯Intent
	   A short description what does this pattern do?
	- ## 😲Intuitive Explanation
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
		- On different categories of declarations:
		  
		  ``` c++
		  extern int x;		// object declaration
		  
		  std::size_t numDigits(int number);		//function declaration
		  
		  class Widget;		//class declaration
		  
		  template<typename T>
		  class GraphNode;		//template declaration
		  ```
		- example of declaration specifiers and declarator
		  
		  ``` c++
		  static unsigned long int            *x[N];
		  /* declaration specifiers */    /* declarator */   /* x is declarator-id */
		  ```
- ## 🌓Complement
  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- 📌Relationship between Declaration and [[Definition]]
	  id:: 630e382f-4c6a-46c2-9c9e-7c9637c54923
		- All definitions are declarations.
		- Not all declarations are definitions.
		-
- ## 🤳Applicability
   What are the situations in which this subject can be applied?
- ## 🧪Composition
  The declaration expression can be divided as 2 parts:
	- a sequence of declaration specifiers
	  id:: 63020af9-4249-4ed2-a628-8b127085e036
	- a declarator
	  id:: 63020af9-5d87-4a89-92fb-4ee153628557
		- declarator-id
- ## 🏷(Sub)Categories
	- By Scott Meyer, The declaration can be subdivided into:
		- object declaration
		- function declaration
		- class declaration
		- template declaration
	- By Bjarne, the declaration can be subdivided into
		- Variables
		- Constants
		- Functions (see §8.5)
		- Namespaces (see §8.7)
		- Types (classes and enumerations; see Chapter 9)
		- Templates (see Chapter 19)
-
- Declaration Specifiers
	- It can be categorized as:
		- type specifier
			- e.g. `int`, `long`, `double`, `string`, `vector<int>`
		- non-type specifier
			- e.g. `extern`, `static`, `virtual`
-
- Declarator Operator
	- | Precedence | Operator | Meaning |
	  | ---- | ---- | ---- |
	  | Highest | () | grouping |
	  | Medium | [] | array |
	  | Medium | () | function |
	  | Lowest | unary * | pointer |
	  | Lowest | unary & | lvalue reference |
	  | Lowest | unary && | rvalue reference |
	- Quiz - what is `*x[N]` ?
		- A. `x` is "a pointer to an array".
		- B. `x` is "an array of pointers".
		- We chose B. Because `[]` has higher precedence than unary `*`.  (Tips: try to read from top to the bottom)
-
- Parentheses in Declarators
	- It has 2 roles:
		- function call operator
			- these `()` follow the declarator-id
		- grouping
			- these `()` enclose the declarator-id
	- example on different uses of parentheses
	  
	  ``` c++
	  // function call operator example
	  *f(int);
	  /* f is a function with parameter of type int returning poitner */
	  
	  // grouping example
	  (*f)(int);
	  /* This becomes a pointer to function. */
	  ```
-
- `const` is a type-specifier
	- The order of the declaration specifiers doesn't matter to the compilers.
	- example of order doesn't matter
	  
	  ``` c++
	  const unsigned long cul;
	  unsigned const long cul;
	  long unsigned const cul;
	  ```
	- once you understand the rule, you can easily notify which is right or wrong?
-
- # 😎Quick Digest -> Alias Declaration
  alias:: type alias
  id:: 630f82a5-8010-4ceb-818e-2800dc04265f
	- ## 📝Definition
	  Alias declaration is to declare a name to use as a synonym for a previously declared type.
	- ## 🎯Intent
		- In C++, Alias declaration is intent to deal with:
			- types involving function pointers.
			  
			  ``` c++
			  // FP is a synonym for a pointer to a function taking an int and
			  // a const std::string& and returning nothing
			  typedef void(*FP)(int, const std::string&);  //typedef
			  
			  // same meaning as above
			  using FP = void(*)(int, const std::string&); //alias declaration is much simpler
			  ```
			- alias templates
			  
			  ``` c++
			  
			  ```