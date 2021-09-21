# options

###### __useful options__
```bash
-v	# print shell input lines while executed  
-x	# print commands/arguments as executed  
-e	# exit on first error  
-o 	# option-name` set bash options by name
```

###### __enable options in scripts__
```bash
bash -x /path/to/script
#!/bin/bash -e
#!/usr/bin/env -S bash -e
```

###### __enable options__
```bash
set -x
set -o xtrace
shopt -s -o xtrace
```

###### __disable option__
```bash
set +x
set +o xtrace
shopt -u -o xtrace
```

###### __show bash options__
```bash
shopt [option-name]
shopt -o [option-name]
```

###### __links__
[https://tldp.org/LDP/abs/html/options.html#OPTIONSTABLE](https://tldp.org/LDP/abs/html/options.html#OPTIONSTABLE)
