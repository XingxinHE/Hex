# 📝Definition
Expression is a [[Tuple|sequence]] of operators and their operands which specify some computation process.
# ⛈Characteristics
It is characterized by 2 factors:
- [[type|data type]]
- [[value categories]]
# 🌓Complement
![[type#🌓Complement#Data Type vs. Expression]]

# 🕳Pitfalls
- 📌Avoid complicated expressions ^676303de228f35c6
    - The **RULE**: if you change the value of a variable in an expression, don’t read or write it twice in that same expression.
    - ``` c++
      v[i] = ++i; 					 // ❌don’t: undefined order of evaluation
      v[++i] = i; 					 // ❌don’t: undefined order of evaluation
      int x = ++i + ++i;  			 // ❌don’t: undefined order of evaluation
      cout << ++i << ' ' << i << '\n'; // ❌don’t: undefined order of evaluation
      f(++i,++i); 					 // ❌don’t: undefined order of evaluation
      ```
    - The preceding code is bad in portability. Regarding various compilers, some work while some don't. Note in particular that `=` (assignment) is considered just another operator in an expression, so there is no guarantee that the left-hand side of an assignment is evaluated before the right-hand side.
  **Fun Fact**😅... I used to think this is kind of cool...
  