# Docker

## Readings

[Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)
[Django for APIs - Library Website](https://djangoforapis.com/library-website-and-api/)
[Django REST Framework](https://www.django-rest-framework.org/)

### Notes

#### Docker

* What is Docker?
  * A way to deploy Linux Containers
* What are Linux Containers?
  * Containers are isolated from one another and bundle their own software, libraries and configuration files
  * They can communicate with each other through well-defined channels
  * Since all of the containers share the services of a single operating system kernel, they use fewer resources than virtual machines
  * Because Docker containers are lightweight, a single server or virtual machine can run several containers simultaneously
* Docker Images and Containers
  * An image is a snapshot in time of what a project *contains*
  * A container is a running instance of the image
  * Analogy:
    * `Dockerfile`is a recipe for a cake
    * *Image* is a snapshot of the recipe at a given time
    * `docker-compose.yml` says how to make the cake
    * *Container* is the actual baked cake
* Creating a Docker Image
  * Create a project folder
  * Create a `Dockerfile` within that folder
    * `touch Dockerfile`
  * In the `Dockerfile`, write the version of `Python` you want the application to use
    
    ```py
    # Dockerfile
    FROM pythonx.x
    ```
  
  * Run `docker image build .` command to create the image
* Image Layers
  * Image dependencies
  * Each layer of images is immutable, acting like a `git commit`
    * Ensures consistency when two or more developers build the same image
  * Docker caches the steps (layers) in a `Dockerfile` to speed up subsequent builds
    * When a change is made to a step, all steps following it will be executed from scratch

#### Deploying Django inside a Docker Container

1. Create a Dockerfile: A Dockerfile is a script that contains the instructions to build a Docker image.
2. Write the instructions to install Django and its dependencies in the Dockerfile. For example:

```py
FROM python:3.8-slim

RUN pip install django

WORKDIR /app

COPY . /app

RUN django-admin startproject myproject .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

3. Build the Docker image using the Dockerfile. For example:

```py
docker build -t myimage .
```

4. Run the Docker container using the image. For example:

```py
docker run -it -p 8000:8000 myimage
```

5. Verify that the Django project is running inside the container by visiting `http://localhost:8000` in the browser.


### Django/React/PostgreSQL Application

Here is a general checklist for creating a Django Rest Framework API with a React frontend and a PostgreSQL database:

1. Set up the development environment:
    - Install necessary software such as Python, Node.js, npm, and PostgreSQL.
    - Set up a virtual environment for the Django project using tools such as virtualenv or pipenv.

2. Create a Django project:
    - Use Django's command-line interface to create a new Django project.
    - Install the necessary packages, such as Django Rest Framework, psycopg2 (for connecting to PostgreSQL), and any other dependencies using pip.
    - Configure the settings.py file to connect to the PostgreSQL database.

3. Define models:
    - Define the models for the Django application using Django's ORM in the models.py file.
    - Create a database schema for the models using Django's migrations.
    - Set up the PostgreSQL database and create tables for the models using the schema.

4. Create API views:
    - Use Django Rest Framework to create the views for the API in the views.py file.
    - Use the views to manage the CRUD (Create, Read, Update, Delete) operations for the data using generic views or custom views.
    - Configure the serializers.py file to handle the serialization and deserialization of data.

5. Define URLs:
    - Use Django's URL dispatcher to map the API views to URLs in the urls.py file.
    - Define URL patterns for the API views to allow clients to access the API.

6. Create a React project:
    - Use npm to create a new React project.
    - Install necessary packages, such as Axios or Fetch, for making API calls using npm.

7. Build the React frontend:
    - Use React components to build the frontend.
    - Use Axios or Fetch to make API calls to the Django API.
    - Render the data received from the API in the frontend.
    - Implement any necessary UI and UX components to enhance the user experience.

8. Deploy the application:
    - Deploy the Django API and the React frontend to a production environment, such as a web server or cloud platform.
    - Set up the PostgreSQL database on a production server and configure the Django settings.py file to connect to the production database.
    - Ensure that the API and frontend can communicate with each other in the production environment.
    - Test the deployed application to ensure that it is working as expected.
