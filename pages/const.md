# 📝Definition and Classification
- Definition by Bjarne. The value of a `const` object is not known at [[compile-time]]. Its value will be initialized at [[run-time]] and cannot be changed after [[Initialization]].
- Definition by Dan Saks. A `const` object is non-modifiable in terms of:
    - write❌
    - read✅
    
# 🚀Benefit
 Turn potential [[run-time]] error to [[compile-time]] error. Therefore it is good at designing [[interface]].

# ⌨Sample Code
- Example on initialization
  
  ``` c++
  const int number;			//❌ERROR. missing init
  extern const int limit;		//✅OK. This is declare not definition.
  const int level = 42;		//✅OK. Explicitly initialize.
  ```
- Example on the characteristic of `const`
  ``` c++
  const int number = 123;
  
  int n = number;		//✅OK to read
  number = 2 * n + 1; //❌NO to write
  ```
-

# 🌱Related Elements
- 📌Key Difference between [[constexpr]] and `const` in C++
    - `const` => run-time
    - `constexpr` => compile-time
    
# 🧀Applicability
 `const` often is used in passing arguments and returning values by pointers and references.

- Uses for `const`
    - In light of the ((63010392-4a98-433e-a3f2-171ce5f96c26)), the categories are:
    - 1. Symbolic Constants ^a96c8a55f4f5336d
    - 2. Immutable(never changing) data ^c731a392d08fda7
    - 3. prevent modifying a potentially modifiable operand ^bfe43db6f575f35a
- Comparison between `const` and [[constexpr]]
    - for ((630181b2-07c2-41c8-bf6e-1da74f2b8812)), `constexpr` is better in modern C++.
    - for ((630181b6-f3be-46eb-b61f-da9ae23c8662)), `constexpr` is better in Modern C++.
    - for ((630181b8-4ffc-4cb3-bdaa-60d1dcaf020d)), `const` is better.
- `const` and [[Initialization]]
    - C++ insists that you MUST initialize every `const` object.
- [[constexpr|Constant Expression]]
    - Ben Saks claimed that "The dimension in an array object definition must be integer constant expression". He provides the following code.
      
      ``` c++
      void foo(size_t n)
      {
        int x[n];  //❌NO. dim must be constant.
        int y[17];	//✅OK. dim is constant.
      }
      ```
      
      However, I can compile with the code.
    - TODO Clarify the preceding code.
- [[CV-Qualifiers]]


# 🏷(Sub)Categories
There are several stuffs that `const` can play.
- const variable
	- `const int var`
- [[Reference Type|const reference]]
	- `const Widget &w`
- const [[pointer]]
	- `int *const var`
- [[pointer]] to const
	- `const int *var`
- `const` method
	- `void someMethod() const`



# 🌱Related Elements
## const and pointer
**💭Problem Address**
If you recall, there are actually 5 kinds of `const` combination in [[pointer]] [[declaration]].😵 However, they can be grouped into 3.
```cpp
//1
const T *p = ~~;
//2
T const *p = ~~;

//3
T *const p = ~~;

//4
const T *const p = ~~;
//5
T const *const p = ~~;
```
___
**📌Category 1**
```c++
//1
const T *p = ~~;
//2
T const *p = ~~;
```

Although it looks like there are 2 forms, they actually are identical.

> 📝Definition: It means <u>what `p` points to</u> is `const`.

> 💻Code

```c++
T xy;
p = &x;  //  ✅OK. Can modify pointer p itself.
*p = y;  //  ❌ERR. Can't modify what p points to.
```

> 🧠Tips to remember: `const` is on the **<u>left</u>** side `*`.

___
**📌Category 2**

```c++
//3
T *const p = ~~;
```

> 📝Definition: It means `p` itself is `const`.

> 💻Code

```c++
T xy;
p = &x;  //  ❌ERR. Can't modify pointer p itself.
*p = y;  //  ✅OK. Can modify what p points to.
```

> 🧠Tips to remember: `const` is on the **<u>right</u>** side `*`.

___
**📌Category 3**
```c++
//4
const T *const p = ~~;
//5
T const *const p = ~~;
```
Although it looks like there are 2 forms, they actually are identical.

> 📝Definition: It is the combination of the preceding 2:
>
> 			1) <u>what `p` points to</u> is `const`.
> 			1) `p` itself is `const`.

> 💻Code

```c++
T xy;
p = &x;  //  ❌ERR. Can't modify pointer p itself.
*p = y;  //  ❌ERR. Can't modify what p points to.
```

> 🧠Tips to remember: `const` is on **both** the **<u>left</u>** and <u>**right**</u> side `*`.


