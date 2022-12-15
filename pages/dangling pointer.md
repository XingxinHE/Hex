---
aliases: [wild pointer]
tags:
  - cpp
  - c
  - error-prone
---
# 📝Definition
Dangling pointers and wild pointers in computer programming are _pointers that do not point to a valid object of the appropriate type_.
# 🗃Example
What `g()` return is a dangling pointer. Because `i` will be destroyed out of scope and therefore its address has meaningless value.
```cpp
int *g()
{
    int i = 0;
    return &i;
}

int *p = g();
```