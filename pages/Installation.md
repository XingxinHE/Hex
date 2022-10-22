- CMake
	- Install from Ubuntu
		- First you have to make sure you have already `gcc` which contains `make` command for C binaries.
		- Make sure you installed `OpenSSL` package
		- ```bash
		  sudo apt-get install libssl-dev
		  wget http://www.cmake.org/files/v3.21/cmake-3.21.2.tar.gz
		  tar xzf cmake-3.21.2.tar.gz
		  cd cmake-3.21.2
		  ./configure --prefix=/opt/cmake
		  make  #for compilation
		  sudo make install  
		  /opt/cmake/bin/cmake -version  #check if installed
		  ```
- CUDA, cudnn
	- Install CUDA
		- https://developer.nvidia.com/cuda-downloads
	- Download cudnn
		- https://developer.nvidia.com/cudnn-download-survey
		- (follow the instruction and you should be good)
- GCC
	- Install from Ubuntu
		- ```bash
		  sudo apt update
		  sudo apt install build-essential
		  sudo apt-get install manpages-dev
		  gcc --version  #verified you have already installed
		  ```
	- Install from Windows
		- MSYS2
- oh-my-posh
	- https://learn.microsoft.com/en-us/windows/terminal/tutorials/custom-prompt-setup
- [[Qt]]
	- Download and Install
		- https://www.qt.io/
		- Click option 'Downloads for open sources users'
		- When select download package, MSVC 2019 64-bit
		- After install Add `YOUR_PATH_TO\Qt\6.2.2\msvc2019_64\bin` to Environment Variable
	- Configure in Visual Studio
		- In Visual Studio, 'Extension' - 'Manage Extension' , search and install 'Qt Visual Studio Tools'
		- Reboot Visual Studio
		- In Visual Studio, 'Extension' - 'Qt VS Tool'
		- In 'Version' tab, add the  `C:\Qt\6.2.2\msvc2019_64\bin`  to the path where it is also the location of  `qmake.exe`
		- In 'Legacy Project Format' tab, change 'Ask before checking out files' from  `True`  to  `False`
- vcpkg
	- Download and Install
		- Navigate to `C:\\`
		- Recommend PowerShell for the following procedure
		- `git clone` the repo
		  ```shell
		  git clone https://github.com/microsoft/vcpkg
		  .\vcpkg\bootstrap-vcpkg.bat
		  ```
	- Remove Outdated Packages
		- ```shell
		  C:\vcpkg> .\vcpkg remove --outdated --recurse
		  ```
	- Build Dependency Visual Studio Can Find
		- ```shell
		  C:\vcpkg> .\vcpkg integrate install
		  ```
	- When Something is terribly slow
		- e.g. powershell core, download by yourself, put it in the download folder.
	- Install Default Architecture
		- e.g. Install only `x64`. Make a system variable <u>named:</u> `VCPKG_DEFAULT_TRIPLET`, <u>value</u>: `x64-windows`
	- Install like a Nuget Package
		- ```shell
		  C:\vcpkg> .\vcpkg integrate remove
		  ```
		- Then you can see something like:
		- ```shell
		  Install-Package vcpkg..........
		  ```
		- Copy the command and run it in Nuget Package Manager Command in Visual Studio.
- Vulkan
	- Install Vulkan SDK
		- https://vulkan.lunarg.com/sdk/home#windows
	- Vulkan Driver
		- It is already inside Nvidia Driver.
		- https://www.nvidia.com/Download/index.aspx?lang=en-us