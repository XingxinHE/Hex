---
aliases: [pass-by-const-reference, pass-by-reference-to-const]
---

# 📝Definition
- Pass by reference typically means pass the argument by reference.
- In C++,
    - we use [[&]] in a method signature to indicate pass by reference.
    - Particularly, there is a sub-domain which has different name but is the same thing.
        - pass-by-const-reference
        - pass-by-reference-to-const
        
- In C#,
    - we use `ref` keyword to indicate pass [[Value Type]] variables by reference
    - for [[Reference Type]] variables, it is pass by reference by nature in C#.
    
# 🚀Benefit
- In C++,
    - pass-by-reference on [[user-defined]] class object is more efficient.
    
# ⌨Sample Code
- example of "pass-by-const-reference" and "pass-reference-to-const"
    - ```c++
      //pass-by-const-reference
      void print(const vector<int> &v)
      ```
    - ``` c++
      //pass-by-reference-to-const
      void print(vector<int> const &v);
      ```
    
# 🌓Complement
- [[pass-by-value]]

# 🥼Expert's Advice
- Lippman address "I recommend *not* passing built-in types by reference. The reference mechanism is primarily intended to support the passing of class objects as parameters to functions."

# 🕳Pitfalls
- In C++,
    - 📌 `&` only modify the variable it applies to
        - ``` c++
          // ❌ Although the values is passed by reference.
          // The `values` does not change since it takes out the
          // elem as value, and increment the elem
          void func1(vector<int> &values)
          {
                  for(int elem : values)  //👈there is no `&` here. So no modification on `values`
                  {
                          elem++;
                  }
          }
          
          // ✅ It does change! Since it is sliced with `int &elem`
          // to indicate we slice the reference out of `values`
          void func2(vector<int> &values)
          {
                  for(int &elem : values)
                  {
                          elem++;
                  }
          }
          
          // ✅ It does change! Since `values` is passed by reference,
          // and we are modifying the `values` itself
          void func3(vector<int> &values)
          {
                  for(int i = 0; i < values.size(); i++)
                  {
                          values[i]++;  //👈because we refer to `values` itself
                  }
          }
          ```
        
# 🙋‍♂️Related Elements
- 📌⭐Our rule of thumb of choosing "pass-by-value", "pass-by-reference", "pass-by-const-reference" in C++ ^75db37bf4ac72c6b
    - Use pass-by-value to pass very small objects. e.g. 1~2 `int` or 1~2 `double`
    - Use pass-by-const-reference to pass large objects that you don’t need to modify.
    - Return a result rather than modifying an object through a reference argument.
        - ``` c++
          int incr1(int a) { return a+1; } // return the new value as the result
          void incr2(int& a) { ++a; } // modify object passed as reference
          int x = 7;
          
          x = incr1(x); // 😉pretty obvious
          incr2(x); //😶pretty obscure
          ```
        
    - Use pass-by-reference only when you have to. e.g. modify few objects in 1 function
        - ``` c++
          void larger(vector<int>& v1, vector<int>& v2)
            // make each element in v1 the larger of the corresponding
            // elements in v1 and v2;
            // similarly, make each element of v2 the smaller
          {
            if (v1.size()!=v2.size()) error("larger(): different sizes");
            for (int i=0; i<v1.size(); ++i)
            if (v1[i]<v2[i])
            swap(v1[i],v2[i]);
          }
          ```
        - It is usually **best to avoid functions that modify several objects**. In theory, there are always alternatives, such as returning a class object holding several values.
        