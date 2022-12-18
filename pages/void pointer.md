# ✒Notation
```cpp
void*
```

# 🧠Intuition
The `void*` means "[[pointer]] to some memory that the compiler doesn't know the type of".

# 🎯Intent
The design of `void*` is to interact with programming languages does not designed for [[type safety]]. That is, a chunk of memory does not know its type.

# 🚀Benefit / Pros
These pointers can be used to allocate memory of **any [[type|data type]]**.

# 🩹Cons
-   The behavior of [[Type conversions|type casting]] is [[Undefined Behavior|undefined]].
-   No [[pointer#💫Operation#pointer arithmetic|pointer arithmetic]]


# 🕳Pitfalls

> [!warning] Warning
> `void*` is a void pointer. Don't mix up with:
> - a variable type (until now, there is no variable is `void` type across all the languages)
> - a return type (the `void` in `void setValue(int)` is a return type.)

# 🗃Example
**📂example of the behavior of type casting is undefined**
Remember, casting `void *` to `T *` is dangerous!📝 The result is always undefined.

```c
// using `void *` pointer in C
Gadget *pg;
Widget *pw;

void *pv;

pv = pg;  // 🆗 in C
pw = pv;  // 🆗 in C
```

The preceding codes are permitted in C. There is no compile error, but the behavior is **<u>undefined</u>**. (equivalent to pass `pg` to `pw`)

```c++
// using `void *` pointer in C++
Gadget *pg;
Widget *pw;

void *pv;

pv = pg;            // 🆗 in C++
pw = (Widget *)pv;  // 🆗 MUST explicitly cast
```

The preceding codes are permitted in C++. The behavior is also <u>**undefined**</u>.



**📂example of inability of pointer arithmetic**
The following code are with errors.
```c++
*pv;    //❌. No dereference.
++pv;   //❌. No pointer arithmetic
--pv;   //❌. No pointer arithmetic
pv++;   //❌. No pointer arithmetic
pv--;   //❌. No pointer arithmetic
pv[i];  //❌. No indexing due to no pointer arithmetic
```



# ⌨Sample Code
📌 basic syntax using `void*`
```cpp
void v;   // ❌error: there are no objects of type void
void f(); // 👌f() returns nothing — f() does not return an object of type void
void* pv1 = new int; // ✅OK: int* converts to void*
void* pv2 = new double[10]; // ✅OK: double* converts to void*
```

📌 `void*` and type cast
```cpp
void f(void* pv)
{
	void* pv2 = pv; // ✅copying is OK (copying is what void*s are for)
	double* pd = pv; // ❌error: cannot convert void* to double*
	*pv = 7; ❌// error: cannot dereference a void*
	pv[2] = 9; ❌// error: cannot subscript a void*
	int* pi = static_cast<int*>(pv); // ✅OK: explicit conversion
}
```


# 🌱Related Elements
`void*` always play with [[Type conversions|type cast]].
