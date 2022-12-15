---
tags:
  - LanguageKeyword
  - cpp
---
# 📝Definition
`size_t` is the [[signedness|unsigned]] integer type of the result of [[sizeof operator]] , _Alignof (since C11) and offsetof, depending on the data model.

# ⛈Characteristics
There are 2 characteristics of `size_t`:
1. it is always [[signedness|unsigned]] integer type.
2. its value depends on the hardware(<u>platform-dependent</u>; ).

# 🎯Intent
There are 2 intents of it:
1. see the [[byte]] of certain [[variable]]
2. working with [[array]]


# 🕳Pitfalls
**🕳Misuse `size_t`**
#error-prone 
A common mistake is to assume `size_t` is the same as `unsigned int`, which can lead to programming errors, particularly as 64-bit architectures become more prevalent.

# 🧬Related Elements
[[ptrdiff_t]]
