---
aliases: [type-conversion operator, static_cast, dynamic_cast, const_cast, reinterpret_cast]
---
# 📝Definition
There are several casting operators specific to the #cpp language. These operators are intended to remove some of the ambiguity and danger inherent in old style #c language casts. These operators are:
-   [dynamic_cast](https://learn.microsoft.com/en-us/cpp/cpp/dynamic-cast-operator?view=msvc-170) Used for conversion of polymorphic types.
-   [static_cast](https://learn.microsoft.com/en-us/cpp/cpp/static-cast-operator?view=msvc-170) Used for conversion of nonpolymorphic types.
-   [const_cast](https://learn.microsoft.com/en-us/cpp/cpp/const-cast-operator?view=msvc-170) Used to remove the **`const`**, **`volatile`**, and **`__unaligned`** attributes.
-   [reinterpret_cast](https://learn.microsoft.com/en-us/cpp/cpp/reinterpret-cast-operator?view=msvc-170) Used for simple reinterpretation of bits.

> [!Warning] Warning
> Use **`const_cast`** and **`reinterpret_cast`** as a last resort, since these operators present the same dangers as old style casts. However, they are still necessary in order to completely replace old style casts.


> [!note] Common Note
> For all the `type-id` and `expression`, the requirements are:
> - they must be either [[pointer]] or [[Reference Type|lvalue reference]]
> - `type-id` and `expression` have to be the same type

# 📋Prerequisite
Casting is an ugly (and dangerous) operation - use it only when absolutely necessary. When you need a cast, reconsider:
- Is there a way to write the code without the cast?
- Is there a way to redesign that part of program so that the cast is not needed?

___

# dynamic_cast
## 📝Definition
Converts the operand `expression` to an object of type `type-id`.

## ✒Syntax
```cpp
dynamic_cast < type-id > ( expression )
```

___

# static_cast
## 📝Definition
Converts an _expression_ to the type of _type-id,_ based only on the types that are present in the expression.

## ✒Syntax
```cpp
static_cast <type-id> ( expression )
```

## 📋Prerequisite
The name `static_cast` is a deliberately ugly name for an ugly (and dangerous) operation — use it **only when** absolutely necessary.

___

# const_cast
## 📝Definition
Removes the **`const`**, **`volatile`**, and **`__unaligned`** attribute(s) from a class.

## 🧠Intuition
Cast away `const`.

## ✒Syntax
```cpp
const_cast <type-id> (expression)
```

___

# reinterpret_cast
## 📝Definition
Allows any pointer to be converted into any other pointer type. Also allows any integral type to be converted into any pointer type and vice versa.

## 🧠Intuition
`reinterpret_cast` can cast between unrelated types, such as `int` and `double*`.

## ✒Syntax
```cpp
reinterpret_cast < type-id > ( expression )
```

# 🕳Pitfalls
`reinterpret_cast` is not portable.

# 🤳Applicability
The `reinterpret_cast` seems quite ugle so why should it be in the #cpp anyway? The answer lies into 2:
- solving the legacy issue with [[void pointer]] in #c 
-  `reinterpret_cast` is good at directly interpert [[memory|memory address]]! ⭐

**📌classic necessary and proper use of a `reinterpret_cast`**
```cpp
Register *input = reinterpret_cast<Register*>(0xff);
```
We tell the compiler that a certain part of memory (the [[memory|memory address]] `0xff` in [[hexadecimal]]) is to be considered a `Register`. Such code is good at device drivers!
