# Bash

## Redirection of both stdout and stderr
```
cmd >>file.txt 2>&1
```

## Automatically fixes your 'cd [folder]' spelling mistakes
```
shopt -s cdspell
```

## Useful functions
```
function psgrep() { ps axuf | grep -v grep | grep "$@" -i --color=auto; }

function fname() { find . -iname "*$@*"; }
```

## '!!:n' selects the nth argument of the last command
```
  ls file1 file2 file3
  cat !!:1-2  # shows all files and cats only 1 and 2
```

```
  $ echo a b c d
  a b c d
  $ echo !!:2
  echo b
  b
````

### '!!:$' (or '!$') shows the last arg of the last command

```
!!:$  # or: !$
```

An arguably better (and slightly more portable) way to accomplish this is the special variable $_ , which expands to the last argument of the previous command. Since $_ is a variable rather than a history substitution, it still works when there is no command history (e.g. in scripts)

### '!!:n:h'

you can use the head modifier with the '!!' prefix. For example:
```
  $ cp file.txt /some/annoyingly/deep/target/directory/other.txt
  $ cd !$:h
  $ pwd # => /some/annoyingly/deep/target/directory
```

### '!!:n:p' prints the command instead of executing it

once you know that !$ is shorthand for !!:$, it's not a huge leap to reason out that you can use `!-2:$` to get the last argument to the 2nd-to-last command. 
Or `!ls:$` for the last arg to the most recent `ls` command. 

### '!!:n:s/before/after' to do substitutions

We can also do substitution with the :s modifier:
```
  $ echo "foo bar"
  foo bar
  $ echo !!:$:s/bar/baz
  foo baz
  $ echo !?bar?:s/foo/qux
  qux bar
```

## The bell character

When a command is going to take a while, and you want to be notified when done:
```
    $ alias b='echo -e "\a"'
    $ long_running_thing
    ^Z
    $ fg ; b
    [long_running_thing resumes]
```
-e : enable interpretation of backslash escapes

## 'for' loops
```
for i in {1..3}; do echo -e "\a"; sleep 0.1; done
```

## Network

### Monitoring network connections in real time
```
lsof -i
```

### Port forwarding
```
ssh -R 12345:localhost:22 server.com "sleep 1000; exit"
```
* forwards server.com's port 12345 to your local ssh port, even if your machine is not externally visible on the net. 
* After that, on server.com, you can 'ssh localhost -p 12345' and you will log into your machine. 
* 'sleep' avoids getting kicked out from server.com for inactivity
