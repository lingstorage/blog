---
tags: ['Git']
---
# Git Basics

## Terminology
|     |     |
| --- | --- |
| repository | A directory where version control is managed by git | 
| tracked file | A file whose change is tracked by git | 
| snapshot | The state of tracked files at a given point in time |
| stage | To make created/updated files the candidate of a new snapshot |
| commit (verb) | To create a new snapshot that reflects the changes in staged files |
| commit (noun) | A committed snapshot / an act of committing |
| commit ID | A unique SHA-1 hash assigned to a commit |
| branch | An isolated working place which has its own commit history and can diverge from or merge with another branch <br>(**Technical definition** : A branch is a pointer which refers to a specific commit, and its reference target moves along with each new commit) | 
| master branch | The default branch which is automatically created when the first commit is created |


## Git commands

|     |     |
| --- | --- |
| git init | initialize the working directory to use it as a git repository | 
| git config --global user.name "your name" | set your username for commits | 
| git config --global user.email "email@example.com" | set your email address for commits | 
| git config user.name | view your username | 
| git config user.email | view your email address | 
| &nbsp; | &nbsp; |
| git add <font color="grey">apple.html pen.html</font> | stage <font color="grey">apple.html</font> and <font color="grey">pen.html</font> (and make them *tracked files* if they are not yet) |
| git reset | unstage all staged files |
| git reset <font color="grey">apple.html pen.html</font> | unstage <font color="grey">apple.html</font> and <font color="grey">pen.html</font> |
| git status | view the following information <br> &nbsp;&nbsp;&nbsp; - a list of untracked files <br> &nbsp;&nbsp;&nbsp; - a list of unstaged tracked files updated from the last commit <br> &nbsp;&nbsp;&nbsp; - a list of staged files |
| git commit | commit with the staged files |
| git commit -a | stage all *tracked files* and then commit with them | 
| git commit --amend | add staged changes to the most recent commit of the current branch instead of creating a new one (You should not do this for pushed commits) | 
| &nbsp; | &nbsp; |
| git reset --mixed HEAD~1 | undo the last commit without changing the contents of the working directory |
| git revert <font color="grey">\<commit-id\></font> | commit a new snapshot to reverse the changes made in the commit of <font color="grey">\<commit-id\></font> |
| git restore <font color="grey">apple.html</font> | change <font color="grey">apple.html</font> to match the latest commit |
| git clean -f | remove all untracked files from the repository |
| &nbsp; | &nbsp; |
| git log | view commit history in detailed format |
| git log <font color="grey">apple.html</font> | view commit history of <font color="grey">apple.html</font> in detailed format |
| git log --oneline | view commit history in readable format |
| git log --oneline <font color="grey">apple.html</font> | view commit history of <font color="grey">apple.html</font> in readable format |
| &nbsp; | &nbsp; |
| git tag -a <font color="grey">v1.0</font> | tag the latest commit with <font color="grey">v1.0</font> |
| git tag -a <font color="grey">v1.0</font> <font color="grey">\<commit-id\></font> | tag the commit of <font color="grey">\<commit-id\></font> with <font color="grey">v1.0</font> |
| git tag -d <font color="grey">v1.0</font> | remove the tag of <font color="grey">v1.0</font> from commit history |
| git tag -n3 | view a list of existing tags along with the first 3 lines of the descriptive message of each |
| &nbsp; | &nbsp; |
| git branch | list the existing branches |
| git branch <font color="grey">ppap</font> | create <font color="grey">ppap</font> branch which refers to the commit of the current branch |
| git branch -d <font color="grey">ppap</font> | delete <font color="grey">ppap</font> branch |
| git checkout <font color="grey">ppap</font> | switch to <font color="grey">ppap</font> branch : load the commit of <font color="grey">ppap</font> branch into the working directory |
| git checkout <font color="grey">master</font> | switch to <font color="grey">master</font> branch : load the commit of <font color="grey">master</font> branch into the working directory |
| git checkout <font color="grey">\<commit-id\></font> | switch to *unnamed* branch whose commit ID is <font color="grey">\<commit-id\></font> : load the commit of <font color="grey">\<commit-id\></font> into the working directory|
| git merge <font color="grey">ppap</font> | merge <font color="grey">ppap</font> branch with the current branch | 
| git rebase -i <font color="grey">ppap</font> | move the base commit of the current branch to <font color="grey">ppap</font> branch | 
| git log <font color="grey">master</font>..<font color="grey">ppap</font> | display all commits contained in <font color="grey">ppap</font> branch that aren't in <font color="grey">master</font> branch |
| &nbsp; | &nbsp; |