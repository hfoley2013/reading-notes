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

# Lab 33

## 1. changed default auth classes

![Zoom_lebZIO7UZO.png](https://i.imgur.com/jLdX6mT.png)

## 2. changed url pattern to include jwt view

  also added url path refresh 

![Zoom_zA0oVUxNZn.png](https://i.imgur.com/Nh4BjGs.png)

first token is usually short lived, refreshed token typically last longer

two different tokens 

## 3. set DB to default sqlite3

## 4. `python manage.py runserver`

## 5. thunderclient requests to test jwt

![Zoom_6Fi0NxjT8k.png](https://i.imgur.com/n3SiqmW.png)

`127.0.0.1:8000/api/token/` with `{"username" : "admin", "password" : "1234"}` in body

admin superuser must have already existed

set up to only give tokens to users

# gUnicorn

**wsgi** 

-web server gateway interface

does a better job of handling concurrent connections

control “workers” and threads

Dev server looks at code constantly and does code analysis

pip install gunicorn

`gunicorn project.wsgi:application --bind 0.0.0.0:8000 --workers 4` will start server now 

Gunicorn is a pre-fork model server, which means that a master process is started and then a several worker processes are forked from the master. The worker processes are responsible for handling requests and returning a response to the client.

application is defined in wsgi file 

0.0.0.0 refers to any local IP on system (container or system)

![pycharm64_IyhKwWhvxe.png](https://i.imgur.com/DMpBjEu.png)

## Whitenoise

- stores static files so the styles are correct when using gunicorn

- middle ware (software that software uses)

- needs to go below django security middleware

- order of django middleware strings matters


![directly underneath .SecurityMiddleware](https://i.imgur.com/LrCIXnd.png)


1. added to middleware in settings.py - directly underneath .SecurityMiddleware
2. added `STATIC_ROOT = BASE_DIR / “staticfiles”`
3. `python [manage.py](http://manage.py) collectstatic`
    
    - collectstatic is builtin to django and whitenoise augments it
    

## launch in docker

change `docker-compose.yml`  line 16 (command section of web section of services) to `gunicorn project.wsgi:application --bind 0.0.0.0:8000 --workers 4`

![pycharm64_z2w45Ra4No.png](https://i.imgur.com/XDs5KCU.png)

1. rebuild docker 

`docker compose up --build`

2. enter bash terminal of docker container
3. Not sure about next steps wasn't paying perfect attention but I think:
5. `docker-compose run web python manage.py migrate`
6. `docker-compose run web python manage.py createsuperuser`
7. potentially have to restart the server? with `gunicorn project.wsgi:application --bind 0.0.0.0:8000 --workers 4`
