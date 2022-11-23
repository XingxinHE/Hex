---
aliases: [memory map, memory layout]
---

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



# ⛈Properties
## Memory Address
### 📝Definition
Within the memory system of a typical computer, every [[Byte|byte]] is identified by a numeric ==**address**==.
The 1st byte in the computer is numbered 0, the 2nd is numbered 1, and so on, up to the number of bytes in the machine minus 1.
### ✒Notation
Address numbers are conventionally written in [[hexadecimal]].

> [!NOTE] Note
> Address用16进制只是一种表现形式，其核心还是排序，e.g.第几个地址。

### 🗃Example
The memory addresse in a tiny 64KB computer.
- index of beginning byte: 0 ---to hexadecimal---> `0`
- index of ending byte: 65,535 ---to hexadecimal---> `FFFF`


## Memory Layout


___
- Code generators and linkers usually separate entities into different program section, such as:
    - "text" or "code" for machine instruction
    - "literal" for initialized read-only data
    - "data" for initialized read-write data
    - "bss" for uninitialized read-write data
    
- The [[Linker]] is responsible for arranging these sections in memory. User can use "linker script" to do that.

- Such arrangement is the program's memory map.
  ![memory map](../assets/memory_map.svg){:height 300, :width 300}

- Controlling Memory Map
    - This can benefit the embedded system which has objects declared at different space.
    - ![memory map](../assets/controlling_memory_map.svg){:height 300, :width 300}
