- ## 🏷(Sub)Categories
	- The syntax of `delete` keyword is different in terms of:
	- objects
	  
	  ``` c++
	  int *pi;
	  pi = new int(1024);
	  delete pi;  //delete an object
	  ```
	- array
	  
	  ``` c++
	  int *pia = new int[24];
	  delete [] pia;  //delete an array
	  ```