---
aliases: [type alias]
---

# 📝Definition
Alias declaration is to declare a name to use as a synonym for a previously declared type.

# 🎯Intent
- In C++, Alias declaration is intent to deal with:
    - types involving [[function pointer]]s.
      
      ``` c++
      // FP is a synonym for a pointer to a function taking an int and
      // a const std::string& and returning nothing
      typedef void(*FP)(int, const std::string&);  //typedef
      
      // same meaning as above
      using FP = void(*)(int, const std::string&); //alias declaration is much simpler
      ```
    - alias templates
      
      ``` c++
      
      ```
    