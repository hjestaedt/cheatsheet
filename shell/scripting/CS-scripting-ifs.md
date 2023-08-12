# IFS (input/internal field separator)

###### print default IFS (whitespace, tab, newline)
```bash
printf '%q\n' "$IFS"
# or
echo -n "$IFS" | od -An -abc
# or
set | grep IFS
```

###### set custom IFS
```bash
IFS=$'\n'   # special character
IFS=':'     # regular character
```

###### set custom IFS and reset to default
```bash
OLD_IFS="$IFS"
IFS=$'\n'

# do magic here

IFS="$OLD_IFS"
```

###### reset IFS to default
```bash
IFS=$' \t\n'
# or
unset IFS
```








