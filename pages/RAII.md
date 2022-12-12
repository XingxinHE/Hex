---
tags:
  - BestPractice
---
# 📝Definition
Resource acquisition is initialization (RAII) is a programming idiom used in several object-oriented, statically-typed programming languages to describe a particular language behavior.

# 🎯Intent
For resource management based on scopes.

# 🤷‍♂️Why should I care?
#BjarneStroustrup  stated that this is the most important subject of C++.

# 🧠Intuition
The idiom of having [[Constructor]] acquire resources and [[Destructor]] release them is called RAII (“Resource Acquisition Is Initialization”).

# 🔎Implementation
The basic idea is simple:
- Whatever resources a [[class]] [[object]] needs to function, it acquires in a [[Constructor]].
- During the object’s lifetime it may release resources and acquire new ones.
- At the end of the object’s lifetime, the [[Destructor]] releases all resources still owned by the object.
