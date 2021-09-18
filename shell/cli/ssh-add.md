# ssh-add

###### __start ssh-agent with x-session (/etc/X11/Xsession.options)__
`use-ssh-agent`

###### __start ssh-agent manuall__
`eval $(ssh-agent)`

###### __list all keys__
`ssh-add -l`

###### __add key__
`ssh-add private-key`

###### __remove key__
`ssh-add -d private-key`

###### __remove all keys__
`ssh-add -D`

###### __lock/unlock agent__
`ssh-add -x	# lock`  
`ssh-add -X	# unlock`
