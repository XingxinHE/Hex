---
aliases: [raw pointer]
---

# 📝Definition
- A pointer is a variable that stores the memory address of an object.

# 🎯Intent
- Pointers are used extensively in both C and C++ for three main purposes:
    - to allocate new objects on the heap
    - to pass functions to other functions
    - to iterate over elements in arrays or other data structures
    
# 🚀Benefit / Pro
- A *pointer* introduces a level of **indirection** to a program. Rather than <u>manipulate an object directly</u>😑, we <u>manipulate a pointer that holds the address of an object</u>😍.

# 🏷(Sub)Categories
- In C++, there are 2 main categories.
    - raw pointer
    - [[Smart Pointer]]
    
# ⌨Sample Code
- ``` c++
  int ival = 1024;
  int* pi;             // pi is a pointer to an object of type int
  &ival;               // evaluates to the address of ival by using `&`
  pi = &ival;          // pass the address of ival to pi
  ```
- sample on different style of C++ raw pointer
    - ``` c++
      int* pi = &ival;
      int *pi = &ival;
      ```
    - I personally favor the second version which seeing that the `*` affects the declarator-id directly.
    - ``` c++
      // pi is a pointer to int
      // pt2 is an int
      int* pi, pi2;
      
      // pi3 is a pointer to int
      // pi4 is a pointer to int
      int* pi3, * pi4;
      ```
    - Use `T *p` rather than ~~`T* p`~~
    
- example on guarding against dereferencing a null pointer ^40c7cc02dd9c4f77
    - ``` c++
      // safe check
      if (pi && *pi!=1024)
      {
          *pi = 1024;
      }
      
      // modern check null pointer
      if (nullptr != pi && *pi!=1024)
      {
          *pi = 1024;
      }
      ```
    
# 🌓Complement
- [[Reference]]

# 🔎Implementation
- 📌nullness of pointer
    - In C++, there are 3 things representing the nullness.
        - integral `0`
        - `NULL`
        - `nullptr` literal
        
    - Use `nullptr` rather than others. Because it kills the ambiguity of overloading function with pointers and integral type.
      
      ``` c++
      // 3 overloading function of f
      void f(int);
      void f(bool);
      void f(void*);
      
      f(0);  //🙁call f(int), not f(void*)
      f(NULL);  //🙁might not compile, but typically calls f(int). Never calls f(void*)
      f(nullptr);  //😊call f(void*) overload
      ```
    
# 🕳Pitfalls
- Pitfall on undefined behavior
    - Description
        - dereference a null C/C++ raw pointer will cause [[Undefined Behavior]] like [[Undefined Behavior#^2a05b7d5f62b6f91|this]]
        
    - Solution
        - Therefore, to [[#^40c7cc02dd9c4f77|guard against dereferencing a null pointer]], we must assure if its address value is zero/null before using...
        
    - Exception
        - But there is no need to check reference since reference must be initialized at the beginning.
        
## 🥼Expert's Advice
- Lippman had words to beginner "Be patient when you are learning pointer. The initial **complexity** of using a pointer comes from its <u>confusing syntax</u>".🤣
