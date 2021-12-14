# script setup

###### __path, directory and name of a script__
```bash
_PATH=$(readlink -f "$0")
_DIR=$(dirname "$_PATH")
_FILENAME=$(basename "$_PATH")
```
