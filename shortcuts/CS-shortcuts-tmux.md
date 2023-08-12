---
tags: cheatsheet/shortcuts
---

# tmux

###### __help__
`prefix` `?`

#### __session (shell)__

###### __new session__
`tmux new -s <name>`

###### __list sessions__
`tmux ls`

###### __attach to session__
`tmux attach -t <name>`

###### __kill session__
`tmux kill-session -t <name>`

###### __kill server__
`tmux kill-server`

#### __session (tmux)__

###### __list sessions__
`prefix` `s`

###### __rename session__
`prefix` `$`

###### __detach from session__
`prefix` `d`

#### __window/tab__

###### __create window/tab__
`prefix` `t`

###### __close window/tab__
`prefix` `$` or `ctrl` `d`

###### __go to a window/tab__
`prefix` `0`-`9`

###### __next window/tab__
`prefix` `page up`

###### __previous window/tab__
`prefix` `page down`

###### __rename window/tab__
`prefix` `,`

###### __list windows/tabs__
`prefix` `w`

###### __find window/tab__
`prefix` `f`

#### __pane__

###### __split vertical__
`prefix` `b`

###### __split horizontal__
`prefix` `r`

###### __navigate between panes__
`prefix` `arrow`

###### __resize pane__
`prefix`+`alt`+`arrow`

###### __toggle maximize pane__
`prefix` `z`

###### __toggle sync panes__
`prefix` `a`
