# 📝Definition
In modern C++ programming, the [[STL]] includes smart pointers, which are used to help ensure that programs are free of memory and resource leaks and are exception-safe.

# 🎯Intent
The main goal of this idiom is to ensure that resource acquisition([[RAII]]) occurs at the same time that the object is initialized, so that all resources for the object are created and made ready in one line of code.

# 🧠Intuition
Leave programmer out of the burden of using [[pointer|raw pointer]]...

# 🏷(Sub)Categories
What are the sub objects of this subject?
- `unique_ptr`, which owns the object to which it points
- `shared_ptr`, which allows multiple pointers to refer to the same object. also known as reference-counted pointer which this object keeps track of how many `shared_ptr` points to the same object.
- `weak_ptr`, which is a weak reference to an object managed by a `shared_ptr`

# ⌨Sample Code
- example of misuse of `shared_ptr`
    - cause dangling pointer(1) ^566fda0a61b20e34
        - ``` c++
          /* A function dealing with shared pointer */
          void process(shared_ptr<int> ptr)
          {
          // use ptr
          } // ptr goes out of scope and is destroyed
          
          
          int *x(new int(1024));       // dangerous: x is a plain pointer, not a smart pointer
          process(shared_ptr<int>(x)); // legal, but the memory will be deleted!
          int j = *x; 				 // ❌😲undefined behavior: x is a dangling pointer!
          ```
      **What happened**🤔? Since line `9` makes a `shared_ptr` by passing a [[pointer|raw pointer]] and therefore the `ptr` will take that ownership. But!! The lifetime of this `ptr` is only in the function call!!!
      
    - cause dangling pointer(2)
        - ``` c++
          shared_ptr<int> p(new int(42)); // reference count is 1
          int *q = p.get(); // ok: but don’t use q in any way that might delete its pointer
          
          { // new block
            // undefined: two independent shared_ptrs point to the same memory
            shared_ptr<int>(q);  //😓boom... create another one shared_ptr by raw pointer
          } // block ends, q is destroyed, and the memory to which q points is freed
          
          int foo = *p;   // ❌😲undefined; the memory to which p points was freed
          ```
      **What happened**🤔?  I proceed the raw pointer with `shared_ptr` and why could it be wrong? Different from the [[#^566fda0a61b20e34|last one]], this one has different reason causing dangling pointer. In this case, both `p` and `q` point to the same memory. Because `p` and `q` **were created independently from each other**, each has a reference count of 1. When `q` is destroyed, because **they are counting independently**, therefore frees the memory to which `q` points. That makes `p` into a dangling pointer!!
      
- example of using deleter in `shared_ptr`
    - TODO find an example here...
    
- example of best practice using `shared_ptr`
    - use `use_count()` before `reset()`
        - TODO find an example here... Before the title is called test if it is `unique()` before reset. But this `unique()` is deprecated.
        
# 🕳Pitfalls
- Pitfall using `shared_ptr`
    - Don't ever mix using raw pointer and `shared_ptr`.
    