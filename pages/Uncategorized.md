- `cout` = character output stream.
- difference between `cout` and `cerr`:
	- `cout` is optimized
	- `cerr` is not optimized and it is more resilient to errors.
- C++ error
	- compile-time error found by compiler
	- link-time error found by linker
	- run-time error / logic error... hard to fix
- ``` c++
  cout << "Hello, ";
  cout << first_name;
  cout << "!\n";
  ``` 
  
  However, we are indifferent typists, and — more importantly — strongly dislike
  needless repetition (because repetition provides opportunity for errors),
- how do we express a program as a set of cooperating parts and how can they share and exchange data? These are key questions in programming. We can illustrate that graphically:
- Our main tool for organizing a program — and for organizing our thoughts
  as we program — is to break up a big computation into many little ones. This
  technique comes in two variations:
	- abstraction
	- divide and conquer
- Bjarne recommended don't use `extern` too often.
- The C++ definition requires declaration before use (except for class members; see §9.4.4).
	- TODO verify this
- Comparison between function declaration and function definition
	- In C++, the following is allowed.
		- ``` c++
		  int my_find(vector<string> vs, string s, int hint); // naming arguments
		  int my_find(vector<string>, string, int); // not naming arguments
		  ```
	- However, in C#, the preceding concept is not allowed.
		- ❌
		  
		  ``` c#
		  internal interface ICalculator
		  {
		    double Calculate(double, double);  //👈can't be compiled
		  }
		  public double Calculate(double x, double y)
		  {
		    return x * y;
		  }
		  ```
		- ✅
		  ``` c#
		  internal interface ICalculator
		  {
		    double Calculate(double x, double y);
		  }
		  public double Calculate(double x, double y)
		  {
		    return x * y;
		  }
		  ```
- Experience shows that “hoping” can lead to “pretty good” programs. However, producing “pretty good” programs that occasionally produce erroneous results and occasionally crash is no way to win friends and respect as a professional. We prefer to write code that can be demonstrated to be correct.
- In mathematics, always try to get used to the notation. e.g.
  $$
  f(x)=a^Tx\\f(0)=0
  $$
  $f(x)$ is a linear function and the `0` inside the `f` is a vector filled with `0`. The rhs 0 is a scalar. This is called the overloading of a symbol... lol