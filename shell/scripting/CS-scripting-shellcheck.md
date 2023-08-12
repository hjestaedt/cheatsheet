# shellcheck

##### config file
```bash
# $HOME/.shellcheckrc or /path/to/project/.shellcheckrc
shell=bash
disable=SC2068,SC1000
enable=check-unassigned-uppercase
```

##### cli

###### set shell dialect (sh, bash, ...)
```bash
shellcheck -s sh /path/to/file
```

###### disable errors in specific run
```bash
shellcheck -e SC2068 /path/to/file
```

###### enable optional checks in specific run
```bash
shellcheck -o check-unassigned-uppercase /path/to/file
```

###### check sources scripts
```bash
shellcheck --checked-sourced /path/to/file
```

###### output format
```bash
shellcheck --format json /path/to/file
shellcheck --format diff /path/to/file
```

##### script

###### enable optional checks globally
```bash
#!/bin/bash
# shellcheck enable=check-unassigned-uppercase
```

###### disable errors globally
```bash
#!/bin/bash
# shellcheck disable=SC2068,SC1234
```

###### disable errors specifically
```bash
# shellcheck disable=SC2068
echo $FOOBAR
```

###### enable optional checks specifically
```bash
# shellcheck enable=check-unassigned-uppercase
echo $FOOBAR
```

###### set/override shell specifically
```bash
# shellcheck shell=bash
if [ "$a" == "$b" ]; then echo "equal"; fi
```
