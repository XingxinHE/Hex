---
aliases: [final keyword]
tags:
  - cpp
  - LanguageKeyword
---
# 📝Definition
Use the **final** keyword to 
- designate [[virtual function]]s that cannot be overridden in a [[derived class]].
- designate [[class]]es that cannot be inherited.

# ✒Syntax
```cpp
function-declaration final;
class class-name final base-classes
```


# 🗃Example
**📂example specify that a virtual function cannot be overridden**
```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // ❌compiler error: attempting to
                         // ❌override a final function
};
```

**📂example specify that a class cannot be inherited**
```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // ❌compiler error: BaseClass is
                                     // ❌marked as non-inheritable
{
};
```