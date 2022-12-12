---
aliases: [reference, reference-type, reference data type, lvalue reference, rvalue reference, const reference]
---

# 📖Terminology
"reference" - #c and #cpp 
"reference data type" - #cpp 
"reference type" - #csharp 
"lvalue reference" - #cpp 
"rvalue reference" - #cpp 
"const reference" - #cpp 

# 📝Definition
In #cpp , a reference, like a [[pointer]], stores the [[memory|address]] of an object that is located elsewhere in memory. Unlike a pointer, a reference after it is initialized cannot be made to refer to a different object or set to null. 

In #c , reference is just a concept. It uses [[pointer]] to manifest the ideal of [[pass-by-reference]].

In #csharp , variables of reference types store references to their data (objects). With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.

___
📌rvalue reference
First of all, it is a [[type|data type]]. It can be on the left side of an expression.
It is a feature in #cpp11 which extends the notion of [[value categories|rvalue]]s by letting you bind an rvalue(category) to an rvalue reference.
It prolongs the lifetime of the rvalue as if it was an [[value categories|lvalue]].

# 🧠Intuition
In #cpp 
(1) a value describing the location of a typed value in memory;
(2) a variable holding such a value.


# 🌓Complement
## reference [[type|data type]] vs. [[pointer]] [[type|data type]]
Reference in #cpp  is not a concept while it is actually a data type. The ==key== evidence is that the C++ standard does not force [[Compiler]] to implement reference using pointers.



## Reference Type vs. [[Value Type]]
This is a comparison in #csharp .

# 🏷(Sub)Categories
There are ==3== kinds of references:
- lvalue reference. It refers to a named variable
- rvalue reference. It refers to a [temporary object](https://learn.microsoft.com/en-us/cpp/cpp/temporary-objects?view=msvc-170). 
- const reference
- [[forwarding reference]]

|                  | modification                                      | observation                                    |
| ---------------- | ------------------------------------------------- | ---------------------------------------------- |
| lvalue reference | called method or function can modify the data✅    | caller will observe any modification made✅     |
| const reference  | called method or function cannot modify the data❌ | \                                              |
| rvalue reference | called method or function can modify the data✅    | caller will not observe any modification made❌ |


# ✒Notation
## Symbol
In #cpp, the symbol related to reference is [[&]].
- the `&` operator signifies an [[Reference Type|lvalue reference]] 
- the `&&` operator signifies
	- either an [[Reference Type|rvalue reference]], 
	- or a universal reference (either rvalue or lvalue) depending on the context.

## [[Declaration]] syntax
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

# 🗃Example
📌rvalue reference example 1
One example to crack all the confusion!
```cpp
int && func()
{
	return 42;  //returns an rvalue
}

int main()
{
	int && foo = func();  //Q1: what is the value category of `foo`?
	                      //Q2: what is the data type of `foo`?
	int var = foo + 3;    //Q3: is this valid? If so, what is `var`?
	foo = 47;             //Q4: does it compile?
}
```
The answer is the following:
- Q1: lvalue. Because it has a name.
- Q2: rvalue reference. Because it is declared as rvalue reference and it can be bound to `func()` which returns an rvalue.
- Q3: It is valid.
- Q4: It is valid as well since it is an lvalue.

📌rvalue reference example 2
```cpp
int & func()
{
	return 42;    //ERROR❌
}
```
The return type here is specifying an ==lvalue reference==. However, the return expression is an ==rvalue==.

