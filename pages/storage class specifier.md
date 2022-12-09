# 📝Definition
A _storage class specifier_ in the context of #cpp variable declarations is a type specifier that governs the lifetime, linkage, and memory location of objects.
# 📋Prerequisite
A given object can have **only one** storage class.

# 🏷(Sub)Categories
There are 3 kinds of specifiers:
- [[extern|extern keyword]]
- [[static keyword]]
- [[thread_local keyword]]

# 🎯Intent
As mentioned, these specifiers intent to play with the storage. Variables defined within a block may have:
- automatic storage
- other storages by using the **`extern`**, **`static`**, or **`thread_local`** specifiers. 

> [!NOTE] Note
> Automatic objects and variables have no linkage; they aren't visible to code outside the block. Memory is allocated for them automatically when execution enters the block, and it's de-allocated when the block is exited.
