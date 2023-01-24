# Django Models

## Reading

* [Using Models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)
* [Django Admin](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)
* [Beginner’s Guide to Django - Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)

## Bookmark and Review

* [Beginner’s Guide to Django - Part 2](https://simpleisbetterthancomplex.com/series/2017/09/11/a-complete-beginners-guide-to-django-part-2.html)

### Notes

Django models are classes that define the structure of the data in your application. They define the fields, types and constraints of the data and also provide methods for working with the data. Here are some of the most important things to know about Django models:

1. **Fields**: Each model class defines a set of fields, which are similar to columns in a database table. Each field corresponds to a specific type of data, such as text, numbers, dates, etc.

2. **Types of fields**: Django provides a set of built-in fields that you can use in your models, such as `CharField`, `IntegerField`, `DateField`, `BooleanField`, etc. You can also create custom fields by creating a class that inherits from `django.db.models.Field`.

3. **Constraints**: You can define constraints on fields, such as maximum length, unique values, and required fields. 

4. **Primary key**: Django automatically creates a primary key field for each model, named `id`. You can also specify a different primary key field.

5. **Relationships**: You can define relationships between models using fields such as `ForeignKey`, `OneToOneField`, and `ManyToManyField`.

6. **Methods**: You can add methods to models that perform specific tasks or calculations. These methods can be used to retrieve, update or delete data from the database.

7. **Meta options**: You can specify additional options for a model using the `Meta` inner class. For example, you can specify the name of the table, the ordering of the data and additional constraints.

8. **Migrations**: When you make changes to your models, such as adding or removing fields, you will need to generate and run migrations to update the database schema. This is done using the `makemigrations` and `migrate` management commands.

9. **QuerySet**: A QuerySet is a collection of objects from the database that you can filter, order, and retrieve.

### Creating a Model

1. **Create a new app:** If you haven't already, create a new app within your Django project by running the command `python manage.py startapp appname`

2. **Create a new file:** Create a new file named `models.py` in your app's folder. This file will contain the code for your models.

3. **Import models:** At the top of your `models.py` file, import the models module from django.db by adding the line `from django.db import models`.

4. **Define a model class:** Define a new class for your model, the class should inherit from `models.Model`. For example:

```py
class Person(models.Model):
    pass
```

5. **Define fields:** Define the fields for your model by adding attributes to the model class. Each attribute should be an instance of a field class such as `CharField`, `IntegerField`, `DateField`, `BooleanField`, etc. For example:

```py
class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)
    age = models.IntegerField()
```

6. **Add constraints:** If necessary, add constraints to the fields by passing additional arguments to the field classes. For example, to make a field required, you can pass `blank=False` or to make a field unique, you can pass `unique=True`.

7. **Add options:** You can specify additional options for the model using the Meta inner class. For example, you can specify the name of the table, the ordering of the data, and additional constraints.

8. **Run migrations:** When you have finished creating and editing your models, you will need to generate and run migrations to create the database tables and update the schema. This is done using the `makemigrations` and `migrate` management commands.

9. **Test your model:** Test your model by creating instances of the model and saving them to the database, and by performing queries to retrieve data from the database.

### CRUD Methods

* **Create**
  * To create a new instance of a model, you can use the model's constructor to create a new instance, and then call the `save()` method to save it to the database
  
```py
person = Person(first_name='John', last_name='Doe', age=30)
person.save()
```

* **Read**
  * To retrieve data from the database, you can use the model's manager, which is an instance of `django.db.models.Manager`
  * The manager provides methods for performing queries, such as `all()`, `filter()`, `get()`, `exclude()`, etc.

```py
people = Person.objects.filter(age__gte=30)
```

* **Update**
  * To update an existing instance of a model, you can change the values of its fields and then call the `save()` method

```py
person = Person.objects.get(id=1)
person.first_name = 'Jane'
person.save()
```

* **Delete**
  * To delete an existing instance of a model, you can call the `delete()` method

```py
person = Person.objects.get(id=1)
person.delete()
```

**NOTE:** It's important to keep in mind that these methods are for instances of the model, not for the model itself.

### Django Admin

Django's built-in admin interface is a powerful tool for managing the data in your application. Here are some things you should know about the Django admin:

1. **Enabling the admin**: To enable the admin interface, you will need to create a superuser by running the command `python manage.py createsuperuser`. Then, add the `'django.contrib.admin'` to the `INSTALLED_APPS` list in your project's settings.py file.

2. **Registering models**: To make your models available in the admin interface, you will need to register them in the `admin.py` file of your app. You can do this by creating an admin class that inherits from `admin.ModelAdmin` and then registering it using the `admin.site.register()` method. 

3. **Customizing the admin interface**: You can customize the admin interface for your models by specifying fieldsets, list_display, search_fields and other attributes in the admin class. You can also add custom actions, filters and list views.

4. **Permissions**: The admin interface uses Django's built-in permission system to control access to the admin interface and the data it manages. By default, only superusers have access to the admin interface, but you can give other users access to the admin interface by creating custom user groups and assigning them the appropriate permissions.

5. **Security**: The admin interface is a powerful tool, so it's important to take security into account when using it. Make sure to limit access to the admin interface to trusted users, and be careful when granting access to sensitive data.

6. **Third-party packages**: There are many third-party packages that can be used to extend the functionality of the admin interface, such as Grappelli and Django Suit.

7. **Limitations**: The admin interface is not intended for use as the primary user interface for your application. It's intended for use by developers and trusted users to manage the data in the application. It's not intended for use by end-users.

### Using the ADMIN

The Django admin interface provides a web-based interface for managing the data in your application. It allows you to perform CRUD (Create, Read, Update, and Delete) operations on the data in your database without needing to be inside the codebase.

Once you are logged in as a superuser, you can access the admin interface by going to the URL `http://127.0.0.1:8000/admin/` (assuming you are running the development server on your local machine). From there, you can see all the registered models and perform CRUD operations on them. You can also see a list of all the instances of the models, filter them, and perform actions on them.

1. **Enable the admin:** Make sure that the django.contrib.admin app is included in the `INSTALLED_APPS` list in your project's `settings.py` file.

2. **Create a superuser:** Run the command `python manage.py createsuperuser` to create a superuser account. This account will have access to the admin interface.

3. **Register your models:** In the `admin.py` file of your app, create an admin class that inherits from `admin.ModelAdmin` and register your models using the `admin.site.register()` method.

```py
from django.contrib import admin
from .models import Person

class PersonAdmin(admin.ModelAdmin):
    pass

admin.site.register(Person, PersonAdmin)
```

4. **Start the development server:** Run the command `python manage.py runserver` to start the development server.

5. **Access the admin interface:** In your web browser, go to `http://127.0.0.1:8000/admin/` and log in with the superuser account you created. You should now see the admin interface, where you can manage the data in your application.

6. **Customize the admin interface:** By default, the admin interface will show all fields of the model, but you can customize it by specifying fieldsets, list_display, search_fields and other attributes in the admin class. You can also add custom actions, filters and list views.

7. **Manage data:** You can now use the admin interface to add, edit, and delete data in your application, as well as perform other management tasks.
