- # 😎Quick Digest -> Dynamic Memory
	- ## 📝Definition
		- In C++, it requires us to allocate the memory of stuffs like variables and arrays in run-time. This is known as dynamic memory allocation.
		- In other programming languages such as Java and Python, the compiler automatically manages the memories allocated to variables.
	- ## 🎯Intent
	  Programs tend to use dynamic memory for one of three purposes:
		- They don’t know how many objects they’ll need. e.g. the implementation of dynamic array
		- They don’t know the precise [[type]] of the objects they need
		- They want to share data between several objects.
	- ## 🔎Implementation
	   The code or technical stuffs implement this.
		- In C++, we use [[pointer]] to do this.
			- 🙁raw pointer, outdated methodology
			- 🙂smart pointer, much preferable
	- ## 🧠Intuition
	  Find an intuitive way of explanation of this concept.
	- ## 🚀Benefit
	   A scenario that illustrates the benefit this object provides.
	- ## ⌨Sample Code
	   Code fragments
		- 📌Use `shared_ptr` to share data between several objects
			- Expected Result
				- ``` c++
				  StrBlob b1;  //blank blob
				  
				  {
				    StrBlob b2 = {"a", "an", "the"};
				    b1 = b2;     //b1 and b2 share the same elements
				    b2.push_back("about");
				  } //b2 is destroyed but the string blob can't be deleted!
				  
				  //b1 should own "a", "an", "the", "about"
				  
				  ```
			- Design Strategy
				- use `std::vector` as container to store stuffs
				- use `std::shared_ptr` to share resource
			- Implementation
				- Header File
				  
				  ``` c++
				  //header include guard
				  #ifndef STR_BLOB_H
				  #define STR_BLOB_H
				  
				  #include <string>
				  #include <vector>
				  #include <memory>
				  
				  class StrBlob
				  {
				  
				  public:
				      using size_type = std::vector<std::string>::size_type;  //👈alias declaration
				    
				    	/* Constructor */
				      StrBlob();
				      StrBlob(std::initializer_list<std::string> il);
				  
				    	/* basic size and empty function as std container */
				      size_type size() const { return data->size(); }
				      bool empty() const { return data->empty(); }
				  
				      void push_back(const std::string &t) { data->push_back(t); }
				      void pop_back();
				  
				    	/* non-const version of front and back */
				      std::string &front();
				      std::string &back();
				  
				    	/* const version of front and back */
				      const std::string &front() const;
				      const std::string &back() const;
				  
				  private:
				    	/* private member */
				      std::shared_ptr<std::vector<std::string>> data;
				      void check(size_type i, const std::string &msg) const;
				  };
				  
				  #endif
				  ```
				- Source File
				  
				  ``` c++
				  #include <stdexcept>  //👈for throwing std::out_of_range
				  #include "StrBlob.h"
				  
				  using namespace std;
				  
				  StrBlob::StrBlob()
				         :data{make_shared<vector<string>> () }  //👈 {} init
				         {}
				  
				  StrBlob::StrBlob(initializer_list<string> il)
				         :data{make_shared<vector<string>>(il)}  //👈 {} init
				         {}
				  
				  void StrBlob::check(size_type i, const string &msg) const
				  {
				      if (i >= data->size())
				      {
				          throw out_of_range(msg);
				      }
				  }
				  
				  string& StrBlob::front()
				  {
				      check(0, "front on empty StrBlob");
				      return data->front();
				  }
				  
				  string& StrBlob::back()
				  {
				      check(0, "back on empty StrBlob");
				      return data->back();
				  }
				  
				  const string& StrBlob::front() const
				  {
				      check(0, "front on empty StrBlob");
				      return data->front();
				  }
				  
				  const string& StrBlob::back() const
				  {
				      check(0, "back on empty StrBlob");
				      return data->back();
				  }
				  
				  void StrBlob::pop_back()
				  {
				      check(0, "pop_back on empty StrBlob");
				      data->pop_back();
				  }
				  
				  ```
				- Client Code
				  
				  ``` c++
				  #include <iostream>
				  #include "StrBlob.h"
				  
				  using namespace std;
				  
				  int main()
				  {
				      StrBlob b1;
				  
				      {
				          StrBlob b2 = {"a", "an", "the"};
				          b1 = b2;
				          b2.push_back("about");
				      }
				  
				      while(!b1.empty())
				      {
				          cout << b1.back() << endl;
				          b1.pop_back();
				      }
				  
				      return 0;
				  }
				  ```
				  The result will be:
				  
				  ``` shell
				  about
				  the
				  an
				  a
				  ```
	- ## 🌓Complement
	  What is the complement of this subject? e.g. vector-covector, constructor-destructor
	- ## 🤳Applicability
	   What are the situations in which this subject can be applied?
	- ## 🧪Composition
	  What kind of stuffs composite this subject?
	- ## 🏷(Sub)Categories
	  What are the sub objects of this subject?
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