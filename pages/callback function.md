---
aliases: [callback]
---
# 📝Definition
A **callback** or **callback function** is any **==reference==** to [executable code](https://en.wikipedia.org/wiki/Executable_code "Executable code") that is passed as an [[Glossary#Argument|argument]] to another piece of code; that code is expected to _call back_ (execute) the callback function as part of its job.

This execution may be immediate as in a **synchronous callback**, or it might happen at a later point in time as in an **asynchronous callback**.

# 🔎Implementation
The code or technical stuffs implement this.
- #cpp , use [[function pointer]]
- #csharp , use [[Delegate]]
# 🗃Example
Following are a few callback functions implemented in different languages.

📌 #c and #cpp version
```cpp
string startKUKA(int amount)
{
    return string{"Start " + std::to_string(amount) + " KUKA robots!"};
}

string startABB(int amount)
{
    return string{"Start " + std::to_string(amount) + " ABB robots!"};
}

//👇`startRobot` is a callback function
void startMachine(string(*startRobot)(int), int amount)
{
    cout << startRobot(amount) << endl;
}

int main()
{
    startMachine(&startKUKA, 6);  //👈take the address of the function by `&`
    startMachine(&startABB, 3);   //👈take the address of the function by `&`
    return 0;
}
```

📌 #JavaScript version
```javascript
function calculate(num1, num2, callbackFunction) {
    return callbackFunction(num1, num2);
}

function calcProduct(num1, num2) {
    return num1 * num2;
}

function calcSum(num1, num2) {
    return num1 + num2;
}
```


📌 #Python version
```python
>>> def get_square(val):
...     """The callback."""
...     return val ** 2
...
>>> def caller(func, val):
...     return func(val)
...
>>> caller(get_square, 5)
25
```

📌 #julia version
```julia
julia> get_square(val)  = val^2 # The callback get_square (generic function with 1 method)
julia> caller(func,val) = func(val) # The caller (generic function with 1 method)
julia> caller(get_square,5)
25
```
