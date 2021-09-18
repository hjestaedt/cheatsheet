# seq

###### __1 to 6__
`seq 6`

###### __6 to 12__
`seq 6 12`

###### __0 to 20 incrementing by 2__
`seq 0 2 20`

###### __backward__
`seq 20 -2 0`

###### __decimals__
`seq 0 0.5 10`

###### __seperator__
`seq -s: 0 10`

###### __format string__
`seq -f "file%02g" 0 10`

###### __zero padding__
`seq -w 0 5 100`

###### __piping into bc__
`seq -s* 6 | bc # 1*2*3*4*5*6 = 720`

###### __creating files__
`touch $(seq -f "file-%g.txt" 1 10)`

###### __in loops__
`for i in $(seq 0 0.5 10); do echo $i; done`
