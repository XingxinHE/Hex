- ## 📝Definition
	- A scope is a region of program text. A name is declared in a scope and is valid (is “in scope”) from the point of its declaration until the end of the scope in which it was declared.
- ## 🏷(Sub)Categories
	- In C++, there are several kinds of scopes:
		- The global scope: the area of text outside any other scope
		- A namespace scope: a named scope nested in the global scope or in another namespace; see §8.7
		- A class scope: the area of text within a class; see §9.2
		- A local scope: between `{ . . . }` braces of a block or in a function argument list
		- A statement scope: e.g., in a for-statement
- ## 🥼Expert's Advice
	- By Bjarne,
		- For most purposes, **locality is good**, so keep names as local as possible. Avoid global variable as much as you can.
		- **Be very suspicious when you see global variables** with nontrivial initializers; consider any initializer that isn’t a constant expression complicated.
- ## ⌨Sample Code
	- In C++,
		- 📌Functions within class(member function) scope can be defined both "in" and "out" of a class.
			- This is the most common and useful.
			- ``` c++
			  class C
			  {
			    public:
			    void f();
			    void g() // ✅a member function can be defined "in" its class
			    {
			      //..
			    }
			    // . . .
			  };
			  
			  
			  void C::f() // ✅a member function can be defined "out" of its class
			  {
			    // . . .
			  }
			  ```
		- 📌Classes within classes: member classes (also called nested classes)
			- This tends to be useful only in complicated classes; remember that **the ideal is to keep classes small and simple**.
			- ``` c++
			  class C {
			  public:
			    class M {
			    // . . .
			    };
			    // . . .
			  };
			  ```
		- 📌Classes within functions: local classes
			- 🆗 to compile. But avoid this❌! If you feel the need for a local class, your function is probably far too long.
			- ``` c++
			  void f()
			  {
			    class L {
			    // . . .
			    };
			    // . . .
			  }
			  ```
		- 📌Functions within functions: local functions (also called nested functions)
			- ❌illegal in C++ and can't be compiled.
			- ``` c++
			  void f()
			  {
			    void g() // ❌illegal
			    {
			    // . . .
			    }
			    // . . .
			  }
			  ```
		- 📌Blocks within functions and other blocks: nested blocks
			- Nested blocks are unavoidable, but be suspicious of complicated nesting: it can **easily hide errors**🤫.
			- ``` c++
			  void f(int x, int y)
			  {
			    if (x>y) {
			    // . . .
			    }
			    else {
			    	// . . .
			      {
			      	// . . .
			      }
			    // . . .
			    }
			  }
			  ```