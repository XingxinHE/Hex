
> [!info] Info
> This is a rarely used stuff in #cpp , so it is totally fine if you don't know about it.


# 📝Definition
In #cpp , [[declaration]] of [[pointer]] to function member is a special case of pointer declaration.



# ⌨Sample Code
📌How to use it
```cpp
bool (Widget::* myMethod) (int, int);
//..

Widget foo;
bool data = (foo->*myMethod)(row, col);
```

📌declaration
```cpp
int (MyClass::*ptr) (double);
```

📌initialization
Assigns the address of the function member to the pointer
```cpp
ptr = &MyClass::myMethod;
```

📌declaration and initialization
```cpp
int (MyClass::*ptr) (double) = &MyClass::myMethod;
```