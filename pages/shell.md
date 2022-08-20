- # 📝Definition
	- In short, **shell** is a type of user interface. It is either **command-line interface (CLI)** or **graphical user interface (GUI)**. This section will mainly on (*CLI*) especially on Bourne Again SHell, or “**bash**” for short.
- # ⌨Frequently Used Commands
	- | Command            | Objective                                       | Example                     |
	  | ------------------ | ----------------------------------------------- | --------------------------- |
	  | `cat`              | catch whatever inside a file                    | `cat hello.txt`             |
	  | `cd`               | change directory                                |                             |
	  | `cp`               | copy a file                                     |                             |
	  | `echo`             | like "echo", it simply prints out its arguments |                             |
	  | `find`             | `find <folder> -name <name> -type <type>`       | `find . -name main -type f` |
	  | `fd`               | shortcut for find(not installed yet)            | `fd "*.py"`                 |
	  | `history`          | list the history of your typed bash commands    |                             |
	  | `ls`               | list all the files in current directory         |                             |
	  | `man`              | manual of something                             | `man rm`                    |
	  | `mkdir`            | make a directory/folder                         |                             |
	  | `mv`               | rename/move a file                              | `mv xx.md yy.md`            |
	  | `pwd`              | present working directory                       |                             |
	  | `rm`               | remove a file                                   |                             |
	  | `rm -r`            | remove all the files recursively                | `rm -r ./img`               |
	  | `rm -rf *`         | remove all the files at the current folder      |                             |
	  | `rmdir`            | remove **EMPTY** folder                         | `rm ./.vscode`              |
	  | `rg`               | R.I.P. grep....:laughing: recursively `grep`    | `rg "import" -t py ~/dev`   |
	  | `tail`             | print the last *n* lines                        | `tail -n3`                  |
	  | `touch`            | create a file                                   | `touch main.cpp`            |
	  | `shellcheck`       | Debug bash file                                 | `shellcheck mcd.sh`         |
	  |                    |                                                 |                             |
	  | `<command> --help` | see the function of this command                | `git --help`                |
	  | `man <command>`    | open the menu of this command                   | `man ls`                    |
	  |                    |                                                 |                             |
	  | `Ctrl+L`           | clean out the shell                             |                             |
- # 📖Basic Knowledge
	- **📌 environment variable(PATH)**
		- All the commands you run in the shell has already been added to the  `environment variable`  in your PC. In Windows, you can search  `edit the system environment variable`  =>  `environment variable..`  => Edit the  `PATH` .
	- **📌 `/` and `\`**
		- A path on the shell is a **delimited** list of directories;
		- on Linux and macOS:
			- > ​	path separated by `/` 
			  >
			  > ​	`/` means the "root"
		- on Windows:
			- > ​	path separated by `\` 
			  >
			  > ​	`C:\` means the "root"
	- **📌 absolute path and relative path**
		- a.**Absolute path** is with full path (literally). e.g.
			- In windows,
				- `C:\Users\Xingxin\AppData\Local\Temp`
			- In Linux and macOS:
				- path starts with `/` is *absolute*
		- b.**Relative path** *takes the advantage of environment variable* to form an absolute path.  e.g.
			- `%USERPROFILE%\AppData\Local\Temp`
	- **📌 `.` , `..` , `~` , `-`   used in path**
		- It is a must to know these 3 symbols for they appear a lot.
			- `.` means current directory, e.g. `cd ./tutorial` change dir to the tutorial folder which under **current** dir.
			- `..` means the parent directory, e.g. `cd ..` change dir to its parent dir.
			- `~` means the **home** directory. e.g. `ssh-add ~/.ssh/id_rsa` add the ssh key in the "*HOME* folder/.ssh/"
			- `-` means the previous directory in the prompt
	- **📌 `-` , `--`  used in command**
		- `-` indicates a flag which **modify** their behavior
		- `--` indicates an options
		- *example*:
			- ```bash
			  ls -l
			  ```
			- The `-l` flag asks the `ls` command to list the files in a *a long listing format*.
		- *example*:
			- ```bash
			  git log --stat
			  ```
			- The `--stat` option indicates the `git` command to show the *statistics* from `git log`.