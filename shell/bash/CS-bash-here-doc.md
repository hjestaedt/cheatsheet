---
tags: cheatsheet/shell/bash
---

# here doc

###### __basic here document (stdin redirection)__
```bash
cat <<MARKER
	$(date) foobar
MARKER
```

###### __supress parameter and command substitution__
```bash
cat <<'MARKER'
	$(date) foobar
MARKER
```

###### __suppress leading tabs__
```bash
cat <<-MARKER
	$(date) foobar
MARKER
```

###### __write here document to file__
```bash
cat >file <<EOT
	$(date) foobar
EOT
```

###### __assign here document to variable__
```bash
FOOBAR=$(cat <<EOT
        foobar farboo barfoo boofar 
EOT
)
```

##### __examples__

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
ssh remote-host <<EOT
echo "local working directory: $PWD"
echo "remote working directory: \$PWD"
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

```bash
ctrl+v esc generates ^[
```

##### __links__
[https://tldp.org/LDP/abs/html/here-docs.html](https://tldp.org/LDP/abs/html/here-docs.html)
