# 🏷(Sub)Categories
- The syntax of `delete` keyword is different in terms of:
- objects
  
  ``` c++
  int *pi;
  pi = new int(1024);
  delete pi;  //delete an object
  ```
- array
  
  ``` c++
  int *pia = new int[24];
  delete [] pia;  //delete an array
  ```


# 🌓Complement
[[new keyword]]

# 🕳Pitfalls
📌`delete` twice a pointer
This is extremely dangerous!
```cpp
int *p = new int{5};
delete p;
//...no use of p here
delete p;  //❌
```
There are 2 problems with the 2nd `delete`:
- it might not be executed correctly due to the [[Heap|free store]] manager may have changed its internal state.
- it might delete other object's data! Since that chunk of memory might be recycled already.