# functions

###### __function definition__
```bash
function foo {
	echo "this is a simple function"
}
```

###### __function definition__
```bash
foo() {
	echo "this is a simple function"
}
```

###### __compact function__
```bash
foo() { echo "this is a compact function"; echo; }
```

###### __exclusively defined function__
```bash
if [ $(id -u) = 0 ]; then
  root_exclusive() { echo "this is an exclusive function (root only)"; }
fi  
```

###### __conditionally defined function__
```bash
[ $(id -u) = 0 ] && amiroot() { echo "i am root"; } || amiroot() { echo "i am not root"; }
```

###### __function with explicit return status__
```bash
foo() { return 0; }
```

###### __function with implicit return status ($? of last command)__
```bash
foo() { echo "this will return 0 as well"; }
```

###### __function with result__
```bash
foo() { echo "result"; }
result=$(foo)
```

###### __function with arguments (starting with 1)__
```bash
foo() {
	local arg1="$1"
    echo "first argument: $arg1"
    echo "other arguments: $2 $3 ..."
}
```

###### __check if arg is passed__
```bash
foo() {
    [ -n "$1" ] || return
}
```

###### __function variables__
```bash
foo() {
    echo "number of function args: $#"
    echo "args (as single string): $*"
    echo "args (as separate strings): $@"
}
```
