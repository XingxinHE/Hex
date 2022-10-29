- ## 🕳Pitfalls
	- 📌Avoid complicated expressions
	  id:: 63145dc9-507f-476b-a516-23ec9b831747
		- The **RULE**: if you change the value of a variable in an expression, don’t read or write it twice in that same expression.
		- ``` c++
		  v[i] = ++i; 					 // ❌don’t: undefined order of evaluation
		  v[++i] = i; 					 // ❌don’t: undefined order of evaluation
		  int x = ++i + ++i;  			 // ❌don’t: undefined order of evaluation
		  cout << ++i << ' ' << i << '\n'; // ❌don’t: undefined order of evaluation
		  f(++i,++i); 					 // ❌don’t: undefined order of evaluation
		  ```
		- The preceding code is bad in portability. Regarding various compilers, some work while some don't. Note in particular that `=` (assignment) is considered just another operator in an expression, so there is no guarantee that the left-hand side of an assignment is evaluated before the right-hand side.
		- **Fun Fact**😅... I used to think this is kind of cool...