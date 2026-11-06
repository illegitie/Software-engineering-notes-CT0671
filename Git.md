#version-control
git is a distributed VC system, with some peculiar features compared
to centralized ones:
- saves snapshots of files
- works mostly locally, and rarely pushes content on the server
- it has integrity and it only add files
- a git file may be in three states: modified, staged, committed.
### Snapshots, not diffs
![[snapshots.png]]
- Every time you modify your repo you create a new snapshot
- Every snapshot contains a version on each file in the repo
- If in a certain version a file was not modified, it is a link to prev one
### Most operations are local
- Since the meta-information reside also in a local copy, the dev can do most of the actions locally, without being online
- They can browse the past version and commit new ones without internet access
-  When it goes back online they will push the differences to the server so all the devs can sync their local repo
### Integrity and recovery
- Every version of repo is identified by a hash value computed on the structure and content of repo so you are assured that the contents are not changed, if the hash is not changed.
- git generally always adds data. You can modify the past but hardly you can make something that is not undoable.
- These two features ensures that when you download code, this was not changed:
	- for instance, modified by some internal error or by an attacker that takes over the repository.
	- Still you have the flexibility of doing and undoing whatever you want.
## **Git structure**
A git project is made of three components:
- The working area: this is a folder that contains the files you work on
- The index: a text file that contains all the information on the files that are part of the repository and were modified, but a new version was not already produced.
- A modified file is said to belong to the staging area.
- The repository: a folder that contains the database of the information and meta-information.
When you checkout a git project you will have:
- The working area, a local folder with files. You work on the files as with any other file in your file system.
- A sub-folder named .git which contains configuration files and the repository database (.git/ is not technically part of your working area)
- A file called .git/index which contains the information on which file was modified compared to the last recorded state.
## **Moving objects between sections**
![[git components.png]]
- When you *checkout* a project you will create your working directory and .git folder (the repository). Your index is now empty.
- When you modify a file, your index is automatically updated to reflect the changes.
- When you decide that something you modified will enter the next version, you *stage* it: technically you are only writing into the index that this file will be part of the next release.
- When you *commit* a file, it gets included in the repository, a new version is created.
## **File status**
A file in a git project can be in 4 states:
- *Untracked*: an untracked file is a file that git does not know nothing about. It is a file that is present in your working directory but it is not present in your last commit. If a file is present in the last commit it is a tracked file.
- *(tracked) Unmodified*: this is a tracked file and that was not modified since the last commit.
- *(tracked) Modified*: this is a tracked file that was modified since the last commit.
- *(tracked) Staged*: this is a tracked file that was modified, and you decided that will enter your next commit. When you create the commit, all staged files become Unmodified.
![[file_status.png]]
## **Commits**
- A commit contains meta-data with the author, date etc.
- Each commit also points to blobs, i.e., the compressed data of each file
- A pointer to the previous and next commit (if they exist).
![[commit_chain.png]]
## **Branches**
- A branch in git is a pointer.
- A branch is just a name, a label that is attributed to a commit.
- When a project is created, a branch is also created, the master branch, which points to the most recent commit.
- When you add another commit, the pointer is moved to the next commit.
- The master branch has nothing special, it is just a convention that every project respects.
![[master_branch.png]]
 - You can create as many branches with the git branch command
 - Every time you create a branch, you simply add a label to the commit.
 - You can have multiple branches for the same commit, and you can have as many branches as you want.
- git branch testing will add another branch.
![[branches.png]]
- Now that you have two branches, if you add another commit, which branch will be moved to the next commit?
- You have to decide which is the branch you are currently on.
- To tell which is your current branch, there is another Pointer that is used, the HEAD pointer.
- The HEAD pointer always tells what is the branch you are on.
- You can change from one branch to another with the git checkout command.
### checkout Changes your Working **Directory**
- When you do git checkout you move from one branch to another.
- This means that your working directory changes.
- Literally the files in your working directory will change under your eyes.
- For this reason, when you checkout, you must be in a clean state, no modified files or staged files. If you modified something you will have to commit it before doing a checkout.
### **Branching is good**
- Branching is a key feature of versioning systems
- Every time you want to add a new feature to your software, it is a good practice to make a new branch and work on it in a separate branch.
- But when you are done with your new feature, how do you port it back to the master branch?
- You will have to use git merge
`git checkout -b testing` or `git branch testing && git checkout testing`
`git add .`
`git commit -m "message"`
`git checkout master`
`git merge testing`
## **Remotes Branches**
- Now that we know how to work on a local project, let’s see how we can cooperate with others
- A remote branch is a branch that resides in some remote computer
- git can use several protocols to communicate, and it has a server version that you can install
- Your local project use a remote server to push and pull contents that you share with other developers
- When you create a project from scratch, it initially has no remotes. You can add a remote with git remote add:
	- `$ git remote add origin URL`
	where:
	- *origin* is the name you give to the remote
	- *URL* is the address of the remote.
- Actually, the most common thing is not to create a local project, but to clone an existing project.
- In this case, a remote is added automatically to your local project.
- This remote is called origin.
	- `$ git clone URL`
	- `$ git show remote`
- A remote branch is exactly as a local branch, it’s a label that points to some commit.
- The difference is that a remote branch can not be moved with local actions. You can move it just sending some command to the server.
- You can distinguish a remote branch by its name, which is going to be `<remote>/<branch>`
- When you clone a remote project you clone all its branches locally, but you cannot change them with git commit, you have to use the git push command.
## **Resolving merge conflict**
Assume “index.html“ is to be merged.
- If git is able to merge it without a conflict then OK, the new file is produced,
ready to be used.
- If a conflict is created, then index.html is a “patchwork“ of the possible versions of the file.
- The headers in the file make it unsuitable to be used, it is not valid HTML anymore (or any other language)
It’s up to you to solve the conflict, which is done in two steps:
1. You need to correct the file and remove the headers. When you edit the file, you have to decide what is the correct version of the two, or take pieces from both. The result must be a file with valid code.
2. After you fixed the file, you have to tell git that the conflict has been solved. This is done with git add index.html. That is, if you add the file to staging area again git understands you fixed the conflict.
Only after these two steps you can go on, do a commit with the merged version
and push it.
## **Good practices**
- When you end your coding session, always commit. Push your changes if you are working on a branch that is present also on the remote.
- Use feature branches. If you work on a separate branch you can feel free to commit things even if they are not fully "perfect" and you do not expect other people to work on the same branch. At the end you will have to marge your code, and there, conflicts can emerge. But at least they do not emerge during the development process.
- Before you start working on the code always do `git fetch`, `git merge` (or simply `git pull`). When you modify a file you must be 100% that this is the most up-to-date copy.
- Coordinate with your colleagues. Split the work in different modules if possible and let each one work on a piece of the code
## **Fixing broken things**
- Several times it can happen that you did something wrong, and you want to “change the past”.
- This can be done in two ways, before you commit, or even after you commit with:
	`git stash`
	`git amend`
### git stash
`git stash` helps you cleaning your working directory without losing the work you did.
- In practice, stashing means that:
	- your working copy is rolled back to the last commit
	- the modifications you did are saved in a stack
	- in the future you can re-apply the modifications from the stash
- You can stash more than once and every change-set is saved in the stash itself
- Both the local modifications and the index are saved, so it does not matter if you already staged your changes
### git amend
- If you run git commit --amend right after you did a commit, you will see the default editor and you will be able to change the message of the last commit.
- If instead you change something after the commit (and you stage it), amend will:
	- merge your new modifications in the last commit
	- remove the last commit
	- add a new commit with the current staged content
- If you amend a commit you did not yet push, feel free
- If you want to amend a commit you already pushed, you are changing history for other people also.
- This is generally a bad move, so you must be sure nobody is working on code you are amending .
- So git allows you push a commit that amends a previous commit, but you must use git push -f origin master where -f stands for force. Otherwise git will not allow you.
## **Doomsday Commands: git reset, git rebase**
- it reset allows you to do a lot more things than what I showed
- It allows you to remove commits, make them disappear, and, together with rebase it allows you to change the shape of the commit graph.
- In practice, it allows you to change the past history.
- As long as you do this on your local branches, this is not a big issue
- When you change the history on the server, if someone is working on the code, you may make big damage.
- I am not entering into their details so it’s better if you don’t use these commands unless you are 100% sure.
==🔴Note Well: with reset and rebase you can do actions that can not be undone. You can==
==🔴loose the history of your project, and remember that the history of your project is part==
==🔴of your evaluation. I prefer dummy comments than broken history.==
