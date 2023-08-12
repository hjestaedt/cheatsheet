---
tags: cheatsheet/shell/cli
---

# ssh-add

###### __start ssh-agent with x-session (/etc/X11/Xsession.options)__
```bash
use-ssh-agent
```

###### __start ssh-agent manuall__
```bash
eval $(ssh-agent)
```

###### __list all keys__
```bash
ssh-add -l
```

###### __add key__
```bash
ssh-add private-key
```

###### __remove key__
```bash
ssh-add -d private-key
```

###### __remove all keys__
```bash
ssh-add -D
```

###### __lock/unlock agent__
```bash
ssh-add -x	# lock
ssh-add -X	# unlock
```
