# bash vi-mode

#### __move__

###### __move cursor (left, down, up, right)__
`h` `j` `k` `l`

###### __move to beginning / end of line__
`0` / `$`

###### __move to first non-whitespace character of line__
`^`

###### __move to end of current word / WORD__
`e` / `E`

###### __move beginning of current word / WORD__
`b` / `B`

###### __move to beginning of next word / WORD__
`w` / `W`

###### __move to 0 / n-th column__
`|` / `n |`

###### __move cursor before next / previous occourance of `c` (character)__
`f c` | `F c`

###### __move cursor one character before next / previous occourance `c` (character)__
`t c` | `T c`

#### __insert__

###### __insert before / after cursor__
`i` / `a`

###### __insert at the beginning / end of line__
`I` / `A`

#### __replace__

###### __replace single / multiple character at cursor__
`r` / `R`

#### __delete__

###### __delete single character left / right from cursor__
`X` / `x`

###### __delete word / cursor to end / cursor to beginning__
`dw` / `d$` / `d0` / `..`

###### __delete word / cursor to end / cursor to beginning and go into insert mode__
`cw` / `c$` / `c0` / `..`

###### __delete line__
`dd` or `0d$`

#### __copy / paste__

###### __yank (copy) line / word__
`yy` / `yw` 

###### __paste before / after cursor__
`P` / `p`

#### __misc__

###### __undo last / all actions on line__
`u` / `U`

###### __redo last command__
`.`

###### __search histrory backwards / forwards__
`/` / `?`

###### __repeat search in same / opposite direction__
`n` / `N`

###### __go into vim__
`v`
