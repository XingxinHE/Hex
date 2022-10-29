- ## 😲Intuitive Explanation
  you can't reliably predict what will happen at [[run-time]].
- ## 😷Symptoms
  The program will behave erratically:
	- sometime running normally
	- other times crashing
	- other times produce incorrect results
- ## ⌨Sample Code
	- 2 examples of code with undefined behavior
	  id:: 63082850-6985-44f0-9172-349283801310
	  
	  ``` c++
	  
	  int *p = 0;		//p is a null pointer
	  std::cout << *p;	//dereferencing a null pointer yields undefined behavior
	  
	  char name[] = "Darla";  //name is an array of size 6(including the last null)
	  char c = name[10];		//referring to an invalid array index yields undefined behavior
	  ```