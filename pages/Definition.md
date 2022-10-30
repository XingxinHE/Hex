# 📝Definition
- In mathematics, Definitions describe the objects and notions that we use.

# 🎯Intent
In terms of different things, its intent is different.
- definition is where compilers set aside [[memory]] for:
    - built-in type object
    - user-defined type object
    
- definition is providing the code body for the following. Note that function bodies are stored in [[memory]] as part of the program:
    - function
    - template function
    
- definition lists the members for:
    - class
    - template class
    
-

# 😲Intuitive Explanation
A definition provides compilers with details a [[Declaration]] omits.

# 🌓Complement
- ![[Declaration#^72ee5fd56e669cbb]]

# 🚀Benefit
 A scenario that illustrates the benefit this object provides.

# ⌨Sample Code
- On object definition
  
  ``` c++
  int x;
  ```
- On function definition
  
  ``` c++
  std::size_t numDigits(int number)
  {
    std::size_t digitsSoFar = 1;
    while ((number /= 10) != 0) ++digitsSoFar;
    return digitsSoFar;
  }
  ```
- On class definition
  
  ``` c++
  class Widget
  {
  public:
    Widget();
    ~Widget();
    //...
  }
  ```
- On template definition
  
  ``` c++
  template<typename T>
  class GraphNode
  {
  public:
    GraphNode();
    ~GraphNode();
  }
  ```

# 🙋‍♂️Related Elements
 The closest pattern to current one, what are their differences?

# 🧱Structure
 ...

# 🤳Applicability
 What are the situations in which the design pattern can be applied?

# 🤼Participants
 The participated classes and/or objects and their responsibility.

# 🤝Collaborations
 How the participants work together?

# 📈Consequences
 The trade-off and results.

# 🔎Implementation
 What pitfalls, hints, or techniques should be aware of implementing the pattern?

# 🤔Known Issues
 Examples
