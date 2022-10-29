- ## 🔎Implementation
	- The copy constructor defines how an object is [[pass-by-value]].
- ## 🕳Pitfalls
	- It is generally a bad idea to pass-by-value for [[user-defined]] type. [[pass-by-const-reference]] is a typically a better idea.
- ## 🙋‍♂️Related Elements
	- [[Copy Assignment Operator]]
-
- How to distinguish Copy Constructor and [[Copy Assignment Operator]]?
	- By logic
		- If a **new object** is being defined, a constructor has to be called.
		- If **NO new object** is being defined, no constructor can be involved, so it's an assignment.
	- By example
	  ``` c++
	  Widget w1;
	  Widget w2(w1);  //new object w2 -> invoke copy constructor
	  w1 = w2;		//no new object -> invoke copy assignment operator
	  Widget w3 = w2; //new object w3 -> invoke copy constructor
	  ```