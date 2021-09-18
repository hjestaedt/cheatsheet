# virtual environment

`# add your virtual environment directory to .gitignore`

###### __create virtual environment__
`apt-get install python3-venv`  
`python3 -m venv /path/to/venv`

###### __activate virtual environment__
`source /path/to/venv/bin/activate`

###### __deactivate virtual environment__
`deactivate`

###### __show installed packages__
`pip list`

###### __install packages__
`pip install flask`

###### __create requirements file__
`pip freeze > /path/to/requirements.txt`

###### __recreate virtual environment__
`python3 -m venv /path/to/venv`  
`pip install -r /path/to/requirements.txt`
