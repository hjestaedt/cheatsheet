---
tags: cheatsheet/shell/scripting
---

# temporary files

###### create a temporary file
```bash
# create file in /tmp (e.g. /tmp/tmp.PlxvgEhcsw)
mktemp

# create dir in /tmp (e.g. /tmp/tmp.1nbcQ2HZPN)
mktemp -d

# create file with shorter suffix (e.g. /tmp/foobar.QVr)
mktemp /tmp/foobar.XXX

# create file with custom suffix (e.g. /tmp/tmp.GyijQde12a.TEMP)
mktemp --suffix ".TEMP" 

# create file in working directory
mktemp --tmpdir=$(pwd) (e.g. /home/donhogo/tmp.pDCO25UfJu)
```

###### create a temporary file in a script
```bash
# create temporary file
TMP_FILE=$(mktemp --tmpdir=$(pwd))

# clean up file on exit
trap "rm -f $TMP_FILE" EXIT
```
