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

###### __links__
[https://tldp.org/LDP/abs/html/here-docs.html](https://tldp.org/LDP/abs/html/here-docs.html)
