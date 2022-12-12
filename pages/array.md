# 📝Definition
- In mathematics,
    - An array is a "list of lists" with the length of each level of list the same. The size (sometimes called the "shape") of a $d$-dimensional array is then indicated as $\underbrace{m×n×...×p}_{d}$. The most common type of array encountered is the two-dimensional $m×n$ rectangular array having $m$ columns and $n$ rows. If $m=n$, a square array results.
- In general,
	- A [[homogeneous]] [[Tuple|sequence]] of elements, usually numbered, e.g.,  `[0:max)` .
- In #csharp 
    - The language designers wrap the mathematical concept into [[data structure]] [Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/) which supports single-dimensional, multidimensional or jagged.
- In #c and #cpp 
    - we often refer to the data structure which is a fixed-length and single-dimensional. Due to the legacy reason, we have 2 forms of array.
        - C-Style array (👎 not recommend, see the [[#^c15ddc3179fae7b6|reason]])
        - modern C++ `std::array` (👍 recommend.)
# 🚀Benefit / Pros
- For `std::array`,
    - It does not degenerate to a pointer when passed to a function and does know its size.
    
# 🕳Pitfalls / Cons
- For C-Style array, this is the cons ^c15ddc3179fae7b6
    - the size is fixed
    - The array does not explicitly specify the length of an array. Therefore, we often accompany an integer to track the size.
    - does not support insert and remove operation
    - array does not have bound-checking
    
# ⌨Sample Code
- C-Style array code example
    - ``` c++
      // (1)init an array
      int seq_size = 6;
      int elem_seq[seq_size] = {
          1, 2, 3,
          4, 5, 6
      };
      
      // (2)init an array
      int elem_seq[] = {
        1, 2, 3,
        4, 5, 6
      };
      
      // (3)declared but not initialized
      int* elem_seq = new int[3];
      cout << elem_seq[0] << endl;    // 2395876
      cout << elem_seq[1] << endl;    // -197630894
      
      // (4)declared and initialized, not slow in general but a bit slower than (3)
      int* elem_seq = new int[3]();   //👈 the`()`
      cout << elem_seq[0] << endl;    // 0
      cout << elem_seq[1] << endl;    // 0
      ```
    
# 🧬Related Elements
- In C++,
    - 📌an array is also a [[pointer]]
        - ```c++
          //The followings are the same!
          array[2];
          *(array + 2);
          ```
        - If you are a C# programmer, you would say what the heck?? 😨😨 That's because an <u>array is a pointer which records the 1st address of that array</u>. Therefore, they are the same.
        