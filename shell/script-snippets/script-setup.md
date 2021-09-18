# script setup

###### __path, directory and name of a script__
```bash
readonly _PATH=$(readlink -f "$0")
readonly _DIR=$(dirname "$_PATH")
readonly _FILENAME=$(basename "$_PATH")
```
