---
tags: ['Terminal', 'Shell', 'macOS', 'Darwin', 'Unix']
---
# Note to Self About macOS Terminal

## The difference between Terminal and Unix shell
1. The macOS **Terminal** is an application to provide a text input/output environment for **Unix shells**. <br>
1. A **Unix shell** is a program that provides a command-line user interface to navigate Unix or Unix-like OS.
1. macOS is a Unix variant. So Terminal gives you a way to interact with macOS via a Unix shell.
1. Terminal supports several Unix shells, such as *csh*, *bash*, *zsh*, etc.
1. Technically speaking, it is incorrect to say "Terminal commands" as Terminal doesn't execute commands but just send them to a Unix shell. 
1. **Darwin** is the core of macOS. It is itself a Unix-like operating system and is mainly in charge of the non-graphical portion of macOS. So you'll encounter the term "*Darwin*" from time to time when you use Terminal.
1. Terminal can connect to a Unix shell not only on your computer but also on a different computer over a network.  
<br>

## Special Characters
|     |     |
| --- | --- |
| \* | Zero or more characters |
| ? | Any single character |
| / | The root directory |
| ~ | The home directory |
| . | The working directory |
<br>

## Unix Command Memo
```
% date
```
Display the current date and time. 
<br><br>

```
% echo $PATH
```
Display PATH.
<br><br>

```
% ls -t
```
 List all contents in the current directory ordered by modification time.
<br><br>

```
% ls -S
``` 
 List all contents in the current directory ordered by size.
<br><br>

```
% cd -
```
Move back to the directory you were in before executing the last cd command.
<br><br>

```
% cp -r apple orange fruit
```
Copy apple and orange directories to fruit directory.<br>
(You need -r to copy directory)
<br><br>

```
% cp -r apple/ orange/ fruit
```
Copy all contents (not directories) of apple and orange to fruit.
<br><br>

```
% mv apple orange fruit
% mv apple/ orange/ fruit
```
Move apple and orange directories to fruit directory <br>
(You don't need -r to move directory)
<br><br>

```
% ln -s <path-to-file/directory> fruit
```
Create a symlink to \<path-to-file/directory\> in fruit directory. <br>
(You can delete the symlink by "rm \<symlink-name\>")
<br><br>

```
% find <directory-name> -name <expression>
```
Search inside \<directory-name\>, and display all directories or files which include \<expression\> in its name with full path format. Use *-iname* instead of *-name* to make a case-insensitive search. 
<br><br>

```
% grep -R "apple" .
```
Display all lines of text which contains "apple" string in the current directory.
<br><br>

```
% sudo !!
```
Run the last executed command as the root user. This command is useful when you realize you don't have permission to run the command after you already execute it.
<br><br>

```
% top -o rsize
```
List processes in order of RAM usage.
<br><br>

```
% ps
```
List shell processes.
<br><br>

```
% kill <PID>
``` 
Polite request to terminate the process. You can confirm PID(Process ID) using *top* command.
<br><br>

```
% kill -9 <PID>
```
Strong request to terminate the process. If this command doesn't work, your only choice is to restart the computer. 
<br><br>

```
% exit
```
End the current shell session 
<br><br>

```
% exit <PID>
```
End the running shell whose process ID is \<PID\>. You can confirm PID by *ps* command.
<br><br>

```
% pwd | pbcopy
```
Put the absolute path to the current directory into the clipboard.
<br><br>

```
% ls *.csv | pbcopy
```
Put the list of all csv files in the current directory into the clipboard
<br><br>

```
% ls > tmp.txt
```
Save the output of *ls* command in tmt.txt. If tmp.txt doesn't exist it will be created. 
<br><br>

```
% ls >> tmp.txt
```
Append the output of *ls* command into tmp.txt. If tmp.txt doesn't exist it will be created.
<br><br>

```
% du -sh <directory-name> 
```
Display the disk usage of \<directory-name\>
<br><br>

## Keyboard Shortcuts 
|  command | effect |
| --- | --- |
| cmd-f | Find a command you executed before |
| ^c | Open a new prompt without executing a typed command |
| q or ^c | Stop a running program |
| cmd-↑ | Highlight the previous command |
| cmd-shift-a | Select the output of a command |
| ^r | Search and put a command from your command history |
<br>

## Other
- *cp* commands overwrite an existing file which has the same name without any alert so it is strongly recommended to add -i flag.

- Customizations you make in .zshrc apply only in a shell session; they aren't used by shell scripts!!
