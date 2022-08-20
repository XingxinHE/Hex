alias:: type conversion, type cast

- # 😎Quick Digest -> Type conversion
	- ## 📝Definition
	  A cast doesn’t change its operand and it produces a new value.
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
		- In C++, type conversions can be categorized like so.
			- In terms of technical perspective
				- Implicit type conversions
					- [[widening conversion]]
					- [[narrowing conversion]]
					- Signed - unsigned conversions
					- Pointer conversions
				- Explicit conversions (cast)
					- Explicit conversion often refers to the term "cast".
					- Done by type-conversion operator.
						- `static_cast`
						- `dynamic_cast`
						- `const_cast`
						- `reinterpret_cast`
			- In terms of [[Type Safety]]
				- Safe Conversion. a.k.a. the bit of `later type` ≥ `current type`. see [this](((63100723-98b5-48d1-937b-b976678e34fe)))
				- Unsafe Conversion. a.k.a the bit of `later type` < `current type`. see [this](((6310049f-38c7-4bb1-8319-52ff81e43f9b))) and [this](((63100740-faf3-4822-902f-edf5567a2aa1)))
	- ## ⚖Laws  
	  The laws related to this math concepts.
		- 📌Type conversion hierarchy in C++
			- TODO  This is by Robert Erics, not sure if it is outdated...
			- | Type           | Hierarchy(most precise on the top) |
			  | -------------- | ---------------------------------- |
			  | long double    | ➕➕➕➕➕➕➕➕➕                          |
			  | double         | ➕➕➕➕➕➕➕➕                           |
			  | float          | ➕➕➕➕➕➕➕                            |
			  | unsigned long  | ➕➕➕➕➕➕                             |
			  | long           | ➕➕➕➕➕                              |
			  | unsigned int   | ➕➕➕➕                               |
			  | int            | ➕➕➕                                |
			  | unsigned short | ➕➕                                 |
			  | char           | ➕                                  |
	- ## 🎯Intent
	   A short description what does this thing do?
	- ## 🧠Intuition
	  From one type to another.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- Safe Conversion🆗
		  id:: 63100723-98b5-48d1-937b-b976678e34fe
		  
		  ``` c++
		  char c = 'x';
		  int i1 = c;
		  int i2 = 'x';
		  ```
		- Unsafe Conversion❌
		  id:: 63100740-faf3-4822-902f-edf5567a2aa1
		  
		  ``` c++
		  int a = 20000;
		  char c = a; // ❌try to squeeze a large int into a small char
		  int b = c;
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
	- ## 🥼Expert's Advice
	  See what experts addressed.
	- ## 🧱Structure
	  Any other hierarchical issues?