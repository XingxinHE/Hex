---
aliases: [identifier]
---
# 📖Terminology
## Identifier vs. Variable
I think they are very similar to each others.
- identifier is to be "==identified==" by the [[compiler]].
- The name of variable is an identifier while variable also contains value.
> [!NOTE] 
> Sometimes people use "identifier" and variable interchangeably. Therefore I put them together.



# 📝Definition
- A named [[object]] of a given [[type]] is called a variable; contains a value unless uninitialized.
- A variable is a box in the **computer’s memory** that holds **temporary information**.
- Identifiers are the names that you use to identify the elements in your programs, such as namespaces, classes, methods, and variables.
# 🧠Intuition
Identifiers are literally the composition of English character, numbers, and symbols.

# ⚖Laws
In #cpp and #csharp ,
- MUST start with 1️⃣underscore or 2️⃣letters
- ONLY 1️⃣letters (uppercase and lowercase), 2️⃣digits, and 3️⃣underscore characters


# 🗃Example
- `result`✅
- `_score`✅
- `footballTeam`✅
- `plan9`✅
- `result%`❌
- `footballTeam$`❌
- `9plan`❌


# ⌨Sample Code
## #cpp 


## #csharp 
### [[declaration]]
```c#
type variableName;
int age;
```

### [[assignment]]
After [[declaration]], you are allowed to assign value to variable by [[Copy Assignment Operator]] assign operator `=`   :

```c#
age = 28;
```

### Declare and Assign
You can also combine **declare** and **assign** altogether:

```c#
int age = 28;
```


## #JavaScript 
