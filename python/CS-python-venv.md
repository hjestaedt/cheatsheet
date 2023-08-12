---
tags: cheatsheet/python
---

# virtual environment

```bash
# add your virtual environment directory to .gitignore
```

###### __create virtual environment__
```bash
apt-get install python3-venv
python3 -m venv /path/to/venv
```

###### __activate virtual environment__
```bash
source /path/to/venv/bin/activate
```

###### __deactivate virtual environment__
```bash
deactivate
```

###### __show installed packages__
```bash
pip list
```

###### __install packages__
```bash
pip install flask
```

###### __create requirements file__
```bash
pip freeze > /path/to/requirements.txt
```

###### __recreate virtual environment__
```bash
python3 -m venv /path/to/venv
pip install -r /path/to/requirements.txt
```
