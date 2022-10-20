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
			- `#define Tutorial_VERSION_MAJOR @Tutorial_VERSION_MAJOR@` this expression means that
				- you will have a variable called `Tutorial_VERSION_MAJOR` in `.h` file.
				- The value of `Tutorial_VERSION_MAJOR` is read in `.version` file by specifying with the 2 `@` symbols.
	- 📌Creating a Library Recipe(Basic )
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
				  
				  # 👇tell current CMakeLists.txt to add a subdirectory
				  add_subdirectory(./MathFunctions)
				  
				  add_executable(Tutorial tutorial.cxx)
				  
				  # 👇link current project with library
				  target_link_libraries(Tutorial PUBLIC MathFunctions)
				  
				  # 👇tell where the `include` folder is
				  target_include_directories(Tutorial PUBLIC
				                             "${PROJECT_BINARY_DIR}"
				                             "${PROJECT_SOURCE_DIR}/MathFunctions")
				  
				  ```
		- Descriptive Explanation
			- `📁MathFunctions` folder
				- `📄CMakeLists.txt` merely tells upper `CMakeLists.txt` that here is a library.
			- `📁Step2` folder
				- `📄CMakeLists.txt` is the upper level `cmake` file.
	- 📌Creating a Library Recipe(adding options)
		- File structures overview
			- ```	  
			  .
			  	  ├── 📁Step2/
			  	  │   ├── 📄CMakeLists.txt
			  	  │   ├── 📄tutorial.cxx
			        │   ├── 📄TutorialConfig.h.in
			  	  │   └── 📁MathFunctions/
			  	  │       ├── 📄CMakeLists.txt
			  	  │       ├── 📄MathFunctions.h
			  	  │       └── 📄MathFunctions.cpp
			  	  └── 📁Step2_build
			  ```
		- Command Line
			- ``` shell
			  cd Step2_build
			  cmake ../Step2 -DUSE_MYMATH=OFF
			  cmake --build .
			  ```
		- Key files overview
			- `📁MathFunctions` folder. Nothing special here. Similar to the last change.
			- `📄CMakeLists.txt`
			  
			  ``` cmake
			  cmake_minimum_required(VERSION 3.10)
			  project(Tutorial VERSION 1.0)
			  
			  # 👇Create a variable MY_MATH using option and set default to ON
			  option(USE_MYMATH "Use tutorial provided math implementation" ON)
			  
			  # 👇configure a header file to pass some of the CMake settings
			  configure_file(TutorialConfig.h.in TutorialConfig.h)
			  
			  # 👇Use list() and APPEND to create a list of optional libraries
			  if(USE_MYMATH)
			    add_subdirectory(MathFunctions)
			    list(APPEND EXTRA_LIBS MathFunctions)
			    list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
			  endif()
			  
			  add_executable(Tutorial tutorial.cxx)
			  
			  # 👇Use target_link_libraries to link the library to our executable
			  target_link_libraries(Tutorial PUBLIC ${EXTRA_LIBS})
			  
			  # 👇This is a classic approach when dealing with many components. We will cover the modern approach in the Step 3 of the tutorial.
			  target_include_directories(Tutorial PUBLIC
			                             ${PROJECT_BINARY_DIR}
			                             ${EXTRA_INCLUDES})
			  
			  ```
			- `📄TutorialConfig.h.in`
			  
			  ``` cmake
			  #cmakedefine USE_MYMATH
			  ```
			- `📄tutorial.cxx`
			  
			  ``` c++
			  // ...
			  #include "TutorialConfig.h"  //👈the `USE_MYMATH` will be written here
			  
			  #ifdef USE_MYMATH
			  #include "MathFunctions.h"
			  #endif
			  
			  int main(int argc, char* argv[])
			  {
			    const double inputValue = std::stod(argv[1]);
			  
			  #ifdef USE_MYMATH
			    const double outputValue = mysqrt(inputValue);
			  #else
			    const double outputValue = sqrt(inputValue);
			  #endif
			    std::cout << "The square root of " << inputValue << " is " << outputValue
			              << std::endl;
			    return 0;
			  }
			  
			  ```
		- Descriptive Explanation
			- `📁MathFunctions`
				- Nothing special here.
			- `📄CMakeLists.txt`
				- The key actions here are twofold: (1)setting and parsing compile option (2)include additional libraries in light of the compile option
				- (1)setting and parsing compile option
					- `option(USE_MYMATH "Use tutorial provided math implementation" ON)` this statement is to create a variable name `USE_MYMATH` and its initial value is `ON`.
					- In `TutorialConfig.h.in`, we `#cmakedefine USE_MYMATH` which merely tells that there is a `cmake` variable called `USE_MYMATH`.
					- `configure_file(TutorialConfig.h.in TutorialConfig.h)` is to copy and modify the values defined in `TutorialConfig.h.in` and applies to `TutorialConfig.h`.
					- When compiling, user can type such command in the shell like `cmake ../Step2 -DUSE_MYMATH=OFF` to specify the variable is `ON` or `OFF`.
				- (2)
					- The code block
					  
					  ``` cmake
					  if(USE_MYMATH)
					    add_subdirectory(MathFunctions)
					    list(APPEND EXTRA_LIBS MathFunctions)
					    list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
					  endif()
					  ```
					  
					  is to say `if(USE_MYMATH)` then we will do the following steps.
					- `add_subdirectory` no need to explain.
					- `list(APPEND EXTRA_LIBS MathFunctions)` is to "append" the `MathFunctions` into the `EXTRA_LIBS`(if it is not created and this statement will initialize it)
					- other codes and self-evident.
			- `📄TutorialConfig.h.in`
				- already explained in previous block.
			- `📄tutorial.cxx`
				- ``` c++
				  #include "TutorialConfig.h"
				  #ifdef USE_MYMATH
				  #include "MathFunctions.h"
				  #endif
				  ```
				- Since `USE_MYMATH` has been written in `TutorialConfig.h` and therefore we can treat it as regular macro.
- 💫Operation
	- Specifying the C++ Standard
		- [CMAKE_CXX_STANDARD](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD.html#variable:CMAKE_CXX_STANDARD)
		- [CMAKE_CXX_STANDARD_REQUIRED](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD_REQUIRED.html#variable:CMAKE_CXX_STANDARD_REQUIRED)
	- [add_library()](https://cmake.org/cmake/help/latest/command/add_library.html#command:add_library)
		- 📝Description: Add a library to the project using the specified source files.
		- ⌨Syntax: `add_library(<name> [STATIC | SHARED | MODULE] [EXCLUDE_FROM_ALL] [<source>...])`
		- 🥚Example: `add_library(MathFunctions MathFunctions.cpp)`   In this case, the 1st argument `MathFunctions` is the name of this library and the 2nd argument is the source files of this library.
	- [add_subdirectory()](https://cmake.org/cmake/help/latest/command/add_subdirectory.html#command:add_subdirectory)
		- 📝Description: Add a subdirectory to the build. It merely tells here is another `cmake` folder.
		- ⌨Syntax: `add_subdirectory(source_dir [binary_dir] [EXCLUDE_FROM_ALL] [SYSTEM])`
		- 🥚Example: `add_subdirectory(MathFunctions)`
		- > ==**Note⚠**==: The 1st argument is `source_dir` but not `project_name`. Therefore`MathFunctions` is the folder name in current folder root. Another proof of this is `add_subdirectory(./MathFunctions)`
	- [cmake_minimum_required()](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html#command:cmake_minimum_required)
	  id:: 6350e8c3-ad24-4b6e-854d-42a506dfd259
		- 📝Description: Require a minimum version of cmake.
		- ⌨Syntax: `cmake_minimum_required(VERSION <min>[...<policy_max>] [FATAL_ERROR])`
		- 🥚Example: `cmake_minimum_required(VERSION 3.10)`
	- [configure_file()](https://cmake.org/cmake/help/latest/command/configure_file.html#command:configure_file)
		- 📝Description: Copy a file to another location and modify its contents.
		- ⌨Syntax: `configure_file(<input> <output> [NO_SOURCE_PERMISSIONS | USE_SOURCE_PERMISSIONS | FILE_PERMISSIONS <permissions>...] [COPYONLY] [ESCAPE_QUOTES] [@ONLY] [NEWLINE_STYLE [UNIX|DOS|WIN32|LF|CRLF] ])`
		- 🥚Example: `configure_file(.version TutorialConfig.h)`   In this case, it reads what's inside `.version` and writes to `TutorialConfig.h`.
	- [list()](https://cmake.org/cmake/help/latest/command/list.html#command:list)
		- 📝Description: List operations. There are many different styles and reading the doc is preferred.
		- ⌨Syntax: `list(<sub-command> <list> ...)`
		- 🥚Example:
	- [option()](https://cmake.org/cmake/help/latest/command/option.html#command:option)
		- 📝Description: Provide a boolean option that the user can optionally select.
		- ⌨Syntax: `option(<variable> "<help_text>" [value])`
		- 🥚Example: `option(USE_MYMATH "Use tutorial provided math implementation" ON)`
	- [set()](https://cmake.org/cmake/help/latest/command/set.html#command:set)
		- 📝Description: set variables values
		- ⌨Syntax: `set(<variable> <value>... [PARENT_SCOPE])`
		- 🥚Example: `set(CMAKE_CXX_STANDARD 11)`
	- [target_link_libraries()](https://cmake.org/cmake/help/latest/command/target_link_libraries.html#command:target_link_libraries)
		- 📝Description: It tells linking a given target and/or its **dependents**.
		- ⌨Syntax: `target_link_libraries(<target> ... <item>... ...)`
		- 🥚Example: `target_link_libraries(Tutorial PUBLIC MathFunctions)`
		- > ==**Note⚠**==: The 1st argument is `<target>` and therefore it is the project name. Not a directory.
	- [target_include_directories()](https://cmake.org/cmake/help/latest/command/target_include_directories.html#command:target_include_directories)
		- 📝Description: Add include directories to a target. It merely tells adding the include directories to a target.
		- ⌨Syntax: `target_include_directories(<target>[SYSTEM] [AFTER|BEFORE] <INTERFACE|PUBLIC|PRIVATE> [items1...] [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])`
		- 🥚Example: `target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}")`
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
	- TODO Step3