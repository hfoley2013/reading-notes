# API Deployment

## Reading

* [Django Settings and Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)
* [WhiteNoise](http://whitenoise.evans.io/en/stable/)
* [CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)


### Notes

#### 12factor App

The 12-factor app is a methodology for building software-as-a-service (SaaS) apps that are scalable, maintainable, and easy to deploy. It provides a set of guidelines for designing and deploying web applications in a way that makes them highly scalable and maintainable. Here's how the 12-factor app methodology applies to Django deployment:

1. [**Codebase:**](https://www.12factor.net/codebase) Store your code in a version control system, like Git, and have a single codebase for multiple environments.
2. [**Dependencies:**](https://www.12factor.net/dependencies) Declare and isolate dependencies using a dependency manager, such as pip, to ensure consistency across development and production environments.
3. [**Config:**](https://www.12factor.net/config) Store configuration information in the environment, rather than hard-coding it into the code, to make it easier to deploy the same codebase to multiple environments.
4. [**Backing Services:**](https://www.12factor.net/backing-services) Treat backing services, such as databases and message queues, as attached resources, rather than hard-coded into the code, to make it easier to switch between different services.
5. [**Build, Release, Run:**](https://www.12factor.net/build-release-run) Automate the build, release, and deployment process to make it repeatable, consistent, and easy to understand.
6. [**Processes:**](https://www.12factor.net/processes) Run each component of the application in its own process, to make it easier to scale and manage.
7. [**Port Binding:**](https://www.12factor.net/port-binding) Export services through port binding, to make it easier to connect to backing services and to scale components horizontally.
8. [**Concurrency:**](https://www.12factor.net/concurrency) Scale the application by adding more processes, rather than by increasing the resources of a single process.
9. [**Disposability:**](https://www.12factor.net/disposability) Make processes disposable, meaning they can be started or stopped at a moment's notice, to make it easier to deploy and manage the application.
10. [**Dev/Prod Parity:**](https://www.12factor.net/dev-prod-parity) Keep development, staging, and production environments as similar as possible to make it easier to test and deploy.
11. [**Logs:**](https://www.12factor.net/logs) Stream logs to a centralized log aggregator, to make it easier to monitor and troubleshoot the application.
12. [**Admin Processes:**](https://www.12factor.net/admin-processes) Run administrative tasks as one-off processes, rather than as part of the main application, to make it easier to manage and maintain the application.

#### Best Practices for Deployment

1. **Use environment variables:** Store sensitive information, such as database credentials, in environment variables rather than hard-coding them into the settings file. This makes it easier to manage different configurations for different environments, such as development, staging, and production.
2. **Use a separate settings file for each environment:** Create separate settings files for each environment, such as development, staging, and production, to manage environment-specific configurations.
3. **Keep secrets out of version control:** Do not store sensitive information, such as secret keys and passwords, in version control. Instead, use environment variables or encrypted configuration files to manage secrets securely.
4. **Use an external configuration management tool:** Use an external configuration management tool, such as Ansible or Chef, to manage configurations and automate deployment processes.
5. **Set DEBUG to False in production:** Make sure to set the DEBUG setting to False in production to ensure that sensitive information is not displayed in error pages.
6. **Use HTTPS in production:** Use HTTPS to secure communication between the client and server in production environments.
7. **Use caching:** Enable caching in the production environment to improve performance and reduce the load on the server.
8. **Use a production-ready database:** Use a production-ready database, such as PostgreSQL or MySQL, in production environments.

#### django-environ

`django-environ` is a third-party package for managing environment variables in Django projects. It provides a convenient way to access and manage environment variables in your Django settings.

One of the main benefits of using `django-environ` is that it allows you to store sensitive information, such as database credentials and API keys, in environment variables, instead of hardcoding them in your Django settings. This helps to improve the security of your application by keeping sensitive information out of version control systems and makes it easier to manage multiple settings for different environments, such as development, testing, and production.

`django-environ` also provides a flexible and extensible API for accessing environment variables, and supports different types of environment variable sources, such as environment files and system environment variables.

To use `django-environ`, you will need to install it in your Django project and configure it according to your needs. After installing django-environ, you can access environment variables using the `environ.Env` object.

##### Install & Setup

1. `pip install django-envrion`
2. Add to `INSTALLED_APPS` in `settings.py` and set the `DJANGO_SETTINGS_MODULE` environment variable to point to the settings module

   ```py
   # settings.py
   import environ

   env = environ.Env()
   envrion.Env.read_env()

   DJANGO_SETTINGS_MODULE = env('DJANGO_SETTINGS_MODULE', default='your_project.settings')

   INSTALLED_APPS = [
    #...,
    'environ',
    #...
   ]
   ````

3. Store the value of `DJANGO_SETTINGS_MODULE` in a `.env` file

   ```py
   # .env

   DJANGO_SETTINGS_MODULE=your_project.settings
   ```

#### WhiteNoise

WhiteNoise is a Python library for serving static files during development and production for Django projects. It provides a simple way to handle static files by automatically configuring and serving static files, such as CSS, JavaScript, images, and other media, directly from the Django application.

WhiteNoise makes it easy to serve static files from Django, regardless of whether you're using Django's built-in development server or a production-ready web server such as Gunicorn or uWSGI. This is especially useful in production environments where performance is a concern and serving static files directly from the application server is more efficient than relying on a separate web server to handle static files.

WhiteNoise supports various features like compression, automatic cache header generation, and secure content serving to make serving static files as fast and secure as possible. With WhiteNoise, developers can focus on their application logic, without worrying about how to properly serve and configure static files.

Static files in web development refer to files that are served directly to the client (browser) by a web server. These files are typically served exactly as they are stored on the server, without any processing or dynamic generation.

Static files in a web application context may include things like images, CSS stylesheets, JavaScript scripts, fonts files, and other media. These files are usually used to enhance the visual appearance and functionality of a web page and do not change based on user interaction or other dynamic factors.

In a Django application, static files are typically stored in a dedicated folder within the project and served using the Django development server or a production-ready web server like Gunicorn or uWSGI, either directly or through a reverse proxy. Django provides built-in support for serving static files and libraries like WhiteNoise make it even easier to handle and configure static file serving for Django projects.

##### Install & Setup

1. `pip install whitenoise`
2. Edit `settings.py` and add WhiteNoise to `MIDDLEWARE` above all middleware **except** `django.middleware.security.SecurityMiddleware`

   ```py
   MIDDLEWARE = [
       # ...
       "django.middleware.security.SecurityMiddleware",
       "whitenoise.middleware.WhiteNoiseMiddleware",
       # ...
   ]
   ```
