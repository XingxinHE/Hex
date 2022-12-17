---
aliases: []
tags:
  - cpp
  - ProgrammingLanguage
---
# 📝Summary
**🎯Intent**
What does this course for?

**✏The Course in 3 Sentences**
1...
2...
3...

**🧠Impression**
I feel ...


| 2019                                 | 2020                 | 2021                       | 2022                                 |
| ------------------------------------ | -------------------- | -------------------------- | ------------------------------------ |
| const as a promise                   | pointer and memory   | pointers                   | API Design                           |
| Function and class template          | templates            | const and constexpr        | Smart Pointer                        |
| lambda                               | ✅lambda               | templates                  | Value Categories With Standard Tools |
| move semantics                       | move semantics       | ✅lambdas                    | RAII                                 |
| Object-oriented programming          | Class Layout         | move semantics             | testing                              |
| RAII & Rule of Zero                  | concurrency          | object-oriented programing | value semantics                      |
| Test Driven Development              | unit test            | Designing Classes          | move semantics                       |
| Type Erasure                         | algebraic data types | concurrency                | templates                            |
| Understanding value categories       | design patterns      | casting                    | debugging                            |
| virtual dispatch and its alternative | the abstract machine | debugging techniques       |                                      |
| smart pointer                        | smart pointers       | special member functions   |                                      |
| inplace construction                 | structure of program | smart pointer and RAII     |                                      |
| exception handling and safety        | exceptions           | undefined behavior         |                                      |
|                                      |                      | overload resolution        |                                      |
|                                      |                      | compiling and linking      |                                      |
|                                      |                      | class STL                  |                                      |
|                                      |                      | algorithmic complexity     |                                      |
|                                      |                      |                            |                                      |

# 📺Lectures
### `const` as a Promise
📝Basic Info
- 🗣Presenter: Dan Saks
- 📆Year: #2019
- 🔖Topic: [[const]]
Outline
- Uses of `const`
- Benefit using `const` and `constexpr`
- Be proactive
- `const` review
- `const` & initialization
- constant expression
- CV-qualifiers
- The Structure of [[declaration]]
- Declaration Specifiers
- Declarator Operator
- Parentheses in Declarators
- type specifier vs Non-type specifier
- `const` is a type-specifier

### Compiling and Linking
📝Basic Info
- 🗣Presenter: Ben Saks
- 📆Year: #2021
- 🔖Topic:
Outline

### Lambdas by Josuttis
📝Basic Info
- 🗣Presenter: Nicolai M. Josuttis
- 📆Year: #2021
- 🔖Topic: [[lambda expression]]
Outline:
- Why should we use lambda? Answer: [[lambda expression#CPP#🗺Big Picture]]
- understand the syntax at [[lambda expression#CPP#🧪Composition]]
- some scenario using lambda at [[lambda expression#CPP#🤳Applicability]]
- understand the "本质" of lambda expression at [[lambda expression#CPP#🔎Implementation]]
- wonder capture by "const-reference"? See [[lambda expression#CPP#Capture clause#⌨Sample Code]]
- the application of `mutable` lambda in [[lambda expression#CPP#🧪Composition#mutable specification]]
#TODO :
- read the microsoft doc: Function Objects vs. Lambdas

### Lambda Expressions by Geller & Sermersheim
📝Basic Info
- 🗣Presenter: # Barbara Geller & Ansel Sermersheim
- 📆Year: 2020
- 🔖Topic: [[lambda expression]]
Outline:
- the [[lambda expression#⌚History]] of lambda
- the [[lambda expression#✒Terminology]] of lambda
- similar item is [[function pointer]]
- [[function call operator]] is a subset of [[Operator overloading]]
- review the similar items at here [[Function Object#🧬Related Elements#Terminology across similar disciplines]]⭐
- understand function object and lambda are closely related [[Function Object#🧬Related Elements#function object & lambda expression]]
- capture clause with `this` pointer at [[lambda expression#CPP#🧪Composition#Capture clause#🧬Related Elements#📌capture clause with this keyword this pointer]]

### Pointer and Memory
📝Basic Info
- 🗣Presenter: Ben Saks
- 📆Year: 2019
- 🔖Topic: [[pointer]], [[memory]]
Outline:
- 1️⃣Pointers to Objects
	- [[null pointer]], [[dangling pointer]], 
- 2️⃣Arrays vs. Pointer Arithmetic
	- [[array#🧬Related Elements#array vs. pointer]], [[pointer#💫Operation#pointer arithmetic]]
- 3️⃣`size_t` and `ptrdiff_t`
	- [[size_t]], [[ptrdiff_t]], [[ssize]]
- 4️⃣Placing `const` in Pointer Declaration
	- [[const#🧬Related Elements#const and pointer]]
- 5️⃣Pointer Type Conversion
	- [[casting operators]], [[Type conversions|type casting]], [[pointer#💫Operation#pointer type conversion]]
- 6️⃣References
	- [[Reference Type#🗻Foundation#⛰Understand why we need reference in C++]], [[Reference Type#🌓Complement#🌗reference type data type vs. pointer type data type]]


# 💻Assignment



# 📖Reading



# ℹSyllabus
- **🎯Course Goal**
- **📖Course Textbook**
- **👩‍🏫👨‍🏫Lecturer**:
- **🔗Link**: [xxx](https://)
- **📺Video**:[xxx](https://)