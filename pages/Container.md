---
aliases: [ADT, abstract data type]
---

# 📝Definition
The term "container" and "ADT" are always used interchangeably.
- In computer science,
    - A container is a class or a [[data structure]] whose instances are collections of other objects.
    - An abstract data type (ADT) is a mathematical model for data types.
    
- In C++,
    - It often refers to [[STL]] which Library provides various type-safe containers for storing collections of related objects. The containers are class templates.
    
# 🧠Intuition
To elaborate an intuition,
- Container emphasizes the **capability** of an object that holds elements (other objects).
- ADT emphasizes the **behavior** (semantics) from the point of view of a user, of the data, specifically in terms of possible values, possible operations on data of this type, and the behavior of these operations.

# 🎯Intent
 A short description what does this thing do?

# 😲Intuitive Explanation
Find an intuitive way of explanation of this concept.

# 🚀Benefit
 A scenario that illustrates the benefit this object provides.

# ⌨Sample Code
 Code fragments

# 🌓Complement
What is the complement of this subject? e.g. vector-covector, constructor-destructor

# 🤳Applicability
 What are the situations in which this subject can be applied?

# 🧪Composition
What kind of stuffs composite this subject?

# 🏷(Sub)Categories
What are the sub objects of this subject?
- In C++, containers can be divided into **3** categories:
    - sequence containers
    - associative containers
    - container adapters
    
# 🔎Implementation
 The code or technical stuffs implement this.
- The iteration order of C++ container
    - Each collection class defines its own policy about iteration order, usually based on considerations of efficiency.
    - TODO the order is "Stanford library" not the STL. Verify it.
    - The iteration is the folloiwng
        - `Vector` - iterate through index
        - `Grid` - the default is row-major order
        - `Map` - natural order, e.g. `int` as key - ascending order, `string` as key - lexicographic order
        - `Set` & `Lexicon` - natural order
        - `Stack` & `Queue` - can't be iterated⚠
        
# 🕳Pitfalls
Be aware of the pitfalls when using this stuffs... (especially considering edge cases)

# 🙋‍♂️Related Elements
 The closest pattern to current one, what are their differences?

# 📋Prerequisite
Some techniques and objects only work under certain condition.

# 🥼Expert's Advice

# 🧱Structure
Any other hierarchical issues?
