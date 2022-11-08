# 📝Definition
- *Iterator* is an object that identifies an element of a sequence.

# 🎯Intent
- In C++
    - More specifically, an iterator is an object that can iterate over elements in a [[C++]] [[STL]] container and provide access to individual elements.
    
# 😲Intuitive Explanation
- Use a same and consistent syntax to iterate the [[STL]] container.

# 🚀Benefit
- Using same syntax and interface provides lots of benefit. For example, the `++` for vector is to query the next element, so as `++` for linked list. But the next address of a linked list cannot be just incremented. Therefore, we can override their operator.
  
  ``` c++
  // no matter which container is
  // a pseudo code of the iterator could be like this
  for(iter = numbers.begin(); iter!=numbers.end(); iter++)
  {
  
  }
  ```

# 🙋‍♂️Related Elements
- [[IEnumerable]]
