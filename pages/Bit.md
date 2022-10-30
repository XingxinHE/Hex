---
aliases: [binary digits]
---

# 📝Definition
The name is the essence of this topic.

# 🎯Intent
- The state `0` and `1` which are two digits used in the binary number system on which computer arithmetic is based.

# 🧠Intuition
Find an intuitive way of explanation of this concept.
- The meaning of bits in memory is completely **dependent** on the [[type]] used to access it. Think of it this way: computer memory doesn’t know about our types; it’s just memory. The bits of memory get meaning only when we decide how that memory is to be interpreted.
- What does `12.5` mean? We don’t know. It could be `$12.5` or `12.5cm` or `12.5gallons`. Only when we supply the unit does the notation `12.5` mean anything.

# 🚀Benefit / Pros
- Good for machine code.

# 🕳Pitfalls / Cons
- Binary numbers are **cumbersome**, mostly because they tend to be so long.

# 🗃Example  
Example is the most straightforward way to understand a mathematical concept.
- 📌Example of interpretation of bits in memory
    - Short review. As addressed in the definition, bit is merely bit. It is meaningful only until we think of it with type.
    - Question. What is `01000001` in terms of `char`?
        - Convert the bits to decimal.
          ![name](../assets/01000001_bits.png){:height 500, :width 500}
        - Therefore it is $2^6\times1+2^0\times1=65$
        - In light of [[Glossary#ASCII Character Codes|ASCII Table]], `01000001` is character `A`.
        
# ⌨Sample Code
 Code fragments

# 🌓Complement
What is the complement of this subject? e.g. vector-covector, constructor-destructor

# 🤳Applicability
 What are the situations in which this subject can be applied?

# 🧪Composition
What kind of stuffs composite this subject?

# 🏷(Sub)Categories
What are the sub objects of this subject?

# 🔎Implementation
 The code or technical stuffs implement this.

# 🧬Related Elements
The stuffs are closed related to bit.
- 📌 Bit and [[Byte]] Conversion
    - ![name](../assets/bit_byte_conversion.png){:height 300, :width 300}
    - Since one bit is either `0` or `1` so therefore 8 bits have $2^8=256$ possibilities.
    
# 📋Prerequisite
Some techniques and objects only work under certain condition.

# 🥼Expert's Advice
- Gottfried Wilhelm Leibniz (1646-1716), one of the greatest intellects of his time, was fond of the dyadic system. To quote Laplace: “Leibniz saw in his binary arithmetic the image of creation. He imagined that Unity represented God, and zero the void; that the Supreme Being drew all beings from the void, just as unity and zero express all numbers in his system of numeration.”

# 🧱Structure
Any other hierarchical issues?
