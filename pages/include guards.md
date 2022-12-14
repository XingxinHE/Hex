---
tags:
  - BestPractice
  - pitfall
---

# 📝Definition
Include guards are something like the following.
```cpp
// file foobar.h:
#ifndef LIBRARY_FOOBAR_H
#define LIBRARY_FOOBAR_H
// ... declarations ...
#endif
// LIBRARY_FOOBAR_H
```

# 🎯Intent
By adding _include guards_ around the header contents, you ensure that the names a [[header file|header]] [[declaration|declares]] are only declared once for each [[translation unit]]. Define the name in only one [[source file|implementation file]].