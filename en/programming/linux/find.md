# find

## Description
* find -- walk a file hierarchy
* find [-H | -L | -P] [-EXdsx] [-f path] path ... [expression]
* The find utility recursively descends the directory tree for each path listed, evaluating an expression (composed of the ``primaries'' and ``operands'' listed below) in terms of each file in the tree.

## Examples:
### Simple ones
* Print out a list of all the files whose names do not end in .c.
```find / \! -name "*.c" -print
             
* Print out all files which do not have the the ".md" extension
```find . \! -name "*.md"
```find . \! -name *.md

* Idem, but only regular files (i.e. not dir or symlinks)
```find . \! -name "*.md" -type f 

* Idem, but OR with directories
```find . \! -name "*.md" \( -type f -or -type d \)

* Print out all (regular) files which have world (case non-sensitive)
```find . -iname "*world*" -type f

* sudo find / -name '*' -size +1G

### Advanced ones
* Print out a file with exactly 2048 bytes
```find . -size 2048c

* Print out (regular) files (with the md extension) which were changed in the last hour and a half
```find . -ctime -1h30m -regex ".*md" -type f

* do a "ls -lAthF" on each file found (the command is executed from the directory from which find was executed)
```find . -type f -exec ls -lAthF {} \; 

* * do a "ls -lAthF" on each file found (the ls command will be executed from the directory that holds the current file)
```find . -type f -execdir ls -lAthF {} \; 


## Gotchas

* -regex and -name 
There is a difference between 
``` -regex .*world.*
and
``` -name *world*
The -name option will only try to match the *last component of the pathname* (the filename), as opposed to the whole path (e.g. /en/world/my_filename.md)