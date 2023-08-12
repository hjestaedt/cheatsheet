---
tags: cheatsheet/shell/bash
---

# redirection

###### __show file descriptors of current bash session__
```bash
lsof -ap $BASHPID -d 0-9
```

###### __file descriptors__
```bash
0		# stdin  
1		# stdout  
2		# stderr  
3 to 9 	# can be assigned freely
```

###### __redirect stdin to file__
```bash
command 0<file
command <file
```

###### __redirect stdout to file__
```bash
command 1>file
command >file
```

###### __force redirect stdout to existing file (if noclobber is set)__
```bash
command >|file
```

###### __redirect stderr to file__
```bash
command 2>file
```

###### __redirect stderr to stdout__
```bash
command 2>&1
```

###### __redirect stdout to stderr__
```bash
command 1>&2
```

###### __redirect stdout and stderr to seperate files__
```bash
command 1>file-stdout 2>file-stderr
```

###### __redirect stdout and stderr to single file__
```bash
command >file 2>&1
command &>file
```

###### __redirect errors to stdout and stdout to file__
```bash
command 2>&1 >file
```

###### __redirect stderr permanently in scripts__
```bash
exec 2>/dev/null
```

###### __close/disable file descriptor n__
```bash
command n>&-
```

###### __open file descriptor n to read/write from/to file__
```bash
exec n<>file
```

##### __examples__

###### __redirect stdout/stderr from within script__
```bash
LOG_FILE="/path/to/logfile"
exec 1> "$LOG_FILE"
exec 2>&1
```

###### __redirect fd3 output to file__
```bash
exec 3>file                             # open fd3 input
echo "foobar" >&3               # read from fd3
exec 3>&-                               # close fd3
```

###### __redirect fd3 input to file__
```bash
exec 3<file                             # open fd3 output
read foobar <&3                 # write to fd3
exec 3>&-                               # close fd3
```

###### __redirect stdin/stdout from/to fd3__
```bash
exec 3<>file                    # open file and assign fd 3 to it
read -n 10 <&3          # read 10 characters from file
echo -n "x" >&3         # write new character to file
exec 3>&-                               # close fd
```

###### __only print to stderr if explicitely wanted__
```bash
exec 3>&2-              # move stderr to fd3 and close fd2
ls -l /foobar           # error not shown
ls -l /foobar 2>&3      # error shown

exec 2>&3-              # restore stderr from sd3 and close fd3
ls -l /foobar                   # error shown
ls -l /foobar 2>&3      # invalid file descriptor
```


##### __links__
[https://wiki.bash-hackers.org/howto/redirection_tutorial](https://wiki.bash-hackers.org/howto/redirection_tutorial)  
[https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirections](https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirections)  
[https://tldp.org/LDP/abs/html/io-redirection.html](https://tldp.org/LDP/abs/html/io-redirection.html)
