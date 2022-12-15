---
tags:
  - cpp
---

# 📝Definition
It is defined in header `<cstddef>`. It is the [[signedness|signed]] integer type of the result of subtracting two [[pointer]]s.

# 🎯Intent
Use in [[pointer#💫Operation#pointer arithmetic]].

# 🗃Example
```cpp
int array[5] = {1, 2, 3, 4, 5};
int *p3 = &array[2];
int *p5 = &array[4];

ptrdiff_t diff = -2;

if(diff == (p3 - p5))
{
    cout << "This is valid";
}
```
