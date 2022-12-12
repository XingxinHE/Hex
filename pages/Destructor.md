# 🚿Source

> [!question] What triggers destructor?
> - implicitly:
> 	- [[object]] goes out of scope
> 	- [[garbage collection]]
> - explicitly
> 	- [[delete keyword]]


# 📝Definition


# 🎯Intent
A destructor makes sure that an object is properly cleaned up before it is destroyed.

# 🌓Complement
[[Constructor]]

# 🤳Applicability
[[RAII]]

# ⛈Characteristics
The destructor works in a [[recursion|recursive]] way.
```cpp
vector<vector<vector<double>>>* p = new vector<vector<vector<double>>>(13);
delete p;
```
The `delete` will
- trigger the destructor from outside to inside
- back propagate the result from inside to outside

# 🧬Related Elements



# 🗑Unorganized
The destructors for [[data member]] — and for [[base class|bases]] — are implicitly called from a [[derived class]] class destructor (whether [[user-defined]] or generated). Basically, all the rules add up to: “Destructors are called when the object is destroyed” (by going out of scope, by [[delete keyword]], etc.).

As a rule of thumb: if you have a class with a virtual function, it needs a virtual
destructor. The reason is:
1. If a class has a virtual function it is likely to be used as a base class, and
2. If it is a base class its derived class is likely to be allocated using new, and
3. If a derived class object is allocated using new and manipulated through
a pointer to its base, then
4. It is likely to be deleted through a pointer to its base