- # ⌨Frequent used commands
	- | command | objective | example |
	  |--|--|--|
	  |  `git add <file_name>`  | Add file to staging area |  `git add README.md`  |
	  |  `git add .`  | Add any unstaged files to staging area |  |
	  |  `git add -p <file>`  | Interactively choose hunks of patch |  |
	  |  `git blame`  | see each commit with authors |  |
	  |  `git branch`  | see all the branches |  |
	  |  `git branch <branch_name>`  | create a new branch based on `HEAD`|  `git branch dev`  |
	  |`git branch <new_branch> <base_branch>`|create a new branch based explicitly on `<base_branch>`|you are in `dev`. create a branch based on `master`.  `git branch fix master`|
	  |  `git branch -d <local_branch>`  | Delete local branch if this branch has been merged|  `git branch -d PointDebug`  |
	  |  `git branch -D <local_branch>`| delete local branch even not been merged||
	  |  `git cat-file -p <SHA-1 hash>`  | Visualize data by SHA-1 hash |  |
	  |  `git checkout <file>`  | remove the unstaged changes and back to current stage |  |
	  |  `git checkout <branch>`  | change HEAD to such branch |  `git checkout dev`  |
	  |  `git checkout <commit_guid>`  | change HEAD to such commit |  |
	  |  `git checkout -b <branch>`  | create a new branch and checkout to it |  `git checkout -b dev`  |
	  |  `git checkout -b <new_branch> <base_branch>`| create a new branch and checkout to it (explicit version) |   |
	  |  `git clean -f -d`  | clean all the untracked files and folders |  |
	  |  `git clone <url>`  | clone the repo from url |  |
	  |  `git clone --shallow`  | clone the repo without any history |  |
	  |  `git clone --recursive <url>`  | clone the repo recursively |  |
	  |  `git clone -b <branchname> <remote-repo-url>`  | clone specific branch |  |
	  |  `git commit`  | "Archive and confirm" the changes to the directory |  |
	  |  `git commit -m"<message>"`  | Same with 👆, but with a short message |  `git commit -m"Update README.md"`  |
	  |  `git commit -a -m"<message>"`  |  `-a`  stands for add; combine add and commit |  `git commit -a -m"Update README.md"`  |
	  |  `git commit --amend`  | append current commit with previous commit |  |
	  |  `git config -l`  |  `-l`  stands for listing the detail of config, e.g. user name |  |
	  |  `git diff`  |  |  |
	  |  `git diff --staged`  | compare the un-commit changes with HEAD |  |
	  |  `git diff <file>`  | see diff of file with HEAD |  |
	  |  `git diff <guid> <file>`  | see diff of file between current HEAD and guid |  |
	  |  `git diff <prev_guid> <now_guid> <file>`  | see diff of file between  `previous`  and  `now`  |  |
	  |  `git fetch <remote>`  | fetch the commits from remote to local |  |
	  |  `git help <command>`  | help menu of such command |  `git help commit`  |
	  |  `git init`  | Initialize a git repo |  |
	  |  `git log`  | the log of git history |  |
	  |  `git log --stat`  | the log of git history statistically |  |
	  |  `git log --all --graph --decorate`  | nice diagram of git log |  |
	  |  `git merge <branchX>`  | merge  `branchX`  into current branch |  `git merge origin/master`  |
	  |  `git merge --squash <branch>`|take all the commits from <branch>, squash them into 1 commit|`git merge --squash bugFix`<br>`git commit`|
	  |  `git mv <old_name> <new_name>`  | rename specific file (this has to be commited) |  |
	  |  `git push`  | push commits to remote(already configured remote) |  |
	  |  `git push <remote> <branch>:<branch>`  | push commits to remote |  `git push origin main:main`  |
	  |  `git push <remote> --delete <the_remote_branch>`  | Delete remote branch |  `git push origin --delete PointDebug`  |
	  |  `git pull`  |  `git pull`  = { `git fetch; git merge <remote>/<branch>` } |  |
	  |  `git rm --cached <file>`  | To **stop tracking files** which have already been tracked |  `git rm --cached main.3dm.bak`  |
	  |  `git reset`  | remove all the staged changes, green=>red |  |
	  |  `git reset --hard <commitGuid>`  | Destroy any local modification and reset to such commit |  `git reset --hard 0d1d7fc32`  |
	  |  `git reset HEAD --hard`  | Reset the modified files back to the HEAD |  |
	  |  `git reset --soft HEAD~1`| remove the last commit from current branch with changes stay in working tree||
	  |  `git revert <commit_guid>`  | Reverting undoes a commit by creating a new commit. |  |
	  |  `git show <guid>`  | check specific commit by guid |  `git show 721d6bd`  |
	  |  `git stash`  | hide current untracked changes |  |
	  |  `git stash pop`  | pop out the hidden untracked changes |  |
- # 🍱Regular Procedures
	- ## 🍒Cherry-pick
	  collapsed:: true
		- 📌recipe 1: cherry-pick changes from master to release
		  id:: 634ff98f-2d88-4cbe-a15f-c81bea32d5fa
			- Update master branch to latest change
				- ``` shell
				  git pull origin master
				  ```
			- Pull release branch to local
				- ``` shell
				  git checkout -b release origin/release
				  ```
			- cherry-pick change to release branch from master
				- ``` shell
				  git cherry-pick <commit-guid>
				  ```
				- P.S. the `commit-guid` must exist in `master` branch
			- Push changes to remote git repo
				- ``` shell
				  git push origin release:<name>/<feature>
				  ```
				- The preceding command will create a new branch for pull request
	- ## Clone and Submodule
		- 📌 Setup for recursive clone
		  collapsed:: true
			- You want to combine several dependencies into one project when you work on a macro project.
			- Procedure
				- create a `.gitmodules` in the root of your `git` folder.
				- define **what** `git` repo will be in which **location** of your main folder.
				- 📄`.gitmodules`
				  ```
				  [submodule "<name_of_this_repo"]
				  	path = <location_of_this_submodule>
				  	url = <url_of_this_repo>
				  - //e.g.
				  [submodule "deps/polyscope"]
				  	path = deps/polyscope
				  	url = https://github.com/nzfeng/polyscope.git
				  [submodule "deps/googletest"]
				  	path = deps/googletest
				  	url = https://github.com/google/googletest.git
				  ```
				- Use the following commands to setup.
				  
				  ``` shell
				  git clone <repo_url>
				  git submodule init
				  git submodule update --depth 10
				  ```
		- 🗑Unorganized
			- what do the following mean...
			- ```cmd
			  git submodule add --depth 1 git@gitee.com:shanghai-dajie-robot/pocket_raichu.git submodules/pocket_raichu
			  git config -f .gitmodules submodule.pocket_raichu.shallow true
			  ```
			- ```
			  git config -f .gitmodules submodule.submodules/pocket_raichu.shallow false
			  ```
	- ## Worktree
		- 📝Definition
			- A Git worktree is a linked copy of your Git repository, allowing you to have multiple branches checked out at a time.
		- 📌What you can't do using worktree
			- in `CGAL`
				- checkout at `master` branch
			- in `CGAL_release2022`
				- you can checkout all the branches except `master` branch, and vice versa
		- 📌Make a worktree
			- Suppose you have 2 branches. `main` and `hotfix`, now you are in `hotfix` branch. You want to create a folder for `main`
			- ``` shell
			  git worktree add ~/repo_hotfix main
			  ```
				- which `~/repo_hotfix` is where you want the repo put. `main` is the branch you want the new repo based on.
			- ``` shell
			  git worktree add -b feature_2023 ~/repo_2023 main
			  ```
				- this version is checkout a new branch for the worktree.
	- ## Conflict
		- 📌Solve Cherry-pick conflict
			- Solve the conflicts
				- Find which files are with conflict
				- Open the file with VSCode(my personal preference)
					- Solve the conflicts
					- `git add/rm <pathspec>` the conflict files. You can either `add` or `rm`
				- And then `git cherry-pick --continue`
			- Skip to solve
				- `git cherry-pick --skip`
			- Abort and go back to the state
				- `git cherry-pick --abort`
			-
	- ## Github
		- 📌Setup a Github Access Token
			- 1. Go to the Github account - Developer Setting - Generate Token
			- 2. Git clone an arbitrary repo from your page
			- 3. When the computer request credential, just close it until it appears on the command line for the following info
			     1. `user_name`: the name of your Github account
			     2. `password`: paste your token here
	- ## Merge
		- 📌 How to solve conflicts?
			- Suppose you are on `master`, and you want to merge `new_feature` branch, the conflict is on `main.cpp`. Then you can do:
			- ```bash
			  git merge new_feature
			  ```
			- You will see the feedback from the prompt saying there are conflicts. You open the `main.cpp` which was decorated with some notation from `git` . Here I use VS Code, you can also use Vim.
			- ```bash
			  code main.cpp
			  ```
			- You manually fix the conflicts. Then you should **add it to the staging area**!(because you literally fix it)
			- ```bash
			  git add main.cpp
			  ```
			- Finally you ask `git` to continue the merging job.
			- ```bash
			  git merge --continue
			  ```
- 🧬Related Elements
	- 📌VCSs, Git, Github/Gitlab
		- VCSs = Version control systems (VCSs)
		- Git = **Git** is the de facto standard for version control
		- Github/Gitlab/Gitee = the host of Git Repository
- 🌾Resources
	- `.gitignore` template
		- https://github.com/github/gitignore
	- Software for Git
		- `SourceTree` is a free software managing Git while it provides GUI to interact with Git. Highly recommend! You can download: https://www.sourcetreeapp.com/
	- Book for git
		- https://git-scm.com/book/en/v2
- 📈Diagram
	- TODO Diagram of git concept
- # Basic Concepts
	- Repository
		- In short, a Git *repository*: it is the data  `objects`  and  `references` .
	- Data Model
		- The following mimics the data model in Git in pseudocode.
		- **File**: it is a bunch of bytes
			- ```
			  type blob = array<byte>
			  ```
		- **Directory**: It contains named files and directories
			- ```
			  type tree = map<string, tree | blob>
			  ```
		- **Commit**: It has parents, metadata, and the top-level tree
			- ```
			  type commit = struct 
			  {
			    parents: array<commit>
			    author: string
			    message: string
			    snapshot: tree
			  }
			  ```
		- **Object**: It could be a blob, tree, or commit.
			- ```
			  type object = blob | tree | commit
			  ```
		- **Data Storage**: In Git data store, all objects are **content-addressed** by their [SHA-1 hash](https://en.wikipedia.org/wiki/SHA-1).
			- ```
			  objects = map<string, object>
			  ​
			  def store(object):
			    id = sha1(object)
			    objects[id] = object
			  ​
			  def load(id):
			    return objects[id]
			  ```
		- **References**: They are pointers to commits. Convert *SHA-1 hash* to *human-readable names*.
			- ```
			  references = map<string, string>
			  ​
			  def update_reference(name, id):
			    references[name] = id
			  ​
			  def read_reference(name):
			    return references[name]
			  ​
			  def load_reference(name_or_id):
			    if name_or_id in references:
			        return load(references[name_or_id])
			    else:
			        return load(name_or_id)
			  ```
			- e.g.
				- `HEAD`  is the latest "where we currently are"
				- `master`  refers to a particular snapshot instead of a bunch of hexadecimal string.
	- Merge
		- 📌 Fast-forward and three-way merge
			- Fast-forward: the commit all points to a same parent commit
			  ```
			  o <-- o <-- o <-- o <-- o
			  ```
			- Three-way merge:
				- master and sub no conflicts✔, different file
				- master and sub no conflicts✔, different modification in the same file
				- master and sub conflicts❌
				- ```
				  o <-- o <-- o <-- o <---- o
				              ^            /
				               \          v
				                --- o <-- o
				  ```
	- 📌Snapshots咔嚓
		- Git models the history of a collection of files and folders within some top-level directory as a series of snapshots.
		  ```
		  <root> (tree)
		  |
		  +- foo (tree)
		  |  |
		  |  + bar.txt (blob, contents = "hello world")
		  |
		  +- baz.txt (blob, contents = "git is wonderful")
		  ```
	- 📌Modeling history: relating snapshots
		- In pro words: a history is a **directed acyclic graph (DAG)** of snapshots
		- In human words: each snapshot in Git refers to a set of “parents”, the snapshots that preceded it.
		- ```
		        this is a commit
		              ↑
		  o <-- o <-- o <-- o
		              ^
		               \
		                --- o <-- o
		  new_feature      new_feature + bug_fix
		              ↑               ↗
		  o <-- o <-- o <-- o <---- o
		              ^            /
		               \          v
		                --- o <-- o
		                          ↓
		                       bug_fix
		  ```