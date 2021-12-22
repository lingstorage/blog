---
tags: ['Git']
---
# Git Basics

## Terminology
|     |     |
| --- | --- |
| repository | A directory where version control is managed by git | 
| working tree | A working directory where you edit files |
| tracked file | A file whose change is tracked by git | 
| snapshot | The state of tracked files at a given point in time |
| stage | To make created/updated files the candidate of a new snapshot |
| index | A list of staged files |
| commit (verb) | To create a new snapshot that reflects the changes in staged files |
| commit (noun) | A committed snapshot / an act of committing |
| commit ID | A unique SHA-1 hash assigned to a commit |
| branch | A pointer which refers to a specific commit, and its reference target moves along with each new commit | 
| master (or main) | The default branch name which is automatically created when the first commit is created |
| HEAD | The most recent commit of a branch |
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
| git version | display version information about git |
| git init | initialize the current directory to use it as a git repository | 
| git config --global user.name "***your name***" | set your username for commits | 
| git config --global user.email "***email@example.com***" | set your email address for commits | 
| git config user.name | view your username | 
| git config user.email | view your email address | 
| &nbsp; | &nbsp; |
| git add ***apple.html pen.html*** | stage ***apple.html*** and ***pen.html*** (and make them *tracked files* if they are not yet) |
| git add .| stage all files in the working tree (and make them *tracked files* if they are not yet) |
| git reset | unstage all staged files |
| git reset ***apple.html pen.html*** | unstage ***apple.html*** and ***pen.html*** |
| git status | view the following information <br> &nbsp;&nbsp;&nbsp; - a list of untracked files <br> &nbsp;&nbsp;&nbsp; - a list of unstaged tracked files updated from the last commit <br> &nbsp;&nbsp;&nbsp; - a list of staged files (= index) |
| git commit | commit staged files |
| git commit -a | stage all *tracked files* and then commit with them | 
| git commit --amend | add staged changes to the most recent commit instead of creating a new one (You should not do this for pushed commits) | 
| &nbsp; | &nbsp; |
| git reset --mixed HEAD~1 | undo the last commit without changing the contents of the working tree |
| git revert ***<commit-id\>*** | commit a new snapshot to reverse the changes made in the commit of ***<commit-id\>*** |
| git restore --source ***<commit-id\>*** ***apple.html*** | change ***apple.html*** to match the commit of ***<commit-id\>*** |
| git clean -f | remove all untracked files from the repository |
| &nbsp; | &nbsp; |
| git log | view commit history in detailed format |
| git log ***apple.html*** | view commit history of ***apple.html*** in detailed format |
| git log --oneline | view commit history in readable format |
| git log --oneline ***apple.html*** | view commit history of ***apple.html*** in readable format |
| git reflog | view change history in a local repository — this command is useful when you want to revive commits deleted by *git reset* |
| git blame ***apple.html*** | show who last modified each line of ***apple.html*** |
| &nbsp; | &nbsp; |
| git tag -a ***v1.0*** | tag the latest commit with ***v1.0*** |
| git tag -a ***v1.0*** ***<commit-id\>*** | tag the commit of ***<commit-id\>*** with ***v1.0*** |
| git tag -d ***v1.0*** | remove the tag of ***v1.0*** from commit history |
| git tag -n3 | view a list of existing tags along with the first 3 lines of the descriptive message of each |
| &nbsp; | &nbsp; |
| git branch | list all local branches |
| git branch ***ppap*** | create ***ppap*** branch which refers to the commit of the current branch |
| git branch -d ***ppap*** | delete ***ppap*** branch |
| git branch -m ***old-name*** ***new-name***| rename a branch from ***old-name*** to ***new-name*** |
| git checkout ***ppap*** | switch to ***ppap*** branch and load the last commit of it into the working tree |
| git checkout ***<commit-id\>*** | switch to *unnamed* branch which refers to ***<commit-id\>*** and load the last commit of it into the working tree |
| git merge ***ppap*** | merge ***ppap*** branch with the current branch | 
| git rebase -i ***ppap*** | squeeze commits which only exist in ***ppap*** branch into the current branch after the last commit which is shared between them | 
| git rebase --continue | restart the rebasing process after editing a commit |
| git rebase --abort | abandon the current rebasing process |
| git log ***master***..***ppap*** | display all commits contained in ***ppap*** branch that aren't in ***master*** branch |
| &nbsp; | &nbsp; |
| git diff | view the difference between the unstaged files and the most recent commit in the current branch |
| git diff --cached | view the difference between the staged files and the most recent commit in the current branch |
| git diff ***X***..***Y*** | view the difference between ***X*** and ***Y*** <br> (***X***,***Y***: commit ID or branch name)|
| &nbsp; | &nbsp; |
| git stash | temporarily stash uncommitted changes in the current branch to create a clean working tree |
| git stash pop | retrieve stashed changes |
| &nbsp; | &nbsp; |
| git clone ***<remote-path\>*** | clone a repository of ***<remote-path\>*** onto the current directory | 
| git remote add ***<remote-name\>*** ***<remote-path\>*** | add a remote repository : connect the current repository to ***<remote-path\>*** and name it ***<remote-name\>*** |
| git remote rm ***<remote-name\>*** | remove a remote repository : remove the connection to ***<remote-name\>*** from the current repository |
| git remote -v | list all remote repositories |
| git branch -r | list all remote-tracking branches |
| git branch -vv | list all local branches with the upstream name of each |
| git branch --set-upstream-to=***origin***/***ppap*** ***ppap*** | set the remote-tracking branch called ***origin/ppap*** as the upstream of local ***ppap*** branch |
| git fetch ***origin ppap*** | update the remote-tracking branch named ***origin/ppap*** | 
| git pull ***origin ppap*** | update the remote-tracking branch named ***origin/ppap*** and merge it with the current branch | 
| git pull --rebase ***origin ppap*** | update the remote-tracking branch named ***origin/ppap*** and rebase it into the current branch | 
| git push ***origin ppap*** | merge the current local branch with the remote-tracking branch named ***origin/ppap*** and upload it to the corresponding remote repository |  
| git push -d ***origin ppap*** | delete the remote-tracking branch named ***origin/ppap*** and the one of the corresponding remote repository |  