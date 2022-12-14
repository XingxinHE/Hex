---
aliases: [header]
---

- convention... put following here
    - [[inline function]]
    - [[constexpr]]
    - [[consteval]]
    - `template`  class definition
    
# 📋Prerequisite
Please always add _[[include guards]]_ to header file.⭐

# 📝Definition
A file containing [[declaration]]s used to share [[interface]]s between parts of a [[program]].

# 🎯Intent
 A short description what does this thing do?

# 🧠Intuition
A header is a collection of [[declaration]]s.

# ✒Notation
- Sample to use a header file
    - ```c++
      #include <iostream>
      #include "igl_mesh"
      ```
    
- Use `" "`
    - if the header file is in the same directory as the program text file including it.
    
- Use `< >`
    - if the header file is anywhere else.
    


# 🚀Benefit
The benefit separating the header file and source file sees [[class#Separation in behavior and implementation]].

# ⌨Sample Code
 Code fragments

# 🌓Complement
[[source file]]

# 🧪Composition
What kind of stuffs composite this subject?

# 🏷(Sub)Categories
What are the sub objects of this subject?

# 🔎Implementation
 The code or technical stuffs implement this.

# 🕳Pitfalls
Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
- Why not put everything here?
    - because header file is "dependencies". One change may cause others' recompile.
    
# 🙋‍♂️Related Elements
 The closest pattern to current one, what are their differences?

# 🥼Expert's Advice

# 🧱Structure
Any other hierarchical issues?
