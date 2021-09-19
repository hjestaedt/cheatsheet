# seq

###### __1 to 6__
```bash
seq 6
```

###### __6 to 12__
```bash
seq 6 12
```

###### __0 to 20 incrementing by 2__
```bash
seq 0 2 20
```

###### __backward__
```bash
seq 20 -2 0
```

###### __decimals__
```bash
seq 0 0.5 10
```

###### __seperator__
```bash
seq -s: 0 10
```

###### __format string__
```bash
seq -f "file%02g" 0 10
```

###### __zero padding__
```bash
seq -w 0 5 100
```

###### __piping into bc__
```bash
seq -s* 6 | bc # 1*2*3*4*5*6 = 720
```

###### __creating files__
```bash
touch $(seq -f "file-%g.txt" 1 10)
```

###### __in loops__
```bash
for i in $(seq 0 0.5 10); do echo $i; done
```
