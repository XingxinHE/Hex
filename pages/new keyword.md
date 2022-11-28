# 📝Definition
- In #cpp , the `new` operator attempts to allocate and initialize an object or array of objects of a specified or placeholder type, and returns a suitably typed, nonzero [[pointer]] to the object (or to the initial object of the array).
- In #csharp , https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-modifier

# 🧠Intuition
The `new` operator allocates("get") memory from the [[Heap|free store]].

# 🌓Complement
[[delete keyword]]

# 🕳Pitfalls
- Please don't forget to `delete` memory which has been `new`. Otherwise it will cause memory leak! 
- A “naked” new outside a constructor is an opportunity to forget to delete the object that new created. Unless you have a good strategy for deleting objects, try to keep news in [[Constructor|constructors]] and deletes in [[Destructor|destructors]].
