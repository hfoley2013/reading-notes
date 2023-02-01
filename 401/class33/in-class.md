# In Class Notes

## Production Server

* Use `Gunicorn`
  * `pip install gunicorn`
* Update `requirements.txt`
  * `pip freeze > requirements.txt`
* Use `gunicorn <project_name>.wsgi:application --bind 0.0.0.0:8000 --workers 4`
  * Make sure what follows the `:` matches what you put in your `wsgi.py` file within the project folder
  * `--bind` is used to bind the program to launch to the specified address
  * `--workers` is how many processes that can handle the load of your application
* In `wsgi.py`

```py
import os
from django.c
os.environment
application = 
```

* In `docker-compose.yml`
  * Add the run script for `gunicorn` to the `command` setting
