# 📝Definition
A [[declaration|declaration]] of an explicit input to a [[function|function]] or a template. When called, a function can access the arguments passed through the names of its parameters.

# 🧠Intuition
A parameter is a variable in a method definition.


# 🌓Complement
[[argument]]

# 🧬Related Elements
## [[pointer]] and [[Reference Type|reference]] parameters
> #FunctionDesign 

Suppose you want to change the value of a variable in a function. You have 3 choices.
```cpp
int incre_value(int x) { return x+1; }
void incre_pointer(int *p) { ++*p; }
void incre_ref(int &r) {++r;}
```
Which is the ==best== ? The answer is :
> "The choice depends on the nature of the function."

1️⃣ `int incre_value(int x) { return x+1; }`
- obvious😊
- less error-prone😊
- good for tiny object, prefer [[pass-by-value]]😊

2️⃣`void incre_pointer(int *p) { ++*p; }`
- indicate the function might change something😊 e.g. `incre_pointer(&num);`
- tedious to check [[null pointer|nullptr]] 😶

3️⃣`void incre_ref(int &r) {++r;}`
- hard to observe if the value is changed😶 e.g. `incre_ref(x);`
- good for pass big object😊

