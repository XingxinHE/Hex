
# 📝Definition

#cpp 
- `&&`  , logic **AND**
- `||` , logic **OR**.
- `!`, logic **NOT**

#csharp 
- `&&`  , logic **AND**
- `||` , logic **OR**.
- `!`, logic **NOT**

#JavaScript 
- `&&`  , logic **AND**
- `||` , logic **OR**.
- `!`, logic **NOT**

#Python 
- `and`  , logic **AND**
- `or` , logic **OR**.
- `not`, logic **NOT**

# ⛈Characteristics / Properties
## operator precedence and associativity
- 📝Definition
	- The operators higher up in the table take precedence over operators lower down.
- 🔗Link
	- https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/



# ⌨Sample Code
## Code Style
> 😶Not good but OK:
```c#
bool flag = num >= 0 && num <= 100;
```

> 🙂Clear, #BestPractice :
```c#
bool flag = (num>=0)&&(num<=100);
```

## Short-circuiting
### 📝Definition
Short-circuiting is putting the easier-"true" codes on the left is more efficient as they will jump out of the condition soon.
### 🚀Benefit / Pros
This is very useful for boosting the performance of the codes.
### ⌨Sample Code
```c#
int num = -10;
bool flag = (num>=0) && (num<=100);
```
This is #BestPractice .
```c#
//👍
int num = -10;
bool flag = (num<=100) || (num>=0);
```

# 🕳Pitfalls
❌ Error:

```c#
bool flag = num >= 0 && <= 100;  //ERROR!!!
```

This is hell wrong! When playing with logical operator, the variable can only appear once at a time.


