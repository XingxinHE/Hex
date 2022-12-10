---
aliases: [copy semantics]
---
# 📝Definition
Value (or “copy”) semantics mean assignment copies the value, not just the pointer. If the [[class]] or [[type|data type]] strictly implements the value semantics, you must use the [[assignment|assignment operator]] to modify the [[value]].

If the data type

# 🚀Benefit / Pros
**Speed**

> [!NOTE] Note on "speed"
> “Speed” seems like an odd benefit for a feature that requires an object (vs. a pointer) to be copied, but the fact of the matter is that one usually accesses an object more than one copies the object, so the cost of the occasional copies is (usually) more than offset by the benefit of having an actual object rather than a pointer to an object.
> 
> #TODO  To be honest, I am not quite understand what it said in [isocpp FAQ](https://isocpp.org/wiki/faq/value-vs-ref-semantics#val-vs-ref-semantics).

# ⛈Characteristics
## 🌧[[mutability and immutability|immutability]]
**📝Definition**
The value semantics imply the immutability of an [[object]].

> [!NOTE] Note
> The only way to modify an immutable object is to use assignment operator to pass new value to it.

**🗃Example**
📂value semantics example 1
```cpp
QString str = "hello world!";
str = str.left(5);
```
Why should we use [[assignment|assignment operator]] to assign back to `str`? It simply because the function `left` is designed in value semantics. Therefore, `str.left(5)` does not modify its original value. Here is the proof.
```cpp
QString	left(qsizetype n) const
```


# 🌓Complement
![[reference semantics#🌓Complement#When should I use Reference and Value Semantics?]]