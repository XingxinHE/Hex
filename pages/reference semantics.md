---
aliases: [pointer semantics]
---
# 📝Definition
With reference semantics, [[assignment]] is a [[pointer]]-copy (i.e., a [[Reference Type|reference]]). 

# 🎯Intent
Avoid copying large and bulky [[value]]. 

# 🚀Benefit / Pros
flexibility and dynamic binding.

# 🗃Example
**📂reference semantics example 1**
```cpp
QPushButton *pb1 = new QPushButton{};
QPushButton *pb2 = pb1;
pb2->setText("OK");
```
If 2 objects refer to the same value, modifying 1 object will also change the value in the other object.

# 🕳Pitfalls
When you have an assignment operation, please be aware the shallow vs. deep copy.

# 🌓Complement
## When should I use Reference and Value Semantics?
That is the answer I should find in [here](https://isocpp.org/wiki/faq/value-vs-ref-semantics).