---
aliases: [type conversion, type cast, type casting]
---

# πDefinition
A cast doesnβt change its operand and it produces a new value.

# π·(Sub)Categories
- In #cpp , type conversions can be categorized like so.
    - In terms of technical perspective
        - Implicit type conversions
            - [[widening|widening conversion]]
            - [[narrowing|narrowing conversion]]
            - Signed - unsigned conversions
            - Pointer conversions
        - Explicit conversions (cast)
            - Explicit conversion often refers to the term "cast".
            - Done by [[casting operators|type-conversion operator]].
                - [[casting operators|static_cast]]
                - [[casting operators|dynamic_cast]]
                - [[casting operators|const_cast]]
                - [[casting operators|reinterpret_cast]]
    - In terms of [[type safety]]
        - Safe Conversion. a.k.a. the bit of `later type` β₯ `current type`. see [[#^d9ff4d8244e830d0|this]]
        - Unsafe Conversion. a.k.a the bit of `later type` < `current type`. see [[narrowing#^a976e85c5e46de10|this]] and [[#^2e3ae7a58be08eb2|this]]
        
# βLaws
- πType conversion hierarchy in C++
    - TODO  This is by Robert Erics, not sure if it is outdated...
    - | Type           | Hierarchy(most precise on the top) |
      | -------------- | ---------------------------------- |
      | long double    | βββββββββ                          |
      | double         | ββββββββ                           |
      | float          | βββββββ                            |
      | unsigned long  | ββββββ                             |
      | long           | βββββ                              |
      | unsigned int   | ββββ                               |
      | int            | βββ                                |
      | unsigned short | ββ                                 |
      | char           | β                                  |
    
# β¨Sample Code
- Safe Conversionπ
  
  ``` c++
  char c = 'x';
  int i1 = c;
  int i2 = 'x';
  ``` ^d9ff4d8244e830d0
- Unsafe Conversionβ
  
  ``` c++
  int a = 20000;
  char c = a; // βtry to squeeze a large int into a small char
  int b = c;
  ``` ^2e3ae7a58be08eb2
