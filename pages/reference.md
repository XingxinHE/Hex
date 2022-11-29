# 📝Definition
In #cpp , a reference, like a [[pointer]], stores the [[memory|address]] of an object that is located elsewhere in memory. Unlike a pointer, a reference after it is initialized cannot be made to refer to a different object or set to null. 
# 🏷(Sub)Categories
There are ==2== kinds of references:
- [[lvalue and rvalue|lvalue reference]]. It refers to a named variable
- [[lvalue and rvalue|rvalue reference]]. It refers to a [temporary object](https://learn.microsoft.com/en-us/cpp/cpp/temporary-objects?view=msvc-170). 
# ✒Notation
**📌Symbol**
In #cpp, the symbol related to reference is [[&]].
- the `&` operator signifies an [[lvalue and rvalue|lvalue reference]] 
- the `&&` operator signifies
	- either an [[lvalue and rvalue|rvalue reference]], 
	- or a universal reference (either rvalue or lvalue) depending on the context.

**📌[[Declaration]] syntax**
$$
\underbrace{[\text{storage-class-specifiers}]\space [\text{cv-qualifiers}]\space \text{type-specifiers}}_{\text{declaration specifiers}}\quad\underbrace{[\&\text{ or }\&\&]\space[\text{cv-qualifiers}]\space\text{identifier}}_{\text{declarator}}=[\text{expression}]
$$
References are declared using the following sequence:
1. The declaration specifiers:
   - An optional [[storage class specifier]].
   - Optional **`const`** and/or **`volatile`** qualifiers. ([[CV-Qualifiers]])
   - The type specifier: the name of a type.
1. The declarator:
   - The **&** operator or **&&** operator.
   - Optional **`const`** and/or **`volatile`** qualifers.
   - The identifier.
1. An optional initializer.

