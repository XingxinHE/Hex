---
aliases: [nullptr]
---

# 📝Definition
In #cpp  , there are 3 things representing the nullness of a [[pointer]].
- integral `0`
- `NULL`, legacy, defined in `<cstddef>`
- `nullptr` literal (👍prefer)  #cpp11

# 🕳Pitfalls
Avoid overloading on integral and pointer types!
```cpp
//❌BAD design
void f(int);
void f(void*);
```


# ⌨Sample Code
📌why `nullptr`
Use `nullptr` rather than others. Because it kills the ambiguity of overloading function with pointers and integral type.
```cpp
// 3 overloading function of f
void f(int);
void f(bool);
void f(void*);

f(0);  //🙁call f(int), not f(void*)
f(NULL);  //🙁might not compile, but typically calls f(int). Never calls f(void*)
f(nullptr);  //😊call f(void*) overload
```

# 🧬Related Elements
[[null keyword]]