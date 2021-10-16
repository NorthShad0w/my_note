# tmux

command

```
If no commands are specified, the new-session command is assumed.

tmux attach -t [target session]
```

shortcuts -- after press C-b 

```
------pane control------
!           Break the current pane out of the window.         
"           Split the current pane into two, top and bottom.  
%           Split the current pane into two, left and right.  
o           Select the next pane in the current window.     ------          **
x           Kill the current pane.
m           Mark the current pane.
M           Clear the marked pane.
q           Briefly display pane indexes.
C+array     Change size                                     ------          **
array       Change current pane.                            ------          **
z           Toggle zoom state of the current pane.(repeat exit)
alt-1 to alt-5  Arrange panes in one of the five preset layouts: even-horizontal, even-vertical, main-horizontal, main-vertical, or tiled.

------window control------
,           Rename the current window.                      ------          **
'           Prompt for a window index to select. (preferred)------          **
w           Choose the current window interactively.        ------          **
0 to 9      Select windows 0 to 9.
n           Change to the next window.
o           Select the next pane in the current window.
p           Change to the previous window.
.           Prompt for an index to move the current window.
&           Kill the current window.
i           Display some information about the current window.


------session control------ 
(           Switch the attached client to the previous session.
)           Switch the attached client to the next session.
$           Rename the current session.
s           Select a new session for the attached client interactively.


------copy and paste------
#           List all paste buffers.
-           Delete the most recently copied buffer of text.
=           Choose which buffer to paste interactively from a list.
[           Enter copy mode to copy text or view the history.
]           Paste the most recently copied buffer of text.
f           Prompt to search for text in open windows.
space       start to select text
enter       select selected text 
C-f         page-down
C-b         page-up


------tmux command prompt------
:           Enter the tmux command prompt.

some basic command:
        split-window / split-window -h


------detach------
D           Choose a client to detach.
d           Detach the current client.


------other------
t           Show the time.
```
