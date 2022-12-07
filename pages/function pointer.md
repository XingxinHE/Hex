---
aliases: [pointer to function, subroutine pointer, procedure pointer]
---
# 📝Definition
Function pointer is a data type whose value points to particular function. The [[Signature]] of function must match the declaration of the function pointer.

> [!important] Difference with [[pointer]]
> Unlike pointer, a function pointer **does not points to data**. Therefore, a function pointer cannot be [[dereference operator|dereference]].



# 🎯Intent
📌 [[callback function]]
```cpp
#include <cstdlib>
#include <iostream>

void Hello(int amount)
{
    cout << "Hello World! " << amount << endl;;
}

int main()
{
    void (*myProcess)(int);  // 👈declaration of the function pointer

	myProcess = Hello;
    myProcess(3);           // 👈calls `void Hello(int amount)``
    
    myProcess = std::exit;
    myProcess(42);           // 👈calls std::exit
}
```

📌an argument to another function