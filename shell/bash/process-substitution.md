# process substitution

###### __disable posix compatibility to use process substitution__
```bash
set +o posix
```

###### __output - write stdout to named pipe (FIFO)__
```bash
command <(command-list)
echo <(command-list)	# /dev/fd/XX
```

###### __input - read stdin from named pipe (FIFO)__
```bash
command >(command-list)
```

###### __examples__
```bash
# output
sed -f <(var1='test' envsubst '$var1' < sed-script.sed) file
diff <(sort file1) <(sort file2)

# input
tar -cf >(ssh remote-host tar xf -) .	 # archive, copy to remote and unarchive in parallel
tee >(wc -l >&2) < file | gzip > file.gz # count lines and compress file in parallel
```
