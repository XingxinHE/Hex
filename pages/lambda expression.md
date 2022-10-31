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


# #csharp 
[Lambda expressions - C# reference | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions)