# 📝Definition
A mismatch between reasonable expectations of [[program]] behavior (often expressed as a requirement or a users’ guide) and what a program actually does.

# 🏹Strategy
[[Error-Handling]] is the art of handling errors.

# 🏷(Sub)Categories
- There are many ways of classifying errors. For example:
- Compile-time errors: Errors found by the compiler. We can further classify compile-time errors based on which language rules they violate, for example:
    - Syntax errors
    - Type errors
    
- Link-time errors: Errors found by the linker when it is trying to combine object fi les into an executable program.
- Run-time errors: Errors found by checks in a running program. We can further classify run-time errors as
    - Errors detected by the computer (hardware and/or operating system)
    - Errors detected by a library (e.g., the standard library)
    - Errors detected by user code
    
- Logic errors: Errors found by the programmer looking for the causes of erroneous results.

# 🥼Expert's Advice
- By Bjarne,
    - Errors are always more common when you are tired or rushed.
    