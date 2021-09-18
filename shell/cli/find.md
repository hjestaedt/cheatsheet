# find

#### __general__

###### __find all below search path__
`find /path/to/search`

###### __find with max depth__
`find . -maxdepth 1`

###### __find with depth range__
`find . -mindepth 2 -maxdepth 2`

###### __find by name__
`find . -name "filename"`

###### __find by name ignoring case__
`find . -iname "filename"`

###### __find by negated option (-not)__
`find . -not -name "filename"`

###### __find logical or__
`find . ( -name "*.pdf" -o -name "*.doc" )`

###### __find logical and__
`find . ( -name "*.pdf" -a -not -name "foobar.pdf" )`

###### __find by regex__
`find . -regex ".*/foo/.*.sh"`

#### __type/empty/hidden__

###### __find by file type__
`find . -type f		# files`  
`find . -type d		# directories`

###### __find empty files__
`find . -type f -empty`

###### __find hidden files__
`find . -type f -name ".*"`

#### __user/group__

###### __find by owner__
`find . -user foobar`

###### __find by group__
`find . -group foobar`

#### __permissions__

###### __find executable files__
`find . -type f -executable`

###### __find by permissions__
`find . -perm 755`

###### __find executable bit set for others__
`find . -perm /a=x`

###### __find with suid set__
`find . -perm /u=s`__
`find . -perm -4000`

###### __find with sgid set__
`find . -perm /g=s`  
`find . -perm -2000`

###### __find with sticky bit set__
`find . -perm -1000`

#### __timestamps__

###### __find modified last 24 hours ago__
`find . -mtime 0`

###### __find modified exactly/more than/less than 7 days ago__
`find . -mtime 7`  
`find . -mtime +7`  
`find . -mtime -7`

###### __find modified between 7 and 14 days ago__
`find . -mtime +7 -mtime -14`

###### __find accessed last 60 seconds__
`find . -amin 1`

###### __find accessed exactly/more than/less than 10 minutes ago__
`find . -amin 10`  
`find . -amin +10`  
`find . -amin -10`

###### __find accessed between 7 and 14 days ago__
`find . -atime +7 -atime -14`

#### __size__

###### __find with size exactly/more than/less than 50MB__
`find . -size 50M`  
`find . -size +50M`  
`find . -size -50M`

#### __execute__

###### __find and execute (one command process per file)__
`find . -exec command {} \;`

###### __find and execute (all files as stdin of command)__
`find . | xargs command`

###### __find and delete__ <span style="color: red; font-size: small;">(always put deletion command at the end of the line!)</span>__
`find . -type f -name "foobar" -delete`  
`find . -type f -name "foobar" -exec rm {} \;`

#### __useful examples__

###### __find files older than 14 days and gzip them__
`find . -mtime +14 -exec gzip {} __;`

###### __find and delete files with access time more than a year ago__
`find . -type f -atime +365 -delete`

###### __find dirs and files by permissions__
`find . -type d -not -perm 700 -o -type f -not -perm 600`

###### __find files which were just modified__
`while true; do find . -type f -mtime -0; done`

###### __fix file/directory permissions__
`find . -type f -perm 0777 -print -exec chmod 644 {} __;`  
`find . -type d -perm 0777 -print -exec chmod 755 {} __;`

###### __size of all files bigger than 1G__
`find . -size +1G -exec du -sh {} \;`
