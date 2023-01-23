# Django

## Readings

* [Getting Started with Django](https://www.djangoproject.com/start/)
* [How Django Works Behind the Scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)

## References

* [What is Django](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)
* [First Django App - Part 1](https://docs.djangoproject.com/en/4.1/intro/tutorial01/)
* [First Django App - Part 2](https://docs.djangoproject.com/en/4.1/intro/tutorial02/)

## Notes

### What is Django?

* Django is a free and open-source web framework written in Python
* It follows the model-view-controller architectural pattern and is used for developing web applications
* It includes an ORM (Object-Relational Mapper), which allows developers to interact with databases using Python code instead of writing raw SQL
* It also has a built-in administrative interface, which makes it easy to manage the data of a web application

### How Do I Use Django?

* Django can be used to build web applications by following these basic steps:

  * Install Django: You can install Django using pip by running the command `pip install Django` in your command prompt or terminal.
  * Create a project: Once Django is installed, you can create a new project by running the command `django-admin startproject projectname` in your command prompt or terminal. This will create a new directory with the project name and the basic file structure for a Django project.
  * Create a new app: In your project directory, you can create a new app by running the command `python manage.py startapp appname`. This will create a new directory with the app name and the basic file structure for a Django app.
  * Define models: In your app directory, create a `models.py` file. Here you can define the models for your app, which will be used to create the database tables.
  * Create the database: Run the command `python manage.py makemigrations` to create the initial database. Then run `python manage.py migrate` to create the tables in the database.
  * Create views: In your app directory, create a `views.py` file. Here you can define the views for your app, which will handle the logic for displaying the data to the user.
  * Create URLs: In your project directory, open the `urls.py` file. Here you can define the URLs for your app, which will map the URLs to the views.
  * Create Templates: Create a folder named 'templates' inside your app directory. Here you can create HTML files that will be used to render the views.
  * Run the server: Run the command `python manage.py runserver` in your command prompt or terminal to start the development server.
  * Develop your app by adding functionality such as forms, authentication, and other features provided by Django.

### What is a View?

In Django, views are Python functions that handle the logic for a specific web page or section of a web application. They are responsible for processing data from the models and rendering templates in response to a user's request.

A view function takes a request object as its first argument and returns a response object. The request object contains information about the user's request, such as the URL, the data sent in a form, and the user's session. The response object can be a simple text message, an HTML template, or a redirect to another URL.

In a view function, you can perform various tasks such as querying the database, performing calculations, and passing data to a template. The view function can also handle user input, such as form submissions, and handle errors.

Django views are defined in the `views.py` file of an app. You can use the `@app.route()` decorator to map a URL to a view function. When a user requests a URL that matches the one you specified in the decorator, Django will call the corresponding view function and return the response.

It's important to note that views should not contain any presentation logic, it should only handle the logic and data handling, and the templates should handle the presentation, this way your views will be more testable and reusable.

### What are important things to remember about Django?

* **Middleware:** Django uses middleware to process requests and responses. Middleware is a way to modify the request and response objects before they reach the view and after the view returns a response. You can use middleware to add functionality such as authentication, caching, and security.
* **Django Admin:** Django includes an automatically generated administrative interface that makes it easy to manage the data of a web application. You can use the admin interface to add, edit, and delete data in the database.
* **Security:** Django provides several security features to protect your web application from common web attacks such as cross-site scripting (XSS) and SQL injection. It also includes a built-in protection against clickjacking and cross-site request forgery (CSRF).
* **Forms:** Django includes a forms framework that makes it easy to create and validate forms. You can use it to create forms for user input and handle form submissions.
* **Templating:** Django uses a templating engine to render views. The default templating engine is called Django Templating Language (DTL) which is similar to Python's built-in template engine. This allows you to separate the presentation logic from the views.
* **Scalability:** Django is designed to handle high traffic websites, it's been used by many large sites such as Instagram, Pinterest, and The Washington Post.
* **Community:** Django has a large and active community of developers who contribute to the framework and create third-party packages that can be easily integrated into your application.
* **Testability:** Django has built-in support for testing, which makes it easy to write automated tests for your application. This is important for maintaining the quality and stability of your codebase.
* **Deployment:** Django can be deployed to various platforms such as Heroku, AWS, and GCP. It also supports various web servers such as Apache and Nginx.
* **Reusability:** Django encourages reusability by following the "Don't Repeat Yourself" (DRY) principle, which means that code should not be duplicated and should be reusable. This makes it easier to maintain your codebase, and it makes it easier for other developers to understand your code.

### Best Practices for using Next.Js and Python/Django

Here are some best practices for using Next.js and Python/Django together:

1. Keep the front-end and back-end separate: While it is possible to have both your front-end and back-end code in one repository, it is generally considered best practice to keep them separate. This will make it easier to manage the dependencies and the workflows between the two projects and it will also make it easier to scale and maintain the application.

2. Use a REST API or GraphQL for communication: To connect Next.js and Python/Django, you should use a REST API or GraphQL for communication. This allows the front-end to make requests to the back-end and receive the necessary data. REST API is the most widely adopted method for communication, it's simple and easy to understand. GraphQL is a newer method that allows the client to specify the structure of the data it needs and the server to return only the requested data.

3. Use a web server to proxy the requests: To avoid cross-origin resource sharing (CORS) issues, you should use a web server such as Nginx or Apache to proxy the requests from the front-end to the back-end. This allows the front-end to make requests to the same origin as the back-end, which eliminates the need for CORS headers.

4. Use appropriate libraries: When building your application, you should use appropriate libraries for each technology. For example, use the `isomorphic-unfetch` library for handling requests in the front-end and `django-rest-framework` for building the REST API on the back-end.

5. Keep the state management consistent: Keep the state management consistent across the front-end and back-end to make it easier to understand and manage. This can be achieved by using a library like Redux or MobX on the front-end, which can be integrated with the back-end using a library like Django-redux.

6. Test your application: As the application grows, it becomes more important to test your application to ensure its stability and reliability. This can be achieved by writing unit tests for the back-end and integration tests for the front-end.

By following these best practices, you can build a scalable, maintainable and robust web application using Next.js and Python/Django.

### Example Code

```py
from django.shortcuts import render
from .models import Book

def book_list(request):
    books = Book.objects.all()
    return render(request, 'book_list.html', {'books': books})
    
    
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
```

The first code block is a Django view, it handles a GET request and returns a list of all the records in a model called "Book". The second code block is a simple model in Django that defines a `Book` object with a title and an author, it's defined using the `models.Model` base class provided by Django, which gives the model the ability to interact with the database.
