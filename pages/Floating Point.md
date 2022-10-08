alias:: floating point type

- # 📝Definition
	- The real numbers $\mathbb{R}$ are stored in **floating point format**. It is either *64-bits* or *8-bytes*. Therefore, there are $2^{64}$ real numbers in a `x64` computer.
- Floating point is the computer's approximation to the mathematical concept of real number.
- Floating-point with [[scientific notation]]
	- In C++,
		- For $10^{8}$
		- ```c++
		  double num = 2.9979E+8;
		  ```
		- `E` just means base $10$ I think...
	- In C#,
		- ``` c#
		  double d = 0.42e2;
		  Console.WriteLine(d);  // output 42
		  
		  float f = 134.45E-2f;
		  Console.WriteLine(f);  // output: 1.3445
		  
		  decimal m = 1.5E6m;
		  Console.WriteLine(m);  // output: 1500000
		  ```
- # 💫Operation
	- 📌floating point operation
		- When computer carries out arithmetic operation, the result is rounded to the nearest floating point number. The very small error is called **round-off error**. Now you understand why you can't compare the *equality* of `float`. Because the left hand side and right hand side are not equal sometimes!! But the error between is extremely small.
	- 📌flop
	  id:: 632141f6-8c0c-40c2-bab8-bce388937019
		- It means <u>floating point operation per second</u>.