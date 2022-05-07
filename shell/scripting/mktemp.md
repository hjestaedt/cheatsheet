# temporary files

###### create a temporary file
```bash
mktemp					# creates file /tmp/tmp.PlxvgEhcsw
mktemp -d				# creates dir /tmp/tmp.1nbcQ2HZPN
mktemp -q /tmp/foobar.XXX		# creates file /tmp/foobar.QVr
mktemp -q --suffix bar /tmp/foo.XXX	# creates file /tmp/foo.WoZbar
```

###### create a temporary file in a script
```bash
# create temporary file
TMP_FILE=$(mktemp --tmpdir=$(pwd))

# clean up file on exit
trap "rm -f $TMP_FILE" EXIT
```
