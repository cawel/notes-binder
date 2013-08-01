## Shortcuts I need to remember

^      To the first non-whitespace character of a line.
H      To the first line of the screen.
M      To the middle line of the screen.
L      To the last line of the screen.
C      Change the rest of the current line.
<c-t>  To insert a tab in insert mode
CTRL-[ is equivalent to hitting the Esc ke
x      in NERDTree, this closes the tree you are in


## save as
there are two ways of "SAVE AS" in Vim. Assumed that I'm editing hello.txt.

:w world.txt will write hello.txt's content to the file world.txt while keeping hello.txt as the opened buffer in vim.
:sav world.txt will first write hello.txt's content to the file world.txt, then close buffer hello.txt, finally open world.txt as the current buffer.


## ctags

* <C-]>   To jump to a tag
* <C-t>   To climb back the tree

:ts or :tselect shows the list
:tn or :tnext goes to the next tag in that list
:tp or :tprev goes to the previous tag in that list
:tf or :tfirst goes to the first tag of the list
:tl or :tlast goes to the last tag of the list

If you’re using the Ctrlp plugin for vim, running :CtrlPTag will let you search through your tags file and jump to where tags are defined.


## Questions
toggles paste mode ?
git@github.com:msanders/snipmate.vim.git ?


## Useful plugins
### pathogem.vim
* description: Manage your 'runtimepath' with ease.  In practical terms, pathogen.vim makes it super easy to install plugins and runtime files in their own private directories. 
* source: https://github.com/tpope/vim-pathogen
```:Helptags``` to generate all tags


### vundle.vim
```BundleInstall!```   will fetch all latest versions of vundle-managed plugins


### ctrlp.vim
* source: https://github.com/kien/ctrlp.vim
```:CtrlP``` for a fuzzy search
* useful commands
  * Press <F5> to purge the cache for the current directory to get new files, remove deleted files and apply new ignore options.
  * Press <c-f> and <c-b> to cycle between modes.
  * Press <c-d> to switch to filename only search instead of full path.
  * Press <c-r> to switch to regexp mode.


## tagslist
:TlistToggle              Will bring a pane with all the methods in the current file
Tlist_Close_On_Select=1
Tlist_Exit_OnlyWindow=1
t                         Will open the tag in the current buffer


## tab name completion
<c-p> and then can press ^P or ^N to navigate through the list
^X ^L	whole line completion


## Spell check
set spell
]s    " next spelling mistake
[s    " previous spelling mistake
z=    " bring up a list of suggestions
1z=   " will take the fist correction


## Renaming a file

* Write the file while editing (name is relative to vim's CWD):
```
:w newname
```

* Start editing the new copy:
```
:e#
```

* (Optionally) remove the old copy:
```
:!rm oldname
```