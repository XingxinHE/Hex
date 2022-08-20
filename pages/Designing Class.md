alias:: class design

- ...
- 📌Design Choice on writing function in class declaration or class definition
	- The **RULE**: Don’t put member function bodies in the class declaration unless you know that you need the performance boost from inlining tiny functions.
	- The **EFFECTS** of Writing the definition of a member function within the class definition
		- The function will be inline; that is, the compiler will try to generate code for the function at each point of call rather than using function-call instructions to use common code. This can be a signifi cant performance advantage for functions, such as month(), that hardly do anything but are used a lot.
		- All uses of the class will have to be recompiled whenever we make a change to the body of an inlined function. If the function body is out of the class declaration, recompilation of users is needed only when the class declaration is itself changed. Not recompiling when the body is changed can be a huge advantage in large programs.
		- The class definition gets larger. Consequently, it can be harder to find the members among the member function definitions.