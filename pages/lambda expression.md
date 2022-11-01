# #cpp 
[Lambda expressions in C++ | Microsoft Learn](https://learn.microsoft.com/en-us/cpp/cpp/lambda-expressions-in-cpp?view=msvc-170)
## 📝Definition
- The name is the essence of this topic.


## 🧠Intuition
```c++
std::vector<int> v {4, 1, 3, 5, 2, 3, 1, 7};
int num_geq5 = std::count_if(v.cbegin(), v.cend(), [](int a)
    {
        return (a >= 5);
    });
```


## 📈Diagram
![[cpp_lambda_expression.png]]


## 🧪Composition
- capture clause (Also known as the lambda-introducer in the C++ specification.)
- parameter list ==Optional==. (Also known as the lambda declarator)
- mutable specification ==Optional==.
- exception-specification ==Optional==.
- trailing-return-type ==Optional==.
- lambda body.

### Capture clause
#### 📝Definition
A lambda begins with the capture clause. 

#### 🏷(Sub)Categories
Capture clause specifies which variables are captured, and whether the capture is by value or by reference.
- `[ ]`, indicates that the body of the lambda expression accesses no variables in the enclosing scope.
- `[&]` means all variables that you refer to are captured by reference
- `[=]` means they're captured by value.
> [!warning]
> >Only variables that are mentioned in the lambda body are captured when a capture-default is used.

#### ⌨Sample Code
-   rules using `&`, `=` in capture clause
    -   ```cpp
        	  struct S { void f(int i); };
        	  - void S::f(int i)
        	  {
        	  [&, i]{};      // ✅OK
        	  [&, &i]{};     // ❌ERROR: i preceded by & when & is the default
        	  [=, this]{};   // ❌ERROR: this when = is the default
        	  [=, *this]{ }; // ✅OK: captures this by value. See below.
        	  [i, i]{};      // ❌ERROR: i repeated
        	  }
        ```
        
-   equivalent capture clause
    -   suppose there are variable `total` and `factor`, the following are the same.
    -   ```cpp
        	  [&total, factor]
        	  [factor, &total]
        	  [&, factor]
        	  [=, &total]
        ```




# #csharp 
[Lambda expressions - C# reference | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions)


