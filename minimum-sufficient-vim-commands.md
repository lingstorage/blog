---
tags: ['Vim']
---
# Minimum Sufficient Vim Commands
There are so many Vim commands that I don't want to remember all of them. So I tried to define the minimum sufficient commands to reduce my memory load.<br>
In order to achieve that, I even excluded some of well-known and popular commands (e.g. s command) from the list because the effect of them can be easily produced by combining 2 or 3 of other commands (e.g. An alternative command of 's' is 'cl'). <br>
Because I'm a beginner in Vim, I might add or delete commands as I'm learning through experience. 
<br><br>


## Manipulate file/buffer/window

| cmd | effect |
| --- | --- |
| :e {file-name} | Open {file-name} (= Read the file into a buffer) |
| :w | save the file (= write the contents of the buffer to the file) |
| :w {file-name} | save the file as {file-name} |
| :wq | save the file and close the window |
| :q! | close the window without saving the file |
| &nbsp; | &nbsp; |
| :ls | list all open buffers |
| :b {buffer-name} | display the contents of {buffer-name} in the window |
| ctrl-^ | toggle between the current(%) and alternate(#) buffers |
| &nbsp; | &nbsp; |
| ctrl-w,s| split the window horizontally |
| ctrl-w,v| split the window vertically |


## Change mode

| cmd | effect |
| --- | --- |
| ctrl-[ | enable NORMAL mode |
| i | enable INSERT mode to insert text before the cursor |
| a | enable INSERT mode to insert text after the cursor |
| shift-i | enable INSERT mode to insert text at the start of the current line|
| shift-a | enable INSERT mode to insert text at the end of the current line|
| o | enable INSERT mode opening a new line below the current line |
| shift-o | enable INSERT mode opening a new line above the current line |
| v | enable character-wise VISUAL mode |
| shift-v| enable line-wise VISUAL mode |
| ctrl-v| enable block-wise VISUAL mode |


## Move cursor

| cmd | effect |
| --- | --- |
| l | move to the right |
| h | move to the left |
| j | move down one line |
| k | move up one line |
| &nbsp; | &nbsp; |
| w | move forward to the start of the word |
| e | move forward to the end of the word |
| b | move backward to the start of the word |
| &nbsp; | &nbsp; |
| 0 | move to the start of the current line |
| $ | move to the end of the current line |
| &nbsp; | &nbsp; |
| f{x} | move forward to the character {x} in the current line |
| ; | repeat the last f{x} in the same direction |
| , | repeat the last f{x} in the opposite direction |
| &nbsp; | &nbsp; |
| ctrl-w,l| move to the right window |
| ctrl-w,h| move to the left window |
| ctrl-w,j| move to the window bellow |
| ctrl-w,k| move to the window above |


## Make cursor jump

| cmd | effect |
| --- | --- |
| gg | jump to the first line of the file |
| shift-g | jump to the last line of the file |
| {n}gg | jump to the line {n} |
| &nbsp; | &nbsp; |
| shift-h | jump to the top of the screen |
| shift-m | jump to the middle of the screen |
| shift-l | jump to the bottom of the screen |
| &nbsp; | &nbsp; |
| /{pattern} | search for {pattern} with the default case sensitivity |
| /{pattern}\c | case-insensitive search for {pattern} |
| /{pattern}\C | case-sensitive search for {pattern} |
| \* | search for the word under the cursor |
| n | repeat the last search in the same direction |
| shift-n | repeat the last search in the opposite direction |
| &nbsp; | &nbsp; |
| % | jump to the matching bracket (e.g. Jump from '{' to '}') |
| `. | jump to the location of the last change |
| &nbsp; | &nbsp; |
| ctrl-o | undo jump |
| ctrl-i | redo jump |


## Delete & Yank & Put (Cut & Copy & Paste)

| cmd | effect |
| --- | --- |
| x | delete the character under the cursor |
| shift-j | delete the EOL of the current line |
| &nbsp; | &nbsp; |
| d | delete the selected region in VISUAL mode |
| dd | delete the current line |
| diw | delete the word under the cursor |
| daw | delete the word under the cursor and the spaces after or before it |
| d{motion} | delete the region specified by {motion} |
| &nbsp; | &nbsp; |
| c | 'd' and enable INSERT mode |
| cc | 'dd' and enable INSERT mode |
| ciw | 'diw' and enable INSERT mode |
| caw | 'daw' and enable INSERT mode |
| c{motion} | 'd{motion}' and enable INSERT mode |
| &nbsp; | &nbsp; |
| y | yank the selected region in VISUAL mode |
| yy | yank the current line |
| yiw | yank the word under the cursor |
| yaw | yank the word under the cursor and the spaces after or before it |
| y{motion} | yank the region specified by {motion} |
| &nbsp; | &nbsp; |
| p | put the yanked text after the cursor |
| shift-p | put the yanked text before the cursor |


## Other
| cmd | effect |
| --- | --- |
| ctrl-[ | cancel a partially completed command |
| . | repeat the last change |
| u | undo |
| ctrl-r | redo |
| ctrl-p/n | autocomplete the partially typed word |
| \> | add indents to each selected line in VISUAL mode. |
| \>\> | add a indent to the current line. |
| guiw | convert the word under the cursor to lowercase |
| gu{motion} | convert the region specified by {motion} to lowercase |
| gUiw | convert the word under the cursor to uppercase |
| gU{motion} | convert the region specified by {motion} to uppercase |
| shift-s{delimiter} | surround the region selected in VISUAL mode with a pair of {delimiter} |
| &nbsp; | &nbsp; |
| ctrl-f | move the screen (and the cursor) down one page |
| ctrl-b | move the screen (and the cursor) up one page |
| zz | move the screen so that the cursor comes to the middle |
| &nbsp; | &nbsp; |
| qm | start recording a macro |
| q | stop recording a macro |
| @m | execute the registered macro |
| &nbsp; | &nbsp; |
| :set smartcase | Make /{pattern} case-sensitive only when {pattern} includes one or more uppercase characters
| :set is | show partial matches for a search |
| :set hls | highlight all search matches |
| :noh | turn off highlighting until the next search |