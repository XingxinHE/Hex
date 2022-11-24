---
aliases: [this pointer]
---

# 📝Definition
- In #cpp , the **`this`** pointer is a [[pointer]] accessible only within the nonstatic member functions of a **`class`**, **`struct`**, or **`union`** type. It points to the object for which the member function is called. Static member functions don't have a **`this`** pointer.
- In #csharp , the `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.


# 🧠Intuition
`this` refers to the internal state of a [[class]].

# 🎯Intent
Since C# and C++ are similar, their intents are as well.
📌intent 1 - referring to members of the class
```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are 
   (*this).month = mn;    // equivalent.
}

Point(int x, int y)
{
   this->x = x;
   this->y = y;
}
```

> [!warning] Warning
> In the industry, we don't allow the name of data member is the same as the argument! This is just an example. I would not recommend using it.


```csharp
public class Employee
{
    private string name;

    public Employee(string name)
    {
        //👇
        this.name = name;
    }
}
```

📌intent 2 - return the current object from a member function
```cpp
return *this;
```

📌intent 3 - used to guard against self-reference:
```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

📌intent 4 - pass an object as a parameter to other methods
```csharp
CalcTax(this);
```

📌intent 5 - to declare [[indexer|indexers]]
```csharp
public int this[int param]
{
    get { return array[param]; }
    set { array[param] = value; }
}
```

# ⌨Sample Code
📌example in #cpp 
```cpp
#include <iostream>
#include <string.h>
using namespace std;

class Buf
{
public:
    Buf(const char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( const Buf & );
    void Display() { cout << buffer << endl; }
private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf(const char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator
    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( const Buf &otherbuf )
{
    if( &otherbuf != this )//👈
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *this;//👈
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );
    myBuf.Display();
    myBuf = yourBuf;  // assignment operator
    myBuf.Display();
}
```

📌example in #csharp 
```csharp
class Employee
{
    private string name;
    private decimal salary = 3000.00m;

    public Employee(string name)
    {
        this.name = name;//👈
    }

    public void printEmployee()
    {
        Console.WriteLine("Name: {0}", name);
        Console.WriteLine("Taxes: {0:C}", Tax.CalcTax(this));//👈`this` is also an object of Employee, it means current object!!
    }

    public decimal Salary
    {
        get { return salary; }
    }
}

class Tax
{
    public static decimal CalcTax(Employee E)//👈so it can pass to here
    {
        return 0.08m * E.Salary;
    }
}

class MainClass
{
    static void Main()
    {
        Employee E1 = new Employee("Mingda Pan");
        E1.printEmployee();
    }
}
/*
Output:
    Name: Mingda
    Taxes: $240.00
 */
```