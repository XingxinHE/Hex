# 😲Intuitive Explanation
- The `extern` means the following is just declaration, please ignore the parameter name. It does not have any relationships with others.

# ⌨Sample Code
- example on how `extern` used in header files
    - compile-error❌
      ``` c++
      const int seq_cnt = 6;
      const vector<int>* (*seq_array[seq_cnt])(int);  //❌ERROR
      //It is not right... 
      //Since the `seq_cnt` as 6 will be passed in the function declaration.
      //While the declaration is merely declaration.
      ```
    - `extern` can help✅
      
      ``` c++
      const int seq_cnt = 6;
      extern const vector<int>* (*seq_array[seq_cnt])(int);
      ```
    