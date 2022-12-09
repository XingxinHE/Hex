# 📝Definition
Forwarding reference is a special kind of [[Reference Type|reference]] that preserve the [[value categories]] of a function argument, making it possible to forward it by means of `std::forward`.

# 🧠Intuition
**📌How to distinguish forward reference?**
The most important ==2== signs to identify forwarding reference are:
- involve [[Type Deduction]]
- some code like `T&&`, `auto&&`
Like this:
```cpp
template< typename T >
void f( T&& x ); 		// 👈Forwarding reference

auto&& var2 = var1; 	// 👈Forwarding reference
```

**📌What does forward references mean?**
`lvalue` is still an `lvalue` if they are initialized by an `lvalue`.
`rvalue` is still an `rvalue` if they are initialized by an `rvalue`.

# ⌨Sample Code
**📌Prove the objective of forwarding reference**
Suppose I have:
```cpp
// I have a class.
class Widget{};

// I have a function.
template <typename T>
void f( T&& x ) 		// 👈Forwarding reference
{
    std::cout << "f.." << std::endl;
}
```

>     ​	Proof -`lvalue` is still `lvalue`
```c++
int main()
{
    Widget w{};
    f(w);
  
    return 0;
}
//output: f..
```
Therefore we prove that `T&& x` looks like `rvalue` reference, it can accept `lvalue` as well.

>     ​	Proof -`rvalue` is still `rvalue`
```c++
int main()
{
    f(Widget{});
  
    return 0;
}
//output: f..
```
`Widget{}` doesn't have a name and therefore it is an `rvalue`. Therefore we prove that `T&& x` accepts `rvalue` as well.

# 🕹Quiz
**📌Quiz 1 - What is forward reference and what is not?**
```c++
template< typename T >
void f( const T&& );
```
- forward reference ❌
- Function template with rvalue reference-to-const ✅

**📌Quiz 2 - What is forward reference and what is not?**
```cpp
template< typename T >
class A
{
public:
	A( T&& t )
		: b_( std::forward<T>( t ) )
	{}
private:
	B b_;
};
```
- forward reference ❌
- The `T&&` in `A(T&& t)` is just `rvalue` reference. **Forward reference does not work in class template**!!

**📌Quiz 3 - What is forward reference and what is not?**
```cpp
template< typename T >
void f( T&& );
```
- forward reference ✅

