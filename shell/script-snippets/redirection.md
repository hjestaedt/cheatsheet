# redirection

###### __redirect stdout/stderr from within script__
```bash
LOG_FILE="/path/to/logfile"
exec 1> "$LOG_FILE"
exec 2>&1
```

###### __redirect fd3 output to file__
```bash
exec 3>file				# open fd3 input
echo "foobar" >&3		# read from fd3
exec 3>&-				# close fd3
```

###### __redirect fd3 input to file__ 
```bash
exec 3<file				# open fd3 output
read foobar <&3			# write to fd3
exec 3>&-				# close fd3
```

###### __redirect stdin/stdout from/to fd3__
```bash
exec 3<>file			# open file and assign fd 3 to it
read -n 10 <&3      	# read 10 characters from file
echo -n "x" >&3     	# write new character to file
exec 3>&-				# close fd
```

###### __only print to stderr if explicitely wanted__
```bash
exec 3>&2-              # move stderr to fd3 and close fd2
ls -l /foobar           # error not shown
ls -l /foobar 2>&3      # error shown

exec 2>&3-              # restore stderr from sd3 and close fd3
ls -l /foobar			# error shown
ls -l /foobar 2>&3      # invalid file descriptor
```
