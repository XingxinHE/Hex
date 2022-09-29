alias:: strings

- ## 📝Definition
	- In [[Theory of Computation]],
		- A string over an alphabet is a finite sequence of symbols from that alphabet, usually written next to one another and not separated by commas.
			- If $\Sigma_1 = \{0,1\}$, then `01001` is a string over $\Sigma_1$.
			- If $\Sigma_2 = \{a, b, c, . . . , z\}$, then `abracadabra` is a string over $\Sigma_2$.
	- In C++,
		- This is in standard `<string>` library. The `string` is not a primitive type in C++ while it is, in fact, a library type([[user-defined]] type). This is due to history artifact with C.
		- [Microsoft Doc on string](https://docs.microsoft.com/en-us/cpp/standard-library/string?view=msvc-170)
		- [Cpp.com](https://cplusplus.com/reference/string/string/)
		- A bit history of C++ string
			- In its early years, C++ succeeded in part because it includes all of C as a subset, thereby making it possible to evolve gradually from one language to the other. That design decision, however, means that C++ includes some aspects of C that no longer make sense in a modern object-oriented language, but nonetheless need yo be maintained for compatibility.
	- In C,
		- This is in `<cctype>` for dealing with legacy C-Style string.
		- [<cctype> (ctype.h)](https://cplusplus.com/reference/cctype/)
- # ✒Notation
	- [$\Sigma$](((632141f8-0ddc-42fb-aeab-bc0c1727dae3)))
		- The alphabet over which the strings are defined may vary with the application. Therefore, in [[Theory of Computation]], we use $\Sigma$, the Greek symbol, to denote "**alphabet**".
	- [$\epsilon$](((632141f8-5571-4a59-9d18-3d64c1b98077)))
		- Denote the [empty string](((6325ce62-b964-47fc-9a6f-f20a4ffb9b3b))).
- # ⛈Characteristics / Properties
	- 📌Length
		- If $w$ is a string over $\Sigma$, the length of $w$, written $|w|$, is the number of symbols that it contains.
		- If $w$ has length $n$, we can write $w = w_1w_2\cdots w_n$ where each $w_i\in\Sigma$. a.k.a the $w_i$ is a character.
	- 📌Lexicographic order
	  alias::  shortlex order, string order
		- The lexicographic order of strings is the same as the familiar dictionary order with shorter strings precede longer strings. Thus the string ordering of all strings over the
		  alphabet $\{0,1\}$ is
			- $$
			  (\epsilon, 0, 1, 00, 01, 10, 11, 000, . . .)
			  $$
	- 📌Prefix
		- Say that string $x$ is a prefix of string $y$ if a string $z$ exists where $xz = y$.
	- 📌Proper Prefix
		- $x$ is a proper prefix of $y$ if in addition $x\neq y$.
- ## 🎯Intent
   A short description what does this thing do?
- ## 🏷(Sub)Categories
	- 📌Empty string
	  id:: 6325ce62-b964-47fc-9a6f-f20a4ffb9b3b
		- The string of length zero is called the empty string.
	- 📌Substring
		- String $z$ is a substring of $w$ if $z$ appears consecutively within $w$.
- ## 📚Library
	- In C++, `<string>`
		- 📌The `cin >>` operator
			- It will read the word separated by whitespace.
			- ```c++
			  cin >> name;
			  ```
			- When you type:
			- ```cmd
			  Eric Roberts
			  ```
			  The name will only store the first word - `Eric`.
		- 📌`getline` to read entire line
			- ```
			  getline(cin, str);
			  ```
			- When you type:
			- ```
			  Eric Roberts
			  ```
			- The  `str`  will store  `Eric Roberts` .
		- 📌`.at()` of `<string>` library
			- When you access certain element of a  `string`  object, you can:
			- ```
			  str[0] = 'x';
			  str.at(0) = 'x';  ✅
			  ```
			- The latter is much safer since it will **check** whether the index is valid.
		- 📌 `str.substr(start, n)`
			- It creates a new string by extracting  `n`  characters from  `str`  starting at the index position specified by  `start` .
		- 📌 `str.find(pattern)`
			- The  `find`  method will try to find the pattern:
			- success - return the 1st index of that pattern
			- failed - return  `string::npos` 
			  
			  The  `find`  can also take an optional second argument which indicates the index position at which to start the search.
- ## 🧠Intuition
  Find an intuitive way of explanation of this concept.
- ## 🚀Benefit
   A scenario that illustrates the benefit this object provides.
- ## ⌨Sample Code
   Code fragments
	- In C++,
		- 📌Conversion between `<string>` and `C-Style string`
			- ``` c++
			  // C => C++
			  string str = string{cstr};
			  
			  // C++ => C
			  str.c_str();
			  ```
		- 📌`string` in C++ is not a primitive type
			- To prove that:
			- ```
			  string str = "Hello world!";                        // VALID✅
			  string str1 = "hello" + ", " + "world!";            // INVALID❌
			  string str2 = string("hello") + ", " + "world!";    // VALID✅
			  ```
- ## 🐍Algorithm
  Algorithm relates to this stuff..
	- remove duplicate item only using `for` loop without using `set`
		- ``` c++
		  vector<string> words;
		  // words grow here..
		  
		  sort(words); // sort the words
		  for (int i = 0; i<words.size(); ++i)
		  {
		    if (i==0 || words[i–1]!=words[i]) // is this a new word? 👈essence of this algorithm
		    {
		     	//do something here 
		    }
		  }
		  
		  ```
- ## 🌓Complement
  What is the complement of this subject? e.g. vector-covector, constructor-destructor
- ## 🤳Applicability
   What are the situations in which this subject can be applied?
- ## 🧪Composition
  What kind of stuffs composite this subject?
- ## 🔎Implementation
   The code or technical stuffs implement this.
- ## 🕳Pitfalls
  Be aware of the pitfalls when using this stuffs... (especially considering edge cases)
- ## 🙋‍♂️Related Elements
   The closest element to current one, what are their differences?
- ## 📋Prerequisite
  Some techniques and objects only work under certain condition.
- ## 🥼Expert's Advice
  See what experts addressed.
- ## 🧱Structure
  Any other hierarchical issues?