# 📝Definition
- In a typical machine, that memory is built out of special integrated-circuit called RAM, which stands for random-access-memory.
- The computer's memory is a [[Tuple|sequence]] of [[Byte|bytes]] numbered from $0$ to the memory size minus $1$.

# 🎯Intent
- For programmer, we should be aware of how the memory is organized.


# 📈Diagram
![name|500](../assets/memory_map_horizontal.svg)
```cpp
int var = 17;
int* ptr = &var;
```
In the preceding diagram,
- the `ptr` is variable which holds an address in the memory.
- `4096` is an address which held by the `ptr` variable.
- `4096` is the $(2^{12}+1)$-th address of the memory. The value stored at `4096+1`-th address is `17`.
> [!tip] Idea
> `ptr` is a variable which holds an arrow. That arrow points to a place in memory.

