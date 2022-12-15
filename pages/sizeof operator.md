# 📝Definition
Definition 1 - Queries size of the object or type.
Definition 2 - Yields the size of its operand with respect to the size of type **`char`**.

> [!question] Why respect to `char`?
> Typically, a `char` is stored in one [[byte|byte]] and therefore `sizeof(char)` is treated as the 1 unit of `sizeof` operator.

# 🕳Pitfalls
📌pitfall 1
The size of atype is ==not== guaranteed to be the same on every implementation of C++. 
`sizeof(int)`
- `=4` on a laptop or desktop machine
- `=2` on embedded system processors
- `=8` on high-performance architecture

📌pitfall 2
`sizeof` is not counting the elements! It can proved simply.
```cpp
vector<int> v(1000);
cout << sizeof(v);

//24
```

# ⌨Sample Code
📌simple code
```cpp
char A = 'A';
int day = 28;
int *pDay = &day;

cout << "the size of char is " << sizeof(char) << ' ' << sizeof(ch) << '\n';
cout << "the size of int is " << sizeof(int) << ' ' << sizeof(i) << '\n';
cout << "the size of int* is " << sizeof(int*) << ' ' << sizeof(p) << '\n';

//the size of char is 1 1
//the size of int is 4 4
//the size of int* is 8 8
```


📌simple code
```cpp
#include <iostream>
struct Empty {};
struct Base { int a; };
struct Derived : Base { int b; };
struct Bit { unsigned bit: 1; };
struct CharChar      { char c; char c2; };
struct CharCharInt   { char c; char c2; int i; };
struct IntCharChar   { int i;  char c;  char c2; };
struct CharIntChar   { char c; int i;   char c2; };
struct CharShortChar { char c; short s; char c2; };

int main()
{
    Empty e;
    Derived d;
    Base& b = d;
    [[maybe_unused]] Bit bit;
    int a[10];
    std::cout
      << "1) sizeof empty class:              " << sizeof e         << '\n'
      << "2) sizeof pointer:                  " << sizeof &e        << '\n'
//    << "3) sizeof function:                 " << sizeof(void())   << '\n' // error
//    << "4) sizeof incomplete type:          " << sizeof(int[])    << '\n' // error
//    << "5) sizeof bit field:                " << sizeof bit.bit   << '\n' // error
      << "6) sizeof(Bit) class:               " << sizeof(Bit)      << '\n'
      << "7) sizeof(int[10]) array of 10 int: " << sizeof(int[10])  << '\n'
      << "8) sizeof a        array of 10 int: " << sizeof a         << '\n'
      << "9) length of array of 10 int:       " << ((sizeof a) / (sizeof *a))   << '\n'
      << "A) length of array of 10 int (2):   " << ((sizeof a) / (sizeof a[0])) << '\n'
      << "B) sizeof the Derived class:        " << sizeof d         << '\n'
      << "C) sizeof the Derived through Base: " << sizeof b         << '\n'
      << "D) sizeof(unsigned)                 " << sizeof(unsigned) << '\n'
      << "E) sizeof(int)                      " << sizeof(int)      << '\n'
      << "F) sizeof(short)                    " << sizeof(short)    << '\n'
      << "G) sizeof(char)                     " << sizeof(char)     << '\n'
      << "H) sizeof(CharChar)                 " << sizeof(CharChar) << '\n'
      << "I) sizeof(CharCharInt)              " << sizeof(CharCharInt) << '\n'
      << "J) sizeof(IntCharChar)              " << sizeof(IntCharChar) << '\n'
      << "K) sizeof(CharIntChar)              " << sizeof(CharIntChar) << '\n'
      << "L) sizeof(CharShortChar)            " << sizeof(CharShortChar) << '\n';
}

// 1) sizeof empty class:              1
// 2) sizeof pointer:                  8
// 6) sizeof(Bit) class:               4
// 7) sizeof(int[10]) array of 10 int: 40
// 8) sizeof a        array of 10 int: 40
// 9) length of array of 10 int:       10
// A) length of array of 10 int (2):   10
// B) sizeof the Derived class:        8
// C) sizeof the Derived through Base: 4
// D) sizeof(unsigned)                 4
// E) sizeof(int)                      4
// F) sizeof(short)                    2
// G) sizeof(char)                     1
// H) sizeof(CharChar)                 2
// I) sizeof(CharCharInt)              8
// J) sizeof(IntCharChar)              8
// K) sizeof(CharIntChar)              12
// L) sizeof(CharShortChar)            6
```
