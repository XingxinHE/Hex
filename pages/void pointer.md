# ✒Notation
```cpp
void*
```

# 🧠Intuition
The `void*` means "pointer to some memory that the compiler doesn't know the type of".

# 🎯Intent
The design of `void*` is to interact with programming languages does not designed for [[type safety]]. That is, a chunk of memory does not know its type.


# 🕳Pitfalls

> [!warning] Warning
> `void*` is a void pointer. Don't mix up with:
> - a variable type (until now, there is no variable is `void` type across all the languages)
> - a return type (the `void` in `void setValue(int)` is a return type.)


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


# 🧬Related Elements
`void*` always play with [[Type conversions|type cast]].