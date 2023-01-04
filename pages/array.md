# 📝Definition
- In #mathematics  ,
    - An array is a "list of lists" with the length of each level of list the same. The size (sometimes called the "shape") of a $d$-dimensional array is then indicated as $\underbrace{m×n×...×p}_{d}$. The most common type of array encountered is the two-dimensional $m×n$ rectangular array having $m$ columns and $n$ rows. If $m=n$, a square array results.
- In general,
	- A [[homogeneous]] [[tuple|sequence]] of elements, usually numbered, e.g.,  `[0:max)` .
- In #csharp 
    - The language designers wrap the mathematical concept into [[data structure]] [Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/) which supports single-dimensional, multidimensional or jagged.
- In #c and #cpp 
    - we often refer to the data structure which is a fixed-length and single-dimensional. Due to the legacy reason, we have 2 forms of array.
        - C-Style array (👎 not recommend, see the [[array#🩹Cons#🤕Cons of C-Style array|reason]])
        - modern C++ `std::array` (👍 recommend.)
# 🚀Benefit / Pros
- For `std::array`,
    - It does not degenerate to a pointer when passed to a function and does know its size.
    
# 🩹Cons
## 🤕Cons of C-Style array
The following:
- the size is fixed
- The array does not explicitly specify the length of an array. Therefore, we often accompany an integer to track the size.
- does not support insert and remove operation
- array does not have bound-checking

# 🗃Example
## 📂C-Style array code example
```cpp
// (1)1️⃣init an array
int seq_size = 6;
int elem_seq[seq_size] = {
    1, 2, 3,
    4, 5, 6
};

// (2)2️⃣init an array
int elem_seq[] = {
  1, 2, 3,
  4, 5, 6
};

// (3)3️⃣declared but not initialized
int* elem_seq = new int[3];
cout << elem_seq[0] << endl;    // 2395876
cout << elem_seq[1] << endl;    // -197630894

// (4)4️⃣declared and initialized, not slow in general but a bit slower than (3)
int* elem_seq = new int[3]();   //👈 the`()`
cout << elem_seq[0] << endl;    // 0
cout << elem_seq[1] << endl;    // 0
```


# 🌱Related Elements
## array vs. pointer
❓Question: is an array also a pointer in #cpp  ?
```cpp
//access is similar🤔
array[2];
*(array + 2);

//a pointer can hold the start of array🤔
int x[10];
int *p;
p = x;    //😵 does it mean pointer = array?
```
🤔Thoughts:
- When I first learned array in C++, I had that confusion that "is array type equal to pointer type"? Because looking from the behavior, they are pretty much similar.
- If you are a C# programmer, you would say what the heck?? 😨😨 That's because an <u>array is a pointer which records the 1st address of that array</u>. 
📃Answer:
The answer to this question is NO❌. It works because the array "<u>decay</u>" into a pointer. We can have another proof by zooming into a memory level.
✏Proof - array is not pointer
```cpp
char x[32];
char *p;

cout << sizeof(x); // 32 = 32 * sizeof(char)
cout << sizeof(p); // maybe one of 2/4/8 depending on the hardware

cout << alignof(x); //   1 = alignof(char)
cout << alignof(p); //   2/4/8 = alignof(char *) depending on the hardware
```
💭Array [[parameter]] is Pointer:
Unfortunately, this is true and also **confusing** in #FunctionDesign  . The followings are all the same:
```cpp
void foo(int *x);
void foo(int x[]);
void foo(int x[10]);
```

