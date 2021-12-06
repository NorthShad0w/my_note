# vim/neovim

customize vim

neovim config file  \~/.config/nvim/init.vim

look at my github







shortcuts

{% embed url="https://github.com/iggredible/Learn-Vim/blob/master/ch04_vim_grammar.md" %}

```
zo                  open a single fold under the cursor.
zc                  close the fold under the cursor.
zR                  open all folds.
zM                  close all folds.
ctrl + hjkl         move cursor
ctrl+Page up/down   swich between tabs   (vim tabs inconvenient, use tmux)
ctrl w  +  hjkl     swich between splits(windows)

use command in insert mode
ctrl + o
 0 move to the start of current line
 $ move to the end of current line.
 ^ to go to the first non-blank character in a line
 10j / 10k   move the cursor down/up 10 lines
 
```

some interesting commands

```
:colo elflord                    easy to read
:set paste                       copy paste from out

:edit foo.file                   new buffer
:ls/buffers                      list buffers      
:buffer <file name>              swith between buffers can use [tab]
:split/vsplit 
          
```

netrw  Vim's built-in file explorer

```
%    Create a new file
d    Create a new directory
R    Rename a file or directory
D    Delete a file or directory
```

vim-plug

```
PlugInstall
PlugUpdate

coc  and coc extension

Plug 'preservim/nerdtree'
Plug 'ryanoasis/vim-devicons'
```

nerdtree

```
open plugin                     :NERDtree   I mapped it to F2
Use the natural vim navigation keys hjkl to navigate the files.
Press o to open the file in a new buffer or open/close directory.
Press t to open the file in a new tab.
Press i to open the file in a new horizontal split.
Press s to open the file in a new vertical split.
Press p to go to parent directory.
Press r to refresh the current directory.
```





### tricks

* First, I use buffers to store all the required files for the current task. Vim can handle many opened buffers before it starts slowing down. Plus having many buffers opened won't crowd my screen. I am only seeing one buffer (assuming I only have one window) at any time, allowing me to focus on one screen. When I need to go somewhere, I can quickly fly to any open buffer anytime.
* I use multiple windows to view multiple buffers at once, usually when diffing files, reading docs, or following a code flow. I try to keep the number of windows opened to no more than three because my screen will get crowded (I use a small laptop). When I am done, I close any extra windows. Fewer windows means less distractions.
* Instead of tabs, I use [tmux](https://github.com/tmux/tmux/wiki) windows. I usually use multiple tmux windows at once. For example, one tmux window for client-side codes and another for backend codes.
