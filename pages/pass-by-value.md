# 📝Definition
The name is the essence of this topic.
- this is the **default** behavior of all types in #cpp 
- this is the default behavior of only [[Value Type]] in #csharp 

# 📈Diagram
From the diagram below, you can see "pass by value" is actually making a full copy (see the difference of address).
```cpp
std::vector<int> v1{1, 2, 3, 4, 5};
std::vector<int> v2;

v2 = v1;
```
![name|500](../assets/pass-by-value-memory.png)


# 🙋‍♂️Related Elements
 The closest element to current one, what are their differences?
![[pass-by-reference#^75db37bf4ac72c6b]]
