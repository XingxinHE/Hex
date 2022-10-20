- ⛈Characteristics / Properties
	- Commands are #case-insensitive . But lower case commands are preferred👍.
- 🧪Composition
	- The 3 **==essential==** commands⭐
		- [cmake_minimum_required()](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html#command:cmake_minimum_required)
		- [project()](https://cmake.org/cmake/help/latest/command/project.html#command:project)
		- [cmake_minimum_required()](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html#command:cmake_minimum_required)
- 🥘Regular Recipe
	- Build and Run Recipe 1
		- For the following file structures
		  ``` 
		  .
		  ├── 📁Step1/
		  │   ├── 📄CMakeLists.txt
		  │   └── 📄tutorial.cxx
		  └── 📁Step1_build
		  ```
		- Commands Behind
			- 1️⃣create a build directory
			  `mkdir Step1_build`
			- 2️⃣navigate to that build directory and run [cmake](https://cmake.org/cmake/help/latest/manual/cmake.1.html#manual:cmake(1)) to **configure** the project and generate a native build system
			  `cd Step1_build`
			  `cmake ../Step1`
			- 3️⃣call that build system to actually compile/link the project
			  `cmake --build .`
			  The `.` means "build at current folder".
	- 📌Basic Recipe
		- File structures overview
			- ``` 
			  .
			  ├── 📁Step1/
			  │   ├── 📄CMakeLists.txt
			  │   ├── 📄.version
			  │   └── 📄tutorial.cxx
			  └── 📁Step1_build
			  ```
		- Command Line
			- ``` shell
			  cd Step1_build
			  cmake ../Step1
			  cmake --build .
			  ```
		- Key Files Overview
			- 📄`CMakeLists.txt`
			  
			  ``` cmake
			  # 1️⃣specify the cmake version
			  cmake_minimum_required(VERSION 3.10)
			  
			  # 2️⃣specify the project name and version
			  project(Tutorial VERSION 1.0)
			  
			  # 3️⃣specify the cpp standard
			  set(CMAKE_CXX_STANDARD 11)
			  set(CMAKE_CXX_STANDARD_REQUIRED ON)
			  
			  # 4️⃣read A and write to B
			  configure_file(.version TutorialConfig.h)
			  
			  # 5️⃣add executable with a name and source file
			  add_executable(Tutorial tutorial.cxx)
			  
			  # 6️⃣add the include path(headers path)
			  target_include_directories(Tutorial PUBLIC
			                             "${PROJECT_BINARY_DIR}"
			                             )
			  ```
			- 📄`.version`
			  
			  ``` c++
			  #define Tutorial_VERSION_MAJOR @Tutorial_VERSION_MAJOR@
			  #define Tutorial_VERSION_MINOR @Tutorial_VERSION_MINOR@
			  ```
			- 📄`tutorial.cxx`
			  
			  ``` c++
			  //...
			  #include "TutorialConfig.h"
			  
			  int main(int argc, char* argv[])
			  {
			    if (argc < 2) {
			      std::cout << argv[0] << " Version " << Tutorial_VERSION_MAJOR << "."
			                << Tutorial_VERSION_MINOR << std::endl;
			      std::cout << "Usage: " << argv[0] << " number" << std::endl;
			      return 1;
			    }
			  
			    //...
			    return 0;
			  }
			  ```
		- Descriptive Explanation
			- [cmake_minimum_required()](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html#command:cmake_minimum_required) is required.
			- [project()](https://cmake.org/cmake/help/latest/command/project.html#command:project) is required.
			- [add_executable()](https://cmake.org/cmake/help/latest/command/add_executable.html#command:add_executable) is required.
			- [set()](https://cmake.org/cmake/help/latest/command/set.html#command:set) variables values. The syntax is `set(<variable> <value>... [PARENT_SCOPE])`
			- [configure_file()](https://cmake.org/cmake/help/latest/command/configure_file.html#command:configure_file) is to copy a file to another location and modify its contents. The syntax is `configure_file(<input> <output>)`. In this case, it reads what's inside `.version` and writes to `TutorialConfig.h`.
			- `#define Tutorial_VERSION_MAJOR @Tutorial_VERSION_MAJOR@` this expression means that
				- you will have a variable called `Tutorial_VERSION_MAJOR` in `.h` file.
				- The value of `Tutorial_VERSION_MAJOR` is read in `.version` file by specifying with the 2 `@` symbols.
			- [target_include_directories()](https://cmake.org/cmake/help/latest/command/target_include_directories.html#command:target_include_directories) is to specify where the executable target should look for include files. The syntax is `target_include_directories(<target>[SYSTEM] [AFTER|BEFORE] <INTERFACE|PUBLIC|PRIVATE> [items1...] [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])`.
	- 📌Creating a Library Recipe(Basic )
	  collapsed:: true
		- 🎯Intent
			- Rather than placing all of the source files in one directory, we can **organize our project with one or more subdirectories.** a.k.a. we can add a new `CMakeLists.txt` file and one or more source files.
			- In the top level `CMakeLists.txt` file, we will use the [add_subdirectory()](https://cmake.org/cmake/help/latest/command/add_subdirectory.html#command:add_subdirectory) command to add the subdirectory to the build.
			- Once the library is created, it is connected to our executable target with [target_include_directories()](https://cmake.org/cmake/help/latest/command/target_include_directories.html#command:target_include_directories) and [target_link_libraries()](https://cmake.org/cmake/help/latest/command/target_link_libraries.html#command:target_link_libraries).
		- File structures overview
			- ```
			  .
			  ├── 📁Step2/
			  │   ├── 📄CMakeLists.txt
			  │   ├── 📄tutorial.cxx
			  │   └── 📁MathFunctions/
			  │       ├── 📄CMakeLists.txt
			  │       ├── 📄MathFunctions.h
			  │       └── 📄MathFunctions.cpp
			  └── 📁Step2_build
			  ```
		- Command Line
			- ``` shell
			  	  cd Step1_build
			  	  cmake ../Step1
			  	  cmake --build .
			  ```
		- Key files overview
			- `📁MathFunctions` folder
				- `📄MathFunctions.h` and `📄MathFunctions.cpp`. Nothing special and they are just function declaration and definition.
				- `CMakeLists.txt`
				  
				  ``` cmake
				  # tell upper CMakeLists.txt that I made a library here.
				  add_library(MathFunctions MathFunctions.cpp)
				  ```
			- `📁Step2` folder
				- `📄tutorial.cxx`  It `#include` the header file of the library. Like so `#include "MathFunctions.h"`.
				- `📄CMakeLists.txt`
				  
				  ``` cmake
				  cmake_minimum_required(VERSION 3.10)
				  project(Tutorial VERSION 1.0)
				  
				  # tell current CMakeLists.txt to add a subdirectory
				  add_subdirectory(./MathFunctions)
				  
				  add_executable(Tutorial tutorial.cxx)
				  
				  # link current project with library
				  target_link_libraries(Tutorial PUBLIC MathFunctions)
				  
				  # tell where the `include` folder is
				  target_include_directories(Tutorial PUBLIC
				                             "${PROJECT_BINARY_DIR}"
				                             "${PROJECT_SOURCE_DIR}/MathFunctions")
				  
				  ```
		- Descriptive Explanation
			- `📁MathFunctions` folder
				- `📄CMakeLists.txt` merely tells upper `CMakeLists.txt` that here is a library. The syntax of [add_library()](https://cmake.org/cmake/help/latest/command/add_library.html#command:add_library) command is that `add_library(<name> [STATIC | SHARED | MODULE] [EXCLUDE_FROM_ALL] [<source>...])`. In this case, the 1st argument `MathFunctions` is the name of this library and the 2nd argument is the source files of it.
			- `📁Step2` folder
				- `📄CMakeLists.txt` is the upper level `cmake` file.
					- [add_subdirectory()](https://cmake.org/cmake/help/latest/command/add_subdirectory.html#command:add_subdirectory) tells here is another `cmake` folder.
					- [target_link_libraries()](https://cmake.org/cmake/help/latest/command/target_link_libraries.html#command:target_link_libraries) tells linking a given target and/or its **dependents**.
					- [target_include_directories()](https://cmake.org/cmake/help/latest/command/target_include_directories.html#command:target_include_directories) tells adding the include directories to a target.
	- 📌Creating a Library Recipe(adding options)
		-
- 💫Operation
	- Specifying the C++ Standard
		- [CMAKE_CXX_STANDARD](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD.html#variable:CMAKE_CXX_STANDARD)
		- [CMAKE_CXX_STANDARD_REQUIRED](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD_REQUIRED.html#variable:CMAKE_CXX_STANDARD_REQUIRED)
	- [set()](https://cmake.org/cmake/help/latest/command/set.html#command:set)
		- 📝Description: set variables values
		- ⌨Syntax: `set(<variable> <value>... [PARENT_SCOPE])`
		- 🥚Example: `set(CMAKE_CXX_STANDARD 11)`
	- [option()](https://cmake.org/cmake/help/latest/command/option.html#command:option)
		- 📝Description: Provide a boolean option that the user can optionally select.
		- ⌨Syntax: `option(<variable> "<help_text>" [value])`
		- 🥚Example: `option(USE_MYMATH "Use tutorial provided math implementation" ON)`
	- [list()](https://cmake.org/cmake/help/latest/command/list.html#command:list)
		- 📝Description: List operations. There are many different styles and reading the doc is preferred.
		- ⌨Syntax: `list(<sub-command> <list> ...)`
		- 🥚Example:
- ⌨Sample Code
	- essential `CMakeLists.txt`
		- This is the minimum set up for `CMake`.
		  ``` cmake
		  # 1️⃣specify version
		  cmake_minimum_required(VERSION 3.10)
		  
		  # 2️⃣specify the name of this project
		  project(Tutorial)
		  
		  # 3️⃣specify the name of the executable and source file.
		  # note: the preceding "Tutorial" is the name of the project.
		  # note: the following "Tutorial" is the name of the executable.
		  add_executable(Tutorial tutorial.cxx)
		  ```
- 🧱Structure
	- Typical File Structures
		- ``` 
		  .
		  ├── 📁Step1/
		  │   ├── 📄CMakeLists.txt
		  │   └── 📄tutorial.cxx
		  └── 📁Step1_build
		  ```
		- ``` 
		  .
		  └── 📁Step1/
		      ├── 📄CMakeLists.txt
		      ├── 📄tutorial.cxx
		      └── 📁build
		  ```
- TODO CMake tutorial
	- DONE archive and doc [exercise 3](https://cmake.org/cmake/help/latest/guide/tutorial/A%20Basic%20Starting%20Point.html#exercise-3-adding-a-version-number-and-configured-header-file)
	-