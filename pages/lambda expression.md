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



> [!NOTE] Note
> Variables can be only appear in "capture clause" and "parameter list".



### Capture clause
#### 📝Definition
A lambda begins with the capture clause. 
#### 🎯Intent
Introduct objects outside of lambda and use them!
#### 🏷(Sub)Categories
Capture clause specifies which variables are captured, and whether the capture is by value or by reference.
- `[ ]`, indicates that the body of the lambda expression accesses no variables in the enclosing scope.
- `[&]` means all variables that you refer to are captured by reference
- `[=]` means they're captured by value.
> [!warning]
> >Only variables that are mentioned in the lambda body are captured when a capture-default is used.

#### 🕳Pitfalls / Cons
`[&]` and `[=]` play an important role in [[Asynchronous Programming]].
- Reference captures introduce a lifetime dependency
- Value captures have no lifetime dependencies.

#### ⌨Sample Code
- rules using `&`, `=`  in capture clause  
	-  
	  ``` cpp
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
- equivalent capture clause  
	- suppose there are variable `total` and `factor`,  the following are the same.  
	-  
	  ``` cpp
	  	  [&total, factor]
	  	  [factor, &total]
	  	  [&, factor]
	  	  [=, &total]
	  ```
- introduce and initialize new variables in the capture clause  
	-  
	  ``` cpp
	  	  //c++14 feature
	  	  pNums = make_unique<vector<int>>(nums);
	  	  //...
	  	        auto a = [ptr = move(pNums)]()
	  	          {
	  	             // use ptr
	  	          };
	  ```


### parameter list

#### 📝Definition
A parameter list (_lambda declarator_ in the Standard syntax) is optional and in most aspects resembles the parameter list for a function.

#### 🧠Intuition
If the parameter list is empty, the lambda expression is jutst like a function accept arguments.

#### ⌨Sample Code
- basic parameter list  
	-  
	  ``` cpp
	  	  auto y = [] (int first, int second)
	  	  {
	  	      return first + second;
	  	  };
	  ```
- generic parameter list  
	-  
	  ``` cpp
	  	  auto y = [] (auto first, auto second)
	  	  {
	  	      return first + second;
	  	  };
	  ```



### mutable specification

#### 📝Definition
A keyword `mutable` followed after parameter list.

#### 🎯Intent
The **`mutable`** specification enables the body of a lambda expression to modify variables that are captured by value.
> [!NOTE] Note
> Typically, a lambda's function call operator is const-by-value, but use of the **`mutable`** keyword cancels this out. It doesn't produce mutable data members.



### exception-specification
#### 📝Definition
Use the **`noexcept`** exception specification to indicate that the lambda expression doesn't throw any exceptions.
> [!WARNING] Warning
> As with ordinary functions, the Microsoft C++ compiler generates warning [C4297](https://learn.microsoft.com/en-us/cpp/error-messages/compiler-warnings/compiler-warning-level-1-c4297?view=msvc-170) if a lambda expression declares the **`noexcept`** exception specification and the lambda body throws an exception


#### ⌨Sample Code
- `noexcept` in lambda expression  
	-  
	  ``` cpp
	  	  // compile with: /W4 /EHsc
	  	  int main() // C4297 expected
	  	  {
	  	     []() noexcept { throw 5; }();
	  	  }
	  ```



### trailing-return-type
#### 📝Definition
It is just an explicit way telling the compiler what is the `return` type by using `->`.

#### 🎯Intent
Increase the probability of success in [[Type Deduction]].

#### ⌨Sample Code
- trailing-return-type is optional  
	-  
	  ``` cpp
	  	  std::vector<int> nums{1,2,3,4,5};
	  	  auto isAnyLower3 = std::any_of(nums.cbegin(), nums.cend(),
	  	                     [](int num)
	  	                     {
	  	  					  return i < 5;
	  	                     });
	  ```
	-  
	  ``` cpp
	  	  std::vector<int> nums{1,2,3,4,5};
	  	  auto isAnyLower3 = std::any_of(nums.cbegin(), nums.cend(),
	  	                     [](int num)->bool  //👈trailing return type
	  	                     {
	  	  					  return i < 5;
	  	                     });
	  ```
- trailing-return-type helps type deduction  
	-  
	  ``` cpp
	  	  auto x1 = [](int i){ return i; }; // ✅OK: return type is int
	  	  auto x2 = []{ return{ 1, 2 }; };  // ❌ERROR: return type is void, deducing
	  	                                    // return type from braced-init-list isn't valid
	  	  auto x2 = [] ()->std::initializer<int> { return{ 1, 2 }; }; //✅OK: explicitly state the type
	  ```




### lambda body⭐
#### 📝Definition
The lambda body of a lambda expression is a compound statement. The body of a lambda expression can access these kinds of variables:
-   Captured variables from [[lambda expression#Capture clause|capture clause]].
-   Parameters defined in [[lambda expression#parameter list|parameter list]].
-   Locally declared variables.
-   Class data members, when declared inside a class and **`this`** is captured.
-   Any variable that has static storage duration—for example, global variables.

#### ⌨Sample Code
- interesting lambda expression example  
	-  
	  ``` cpp
	  	  int m = 0;
	  	  int n = 0;
	  	  [&, n] (int a) mutable { m = ++n + a; }(4);
	  	  cout << m << endl << n << endl;
	  ```
	- 1️⃣ `mutable` allows  `n`  to be modified within the lambda.  
	- 2️⃣ `n` is capture by value and therefore in the end is `0` (even though is incremented).  
	- 3️⃣ This is a "`void`" lambda since no `return`. So what is the input?! The `4`!! You can see the chunk `[&, n] (int a) mutable { m = ++n + a; }` as a function...  



## 🏷(Sub)Categories
There is something called constexpr lambda expressions using [[constexpr]].

### `constexpr` lambda expressions
#### 📝Definition
The initialization of each captured or introduced data member is allowed within a constant expression.
> [!INFO] C++ Version
> `constexpr` lambda expression is #cpp17 feature.

#### ⌨Sample Code
- simple example  
	-  
	  ``` cpp
	  	  int y = 32;
	  	  auto answer = [y]() constexpr
	  	      {
	  	          int x = 10;
	  	          return y + x;
	  	      };
	  	  
	  	  constexpr int Increment(int n)
	  	  {
	  	    return [n] { return n + 1; }();
	  	  }
	  ```
- implicitly deduce as `constexpr` if its result satisfies the requirements of a `constexpr` function  
	-  
	  ``` cpp
	  	  auto answer = [](int n)
	  	  {
	  	    return 32 + n;
	  	  };
	  	  
	  	  constexpr int response = answer(10);
	  ```
- complicate example  
	-  
	  ``` cpp
	  	  auto Increment = [](int n)
	  	  {
	  	    return n + 1;
	  	  };
	  	  
	  	  constexpr int(*inc)(int) = Increment;
	  ```
	- If a lambda is implicitly or explicitly ** `constexpr` **, conversion to a function pointer produces a ** `constexpr` ** function  



# #csharp 
[Lambda expressions - C# reference | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions)


