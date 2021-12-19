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
| master | The default branch name which is automatically created when the first commit is created |
| clone | To make a copy of a repository |
| local repository | A copy of a repository |
| origin | The original repository of a local repository |
| remote repository | Another repository connected to a local repository <br> (e.g. *origin* is the default remote repository of a local repository) |
| local branch | A branch in a local repository |
| remote-tracking branch | A branch in a local repository, but separated from local branches, to track changes in a remote repository |
| upstream | A remote-tracking branch associated with a local branch <br> (e.g. the remote-tracking branch called "*origin/master*" is the default upstream of the local *master* branch) |


## Git commands

|     |     |
| --- | --- |
| git init | initialize the working directory to use it as a git repository | 
| git config --global user.name "***your name***" | set your username for commits | 
| git config --global user.email "***email@example.com***" | set your email address for commits | 
| git config user.name | view your username | 
| git config user.email | view your email address | 
| &nbsp; | &nbsp; |
| git add ***apple.html pen.html*** | stage ***apple.html*** and ***pen.html*** (and make them *tracked files* if they are not yet) |
| git reset | unstage all staged files |
| git reset ***apple.html pen.html*** | unstage ***apple.html*** and ***pen.html*** |
| git status | view the following information <br> &nbsp;&nbsp;&nbsp; - a list of untracked files <br> &nbsp;&nbsp;&nbsp; - a list of unstaged tracked files updated from the last commit <br> &nbsp;&nbsp;&nbsp; - a list of staged files |
| git commit | commit with the staged files |
| git commit -a | stage all *tracked files* and then commit with them | 
| git commit --amend | add staged changes to the most recent commit of the current branch instead of creating a new one (You should not do this for pushed commits) | 
| &nbsp; | &nbsp; |
| git reset --mixed HEAD~1 | undo the last commit without changing the contents of the working directory |
| git revert ***<commit-id\>*** | commit a new snapshot to reverse the changes made in the commit of ***<commit-id\>*** |
| git restore ***apple.html*** | change ***apple.html*** to match the latest commit |
| git clean -f | remove all untracked files from the repository |
| &nbsp; | &nbsp; |
| git log | view commit history in detailed format |
| git log ***apple.html*** | view commit history of ***apple.html*** in detailed format |
| git log --oneline | view commit history in readable format |
| git log --oneline ***apple.html*** | view commit history of ***apple.html*** in readable format |
| git reflog | view change history in a local repository — this command is useful when you want to revive commits deleted by *git reset* |
| &nbsp; | &nbsp; |
| git tag -a ***v1.0*** | tag the latest commit with ***v1.0*** |
| git tag -a ***v1.0*** ***<commit-id\>*** | tag the commit of ***<commit-id\>*** with ***v1.0*** |
| git tag -d ***v1.0*** | remove the tag of ***v1.0*** from commit history |
| git tag -n3 | view a list of existing tags along with the first 3 lines of the descriptive message of each |
| &nbsp; | &nbsp; |
| git branch | list the existing branches |
| git branch ***ppap*** | create ***ppap*** branch which refers to the commit of the current branch |
| git branch -d ***ppap*** | delete ***ppap*** branch |
| git checkout ***ppap*** | switch to ***ppap*** branch ; load the commit of ***ppap*** branch into the working directory |
| git checkout ***<commit-id\>*** | switch to *unnamed* branch whose commit ID is ***<commit-id\>*** ; load the commit of ***<commit-id\>*** into the working directory|
| git merge ***ppap*** | merge ***ppap*** branch with the current branch | 
| git rebase -i ***ppap*** | move the base commit of the current branch to ***ppap*** branch | 
| git log ***master***..***ppap*** | display all commits contained in ***ppap*** branch that aren't in ***master*** branch |
| &nbsp; | &nbsp; |
| git clone ***<remote-path\>*** | clone a repository of ***<remote-path\>*** onto the current directory | 
| git remote add ***<remote-name\>*** ***<remote-path\>*** | add a remote repository : connect the current repository to ***<remote-path\>*** and name it ***<remote-name\>*** |
| git remote -v | list all remote repositories |
| git branch -r | list all remote-tracking branches |
| git branch -vv | list all local branches with the upstream name of each |
| git branch --set-upstream-to=***origin***/***ppap*** ***ppap*** | set the remote-tracking branch called ***origin/ppap*** as the upstream of local ***ppap*** branch |
| git fetch ***<remote-name\>*** | update remote-tracking branches for ***<remote-name\>*** | 
| git pull ***<remote-name\>*** | update remote-tracking branches for ***<remote-name\>*** and merge them with associated local branches | 