# 📝Definition
The most vexing parse is a counterintuitive form of syntactic ambiguity resolution in the #cpp  programming language. In certain situations, the C++ grammar cannot distinguish the following 2.
- the creation of an object parameter
- specification of a function's type.

# 🗃Example
**📂example on most vexing parse(1)**
```cpp
void f(double my_dbl) {
  int i(int(my_dbl));
}
```
Line 2 above is **ambiguous**😲. However, due to C allows superfluous parentheses around function parameter declarations. There are 2 interpretation.
One is to interpret to **declare a variable** `i` with initial value produced by converting `my_dbl` to an `int`.
```cpp
//an int object with initial value of `my_db1`
int i = my_db1;
```

Other is to interpret to **declare a function** `i`.
```cpp
// A function named i takes an integer and returns an integer.
int i(int my_dbl);
```


**📂example on most vexing parse(2)**
```cpp
Widget w1(10); // ✅🆗call Widget ctor with argument 10

Widget w2(); // ❌most vexing parse! declares a function
			 // named w2 that returns a Widget!

Widget w3{}; // ✅calls Widget ctor with no args bu using {} init
```