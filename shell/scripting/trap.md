# trap 

###### list of signals
```bash
$ trap -l
 1) SIGHUP	 2) SIGINT	 3) SIGQUIT	 4) SIGILL	 5) SIGTRAP
 6) SIGABRT	 7) SIGBUS	 8) SIGFPE	 9) SIGKILL	10) SIGUSR1
 ...
 ...
```

###### basic syntax
```bash
trap [action] [signal]
```

###### enable/disable trap
```bash
trap "" SIGINT	# enable trap
# uninterruptable magic bash scripting

trap - SIGINT	# disable trap
# interruptable magic bash scripting
```

###### clean up on any exit (signal or completion)
```bash
TMP_FILE=$(mktemp)
trap "rm -f $TMP_FILE" EXIT

# magic bash scripting
```

###### clean up with function
```bash
function cleanup {
     # cleanup code
}
trap cleanup EXIT

# magic bash scripting
```

###### disable ctrl-c
```bash
function no_ctrlc {
    echo "ctrl-c is disabled"
}
trap no_ctrlc SIGINT

while true; do
    sleep 10
done
```
