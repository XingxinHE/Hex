---
aliases: [The auto Type Specifier]
tags:
  - cpp
  - LanguageKeyword
---

# 📝Definition
`auto` is a [[Type Specifier]] which [[Type Deduction|deduces the type]] of a declared variable from its initialization expression.

# 🚀Benefit / Pros
The `auto` keyword provides following benefits:
-   **Robustness:** If the expression's type is changed—including when a function return type is changed—it just works.
-   **Performance:** You're guaranteed that there's no conversion.
-   **Usability:** You don't have to worry about type name spelling difficulties and typos.
-   **Efficiency:** Your coding can be more efficient.

# 🧠Intuition
`auto` let the [[compiler]] figure out the [[type]] for us.



# ✒Notation
> **`auto`** _declarator_ _initializer_ **`;`**

> **`[](auto`** _param1_ **`, auto`** _param2_ **`) {};`**
