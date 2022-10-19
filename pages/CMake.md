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
			  │   ├── 📄TutorialConfig.h.in
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
			  cmake_minimum_required(VERSION 3.10)
			  project(Tutorial VERSION 1.0)
			  
			  set(CMAKE_CXX_STANDARD 11)
			  set(CMAKE_CXX_STANDARD_REQUIRED ON)
			  
			  configure_file(TutorialConfig.h.in TutorialConfig.h)
			  
			  add_executable(Tutorial tutorial.cxx)
			  
			  target_include_directories(Tutorial PUBLIC
			                             "${PROJECT_BINARY_DIR}"
			                             )
			  ```
			- 📄`TutorialConfig.h.in`
			  
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
- 💫Operation
	- [set()](https://cmake.org/cmake/help/latest/command/set.html#command:set) variables values
		- The syntax is `set(<variable> <value>... [PARENT_SCOPE])`
		- e.g.  `set(CMAKE_CXX_STANDARD 11)`
	- Specifying the C++ Standard
		- [CMAKE_CXX_STANDARD](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD.html#variable:CMAKE_CXX_STANDARD)
		- [CMAKE_CXX_STANDARD_REQUIRED](https://cmake.org/cmake/help/latest/variable/CMAKE_CXX_STANDARD_REQUIRED.html#variable:CMAKE_CXX_STANDARD_REQUIRED)
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
	- TODO archive and doc [exercise 3](https://cmake.org/cmake/help/latest/guide/tutorial/A%20Basic%20Starting%20Point.html#exercise-3-adding-a-version-number-and-configured-header-file)