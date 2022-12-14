---
tags:
  - function
---
# 📝Definition
An `inline` function represents a request to the [[compiler]] to expand the function at each call point. With an `inline` function, the compiler replaces the function call with a copy of the code to be executed.

# 🎯Intent
- To reduce the function call overhead.

# 😲Intuitive Explanation
- 假设一个大方法里面有很多小方法，这些小方法实际上非常小。<u>数据转换过程所占用的时间</u>大于<u>方法运行本身所占用的时间</u>要多，因此才要用`inline` 函数。

# 🥼Expert's Advice
- Bjarne on `inline` function,
    - An `inline` function is only consisted **no more than one or two expressions**.
    
# 🤳Applicability
- `inline` function only suits to **small** function.

# 🎭Analogy
- The analogy of C++  `inline`  function in C# are  `Action<>`  and  `Func<>` .
