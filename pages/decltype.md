---
aliases: [decltype specifier]
tags:
  - LanguageKeyword
  - cpp
---
# 📝Definition
The **`decltype`** type specifier yields the type of a specified expression.

# 🚀Benefit / Pros
The **`decltype`** type specifier, together with the [`auto` keyword](https://learn.microsoft.com/en-us/cpp/cpp/auto-cpp?view=msvc-170), is useful primarily to developers who write [[Templates]] libraries.

# 🎯Intent
- 1️⃣ Use [[auto keyword]] and **`decltype`** to declare a function template whose return type depends on the [[type]]s of its template arguments.
- 2️⃣ Use **`auto`** and **`decltype`** to declare a function template that wraps a call to another function, and then returns the return type of the wrapped function.

# ✒Notation
```cpp
decltype( expression );
```
- parameter: An [[Expression]]
- return type: the type of the _`expression`_ parameter

# ⚖Laws
The laws of how `decltype` works.⭐⭐⭐
- 1️⃣  If the _`expression`_ parameter is an [[variable|identifier]] or a [[Member access operator|class member access]], `decltype(expression)` is the type of the entity named by _`expression`_. If there's no such entity or the _`expression`_ parameter names a set of overloaded functions, the compiler yields an error message.
- 2️⃣  If the _`expression`_ parameter is a call to a function or an overloaded operator function, `decltype(expression)` is the return type of the function. Parentheses around an overloaded operator are ignored.
- 3️⃣  If the _`expression`_ parameter is an [[value categories|rvalue]], `decltype(expression)` is the type of _`expression`_. If the _`expression`_ parameter is an [[value categories|lvalue]], `decltype(expression)` is an [[Reference Type|lvalue reference]] to the type of _`expression`_.


# 🗃Example
Suppose you have the following:
```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```
Then we can summarize:
| Statement           | Type            | Notes                                                        |
| ------------------- | --------------- | ------------------------------------------------------------ |
| `decltype(fx());`   | `const int&&`   | An [rvalue reference](https://learn.microsoft.com/en-us/cpp/cpp/rvalue-reference-declarator-amp-amp?view=msvc-170) to a **`const int`**. |
| `decltype(var);`    | **`int`**       | The type of variable `var`.                                  |
| `decltype(a->x);`   | **`double`**    | The type of the member access.                               |
| `decltype((a->x));` | `const double&` | ⭐The inner parentheses cause the statement to be evaluated as an expression instead of a member access. And because `a` is declared as a **`const`** pointer, the type is a reference to **`const double`**. |


# 🧬Related Elements
##  `decltype` and `auto`
https://learn.microsoft.com/en-us/cpp/cpp/decltype-cpp?view=msvc-170#decltype-and-auto

## `decltype` and forwarding functions
[[forwarding reference]]
https://learn.microsoft.com/en-us/cpp/cpp/decltype-cpp?view=msvc-170#decltype-and-forwarding-functions-c11