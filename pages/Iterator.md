- # 😎Quick Digest -> Iterator
	- ## 📝Definition
	  *Iterator* is an object that identifies an element of a sequence.
	- ## 🎯Intent
		- In C++
			- More specifically, an iterator is an object that can iterate over elements in a [[C++]] [[STL]] container and provide access to individual elements.
	- ## 😲Intuitive Explanation
	  Use a same and consistent syntax to iterate the [[STL]] container.
	- ## 🚀Benefit
	  Using same syntax and interface provides lots of benefit. For example, the `++` for vector is to query the next element, so as `++` for linked list. But the next address of a linked list cannot be just incremented. Therefore, we can override their operator.
	  
	  ``` c++
	  // no matter which container is
	  // a pseudo code of the iterator could be like this
	  for(iter = numbers.begin(); iter!=numbers.end(); iter++)
	  {
	  
	  }
	  ```
	- ## ⌨Sample Code
	   Code fragments
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
	  [[IEnumerable]]
	- ## 🥼Expert's Advice
	- ## 🧱Structure
	  Any other hierarchical issues?