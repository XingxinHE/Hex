---
aliases: [data type]
---

# 📝Definition
A type is something that defines a set of possible **values** and a set of **operations** for an [[object]].

A data type is a classification identifying the possible **values** for that type and the **operations** which can be done on values of that type.

# 🎯Intent
- Types are good for directly representing ideas in code.
**Representation**: A type “knows” how to represent the data needed in an object.
**Operations**: A type “knows” what operations can be applied to objects.

# 🌓Complement
## Data Type vs. Expression
- Data Type
	- values
		- `12`, `true`, `"cake"`, `3.14`, `nullptr`
	- operations
		- what can be done with the data (compare, assignment, some manipulation)
- Expression
	- data type
		- `int`, [[pointer]], `string`, [[Reference Type|lvalue reference]], [[Reference Type|rvalue reference]]
	- [[value categories]]
		- lvalue, rvalue

# ⛈Characteristics
A data type is characterized by 2 factors:
- value
- operations

# 🏷(Sub)Categories
There are many categories on data type.
## primitive data type
`char`, `int`, `double`
## built-in data type
lists, hash table, `std::complex`
## compound data type
`std::vector, std::iostream`
## [[user-defined]] data type
`enum class`, `class`
## [[Container|abstract data type]]

## [[atomic data type]]

## [[pointer|pointer data type]]

## [[Reference Type|reference data type]]

## [[function pointer|function pointer data type]]


## [[method pointer data type]]



- In programming, a type can normally divide into 2 main categories.
    - [[user-defined]] types. which designed and implemented by user.
        - In C++,
            - `class`
            - `enum`
            
        - In C#,
            - `struct`
            - `class`
            - `interface`
            - `enum`
            - `record`
            
    - built-in types.
        - Built-in type is provided by the programming language. Generally, the built-in type can be divided as
            - [[integral type]]. e.g. for C++, `bool`, `char`, `short`, `int`, `long`, and `long long` and their `unsigned` variants.
            - [[floating point type]]. e.g. for C++, `float`, `double`, and `long double`
            - void
            
        - The following are the built-in type for language I am familiar.
            - In C++, the built-in types are named with [[Naming Convention#^6e89cb96fbb85250|lower case]] and here are the following
                - void
                - short
                - int
                - long
                - float
                - double
                - bool
                - char
                
            - In [[C#]], the built-in types separate into 2 categories.
                - [[Value Type]]
                    - | C# type keyword                                              | .NET type                                                    |
                      | ------------------------------------------------------------ | ------------------------------------------------------------ |
                      | [`bool`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/bool) | [System.Boolean](https://docs.microsoft.com/en-us/dotnet/api/system.boolean) |
                      | [`byte`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.Byte](https://docs.microsoft.com/en-us/dotnet/api/system.byte) |
                      | [`sbyte`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.SByte](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte) |
                      | [`char`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/char) | [System.Char](https://docs.microsoft.com/en-us/dotnet/api/system.char) |
                      | [`decimal`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types) | [System.Decimal](https://docs.microsoft.com/en-us/dotnet/api/system.decimal) |
                      | [`double`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types) | [System.Double](https://docs.microsoft.com/en-us/dotnet/api/system.double) |
                      | [`float`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types) | [System.Single](https://docs.microsoft.com/en-us/dotnet/api/system.single) |
                      | [`int`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.Int32](https://docs.microsoft.com/en-us/dotnet/api/system.int32) |
                      | [`uint`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.UInt32](https://docs.microsoft.com/en-us/dotnet/api/system.uint32) |
                      | [`nint`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.IntPtr](https://docs.microsoft.com/en-us/dotnet/api/system.intptr) |
                      | [`nuint`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.UIntPtr](https://docs.microsoft.com/en-us/dotnet/api/system.uintptr) |
                      | [`long`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.Int64](https://docs.microsoft.com/en-us/dotnet/api/system.int64) |
                      | [`ulong`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.UInt64](https://docs.microsoft.com/en-us/dotnet/api/system.uint64) |
                      | [`short`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.Int16](https://docs.microsoft.com/en-us/dotnet/api/system.int16) |
                      | [`ushort`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) | [System.UInt16](https://docs.microsoft.com/en-us/dotnet/api/system.uint16) |
                    
                - [[Reference Type]]
                    - | C# type keyword                                              | .NET type                                                    |
                      | ------------------------------------------------------------ | ------------------------------------------------------------ |
                      | [`object`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types#the-object-type) | [System.Object](https://docs.microsoft.com/en-us/dotnet/api/system.object) |
                      | [`string`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types#the-string-type) | [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string) |
                      | [`dynamic`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types#the-dynamic-type) | [System.Object](https://docs.microsoft.com/en-us/dotnet/api/system.object) |





