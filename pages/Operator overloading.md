- ## 📝Definition
  The name is the essence of this topic.
	- In C++, there are 2 ways of operator overloading.
		- <u>Method-based style</u>
		- <u>Free function style</u>
	- In JavaScript,
		- It doesn't support Operator overloading.
- ## 🕳Pitfalls
  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
	- 📌Overload operator ONLY when you have to
		- operator overloading provides such convenience but!! It is generally a good idea not to define operators for a type unless you are really **certain** that it **makes a big positive change** to your code.
- ## 📋Prerequisite
  Some techniques and objects only work under certain condition.
	- For C++ operator overloading, an overloaded operator **must** have **at least one** [[user-defined]] type as operand.
		- ``` c++
		  int operator+(int,int); // ❌error: you can’t overload built-in +
		  Vector operator+(const Vector&, const Vector &); // OK
		  Vector operator+=(const Vector&, int); // OK
		  ```