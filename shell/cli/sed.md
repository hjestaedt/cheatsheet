# sed

###### __general usage__
```bash
sed 'instruction' <input
sed 'instruction1; instruction2' <input
sed -e 'instruction1' -e 'instruction2' <input
sed -f instruction-file <input					# instructions from file
sed -e 'instruction' -f instruction-file <input	# instructions from arg and file
sed -i 'instruction' <input						# in file editing
sed -i'.backup' 'instruction' <input			# in file editing with backup
sed -n	'instructions' <input 					# disable auto print
sed -s 'instructions' file1 file2 				# restart stream with each file
```

###### __addressing__
```bash
sed '5a text' <input				# append line after line 5
sed '10,13d' <input					# delete lines 10-13
sed '0,5!s/pattern/text/g' <input	# substitute all matches except for line 0-5
sed '/pattern/i text' <input		# insert line before matching line
sed '/pattern/!i text' <input		# insert line before all lines not matching
sed '/p1/,/p2/c text' <input		# replace lines matching p1 to p2 with text
sed '10,/pattern/d' <input			# delete lines from line 10 to matching line
sed '/pattern/,+5p' <input			# print matching line plus next 5 lines
sed '0~25r file' <input				# append content of file to each 25th line
sed '10,+80y/ab/AB/' <input 		# replace characters from line 10 to 90
sed -n '$p' <input 					# print last line
```

###### __a - append line after matching line__
```bash
sed '/pattern/a text'
```
                                                   
###### __i - insert line before matching line__
```bash
sed '/pattern/i text' <input
```

###### __r - append file content after matching line__
```bash
sed '/pattern/r filename' <input
```

###### __c - replace matching line__
```bash
sed '/pattern/c text' <input
```

###### __d - delete matching line__
```bash
sed '/pattern/d' <input
```

###### __s - substitute matching line__
```bash
sed 's/pattern/text/' <input		# 1st match
sed 's/pattern/text/g' <input		# all matches
sed 's/pattern/text/3' <input		# 3rd match
sed -n 's/pattern/test/p' <input 	# print matching line
```

###### __y - substitute characters on current line__
```bash
sed 'y/abc/ABC/' <input
```

###### __p - print matching line__
```bash
sed -n '/pattern/p' <input
```

###### __e - execute matching line as command (and replace)__
```bash
sed '/pattern/e' <input
```

###### __w - write macthing line to file__
```bash
sed '/pattern/w file' <input
```

###### __grouping commands__
```bash
sed '1,5{ /^$/d ; s/pattern/text/ }; 10,15{ s/pattern/text/ }' <input
```

###### __use extended regex__
```bash
sed -r 's/  s+//g' <input
```

###### __reference match pattern &__
```bash
sed 's/[fb]oo/-->&<--/' <input
```

###### __reference match group (1-9)__
```bash
sed 's/  ([a-z]*  ).*/  1/' <input
```

###### __custom separators__
```bash
sed 's_pattern_text_' <input
sed 's:/path:/new/path:' <input
```

###### __print line numbers__
```bash
sed '/pattern/=' <input
```

###### __instructions from file with variables__
```bash
sed -f <(var1='test' envsubst '$var1' < sed-script.sed) file
```

###### __usefull commands__
```bash
sed 's/^<foo>\(.*\)<\/foo>/\1/' <input		# remove sourrounding xml tag
```
