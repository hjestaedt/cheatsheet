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

###### __links__
[https://wiki.bash-hackers.org/howto/redirection_tutorial](https://wiki.bash-hackers.org/howto/redirection_tutorial)  
[https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirections](https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirections)  
[https://tldp.org/LDP/abs/html/io-redirection.html](https://tldp.org/LDP/abs/html/io-redirection.html)
