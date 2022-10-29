- ## 🏷(Sub)Categories
  What are the sub objects of this subject?
	- In C++, there are 2 kinds of member access operators of `struct`, `union`, and `class`.
		- `.`
		- `->`
- ## 🧠Intuition
  Find an intuitive way of explanation of this concept.
	- In C++,
		- `->` is a <u>shorthand</u> for **dereference and then access**.
- ## ⌨Sample Code
   Code fragments
	- example of different member access operator in C++
		- syntax difference
		  ``` c++
		  struct Date
		  {
		    int month;
		    int day;
		  };
		  
		  // `.` operator. non-poitner
		  Date d1;
		  d1.month = 4;
		  d1.day = 21;
		  // `->` operator. pointer
		  Date* d2;
		  d2->month = 4;
		  d2->day = 20;
		  ```
		- mechanism difference. The main difference is that the later one ***will not be deleted automatically by the garbage collection***!!
		  
		  ``` c++
		  // non-poitner
		  void foo1()
		  {
		      Date d1;
		      d1.month = 4;
		      d1.day = 21;
		      ...
		      
		      // d1 will be thrown away once out of this scope
		  }
		  
		  // pointer
		  void foo2()
		  {
		      Date* d2;
		      d2->month = 4;
		      d2->day = 20;
		      ...
		      
		      // d2 will be thrown away but what d2 points to will NOT be thrown away!
		  }
		  
		  ```
		- the Interchangeability of `.` and `->`
		  
		  ``` c++
		  // The followings are the same!
		  d2->month = 4;
		  (*d2).month = 4;
		  ```