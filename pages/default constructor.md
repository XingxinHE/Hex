- ## 📝Definition
  A default constructor is one that can be called without any arguments. Such a constructor either has no parameters or has a default value for every parameter.
- ## ⌨Sample Code
	- Code on is/is-not a default constructor
	  
	  ``` c++
	  class A
	  {
	  public:
	    A();		//a default constructor.✅
	  };
	  
	  class B
	  {
	  public:
	    explicit B(int x = 0, bool b = true);		//a default constructor✅
	  };
	  
	  class C
	  {
	  public:
	    explicit C(int x);		//❌NOT a default constructor
	  };
	  
	  ```