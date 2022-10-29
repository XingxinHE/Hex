alias:: type conversion, type cast

- ## 📝Definition
	- A cast doesn’t change its operand and it produces a new value.
- ## 🏷(Sub)Categories
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
- ## ⌨Sample Code
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