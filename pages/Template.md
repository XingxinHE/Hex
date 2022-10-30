- Explicit Template Initialization
    - Treat it as non-inline entities.
    - Situation 1
        - ``` c++
          //a.h header file
          
          //primary class template
          template <typename T>
          class foo;
          
          //explicit specialization
          template<>
          class foo<int>
          {
          public:
          	//member declaration
              void f(int n);
          }
          ```
        - ``` c++
          //a.cpp source file
          
          //member definition for ...
          //... explicit specialization
          void foo<int>::f(int n)
          {
            //
          }
          ```
        
    - Situation 2
        - ``` c++
          //a.h header file
          
          //primary class template
          template <typename T>
          class foo
          {
          public:
          	//member declaration
              void f(T n);
          }
          
          //explicitly-specialized declaration
          template<>
          void foo<int>::f(int n);
          ```
        - ``` c++
          //a.cpp source file
          
          //member definition for ...
          //... explicit specialization
          template <>
          void foo<int>::f(int n)
          {
            //
          }
          ```
        
- Explicit Template Instantiation
    - Another feature of "what goes where".
    - You declare it in a header file with `extern`.
    - You define it in a source file, **but don't provide a body**! Since the body comes from the earlier template definition.
    - ``` c++
      //a.h
      
      //function template definition
      template <typename T>
      void swap(T &x, T &y)
      {
        T temp(std::move(x));
        x = std::move(y);
        y = std::move(temp);
      }
      
      //explicit function instantiantion declaration
      extern template
      void swap<int> (int &x, int &y);
      ```
    - ``` c++
      //a.cpp
      
      //explicit function
      //instantiation definition
      template
      void swap<int>(int &x, int &y);
      ```
    
- A function template isn't a function.
    - it's a recipe for generating functions.
    
- A class template isn;t a class
    - it's a recipe for generating class.
    