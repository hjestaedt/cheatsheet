# here doc

###### __here document to stderr__
```bash
cat >&2 <<EOT
usage: script [-h] [-f] /path/to/file
h - help
f - foobar
EOT
```

###### __ssh session__
```bash
ssh vm-condor <<EOT
echo "local working directory: $PWD"
echo "remote working directory: __$PWD"
uptime
EOT
```

###### __ex session__
```bash
ex file <<EOT
:%s/foobar/boofar/g
:wq
EOT
```

###### __vi session__
```bash
vi file <<EOT
i
foo
bar
^[
:wq
EOT
```

`ctrl` `v` + `esc` generates `^[`
