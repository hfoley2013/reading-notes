# DRF API Permissions & PostgresSQL

* Goal is to combine the Django REST Framework with PostgresSQL project constructed by Adam and add functionality
* Make it run in Docker

## Permissions

* Add permission features to web app

## PostgresSQL

* Install this package
  * `pip install psycopg2-binary`
  * Driver that connects Python to a PostgreSQL DB
  * `psycopg2` is a popular Python adapter for PostgreSQL. It allows Python code to interact with a PostgreSQL database, executing SQL commands and managing transactions. `psycopg2` provides a set of Python functions for accessing and manipulating the data stored in a PostgreSQL database, making it a convenient tool for integrating a Python application with a PostgreSQL database.
* In `settings.py`
  * Change the `DATABASES` section

    ```py
    DATABASES = {
      "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "postgres",
        "USER": "postgres",
        "PASSWORD": "postgres",
        "HOST": "db",
        "PORT": 5432,
      }
    }
    ```

* Use the same `Dockerfile` from yesterday
* Copy over the `docker-compose.yml` file from yesterday and make the following changes:
  * Under `services:`
    * NOTE: The values of the environmental variables need to match what is in your `settings.py`

    ```py
    db:
      image: postgres
      environment:
        - POSTGRES_DB=postgres
        - POSTGRES_USER=postgres
        - POSTGRES_PASSWORD=postgres
    ```

* To run CLI within Docker:
  * `docker-compose run web` needs to be added before the command
  * `docker-compose run web python manage.py makemigrations`
* To shut down Docker
  * `docker-compose down`
  * NOTE: When you shutdown, Postgres will disappear
    * We will later integrate with ElephantSQL to make a persistent database
