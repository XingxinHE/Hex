- ## 📝Definition
	- `double` is short for "double-precision" [[Floating Point]].
- ## 🕳Pitfalls
	- 📌⚠pitfall on numeric literal on [[narrowing]]
		- Suppose you are converting degrees Celsius to degree Fahrenheit: $f=9/5*c+32$. It involves [[integral type]]
		- Bad code
		  
		  ``` c++
		  double dc;
		  cin >> dc;
		  double df = 9/5*dc+32; // ❌beware!
		  ```
		- Good code
		  
		  ``` c++
		  double dc;
		  cin >> dc;
		  double df = 9.0/5*dc+32; // ✅better
		  ```