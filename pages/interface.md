# 📝Definition
The term "interface" differs in different programming language.
- More General
    - The set of operations supported by a [[data structure]] is called an **interface**.
    
- For C++
    - An interface describes the behavior or capabilities of a C++ class without committing to a particular implementation of that class.
    
- For C# and Java
    - An interface defines a contract. Any class or struct that implements that contract must provide an implementation of the members defined in the interface.
    
# 🧠Intuition
Since the definition differs, here as well.
- For [[C#]] and [[Java]]
    - Interface is a language element.
    
- For [[C++]],
    - Interface is a concept and it is very close to the General Concept.
    
# 🗃Example
Example is the most straightforward way to understand a concept.
- In C#,
    - `List<T>` has the interface `Add()`.
    - `Dictionary<TKey, TValue>` has the interface `Add()`.
    - They are with **same** semantics but their logic behind are highly **different**.⚠
    
- In C++,
    - `std::vector` has the interface `begin()`
    - `std::deque` has the interface `begin()`
    - They are with **same** semantics but their logic behind are highly **different**.⚠
    
# 🙋‍♂️Related Elements
 The closest pattern to current one, what are their differences?
- The representation of an interface is called [[Signature]].

# 🎯Intent
 A short description what does this thing do?

# 🚀Benefit
 A scenario that illustrates the benefit this object provides.

# ⌨Sample Code
 Code fragments

# 🌓Complement
- What is the complement of this subject? e.g. vector-covector, constructor-destructor
- ![[data structure#^8a966e5bc270ebf]]

# 🤳Applicability
 What are the situations in which this subject can be applied?

# 🧪Composition
What kind of stuffs composite this subject?

# 🏷(Sub)Categories
What are the sub objects of this subject?

# 🔎Implementation
 The code or technical stuffs implement this.

# 🕳Pitfalls
Be aware of the pitfalls when using this stuffs... (especially considering edge cases)

# 🧱Structure
Any other hierarchical issues?
