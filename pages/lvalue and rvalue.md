---
aliases: [lvalue, rvalue, lvalue reference, rvalue reference]
---

# 📝Definition

By #EricRoberts , 
> In #cpp , any expression that refers to an internal memory location capable of storing data is called ==lvalue==.

By #CppPrimer, 
> an lvalue expression yields an object or a function.

By 👨‍🔬Herb Sutter
> Everything that has a name is a lvalue, everything that doesn't is a rvalue.

By 👨‍🔬Stephan T. Lavavej
> If you can get its address, its an lvalue, otherwise its an rvalue.

rvalue has data but it does not have [[memory|memory address]]. e.g. [[Literal]].
# ✒Notation
***lvalue*** pronounced "ell-value".
***rvalue*** pronounced "are-value".
# ⛈Properties
The following properties apply to lvalues in C++:
- Every lvalue is stored somewhere in [[memory]] and therefore has an [[memory|memory address]].
- Once it has been declared, the address of an lvalue never changes, even though
the contents of those memory locations may change.
- The address of an lvalue is a [[pointer]] value, which can be stored in memory and
manipulated as data.

# 🌓Complement
lvalue - rvalue

# 🗃Example
📌lvalue and rvalue example
```cpp
int num = 3;
```
`num` is lvalue. `3` is rvalue.

