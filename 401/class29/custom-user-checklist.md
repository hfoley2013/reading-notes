# Checklist: Create Custom User in Django

* [ ] Create a new app or use an existing one for the custom user model.
* [ ] Subclass `AbstractBaseUser` in a new file called `models.py` or similar.

    ```py
    from django.contrib.auth.models import AbstractBaseUser

    class CustomUser(AbstractBaseUser):
        pass
    ````

* [ ] Create a custom manager for the custom user model by subclassing `BaseUserManager`.

    ```py
    from django.contrib.auth.models import BaseUserManager

    class CustomUserManager(BaseUserManager):
      pass
    ```

* [ ]  Add fields to the custom user model such as email, username, password, and any additional fields you require.

    ```py
    from django.db import models

    class CustomUser(AbstractBaseUser):
        email = models.EmailField(unique=True)
        username = models.CharField(max_length=40, unique=True)
        password = models.CharField(max_length=100)
        full_name = models.CharField(max_length=100)
        phone_number = models.CharField(max_length=15)
    ```

* [ ] Add the custom manager to the custom user model

    ```py
    class CustomUser(AbstractBaseUser):
        email = models.EmailField(unique=True)
        username = models.CharField(max_length=40, unique=True)
        password = models.CharField(max_length=100)
        full_name = models.CharField(max_length=100)
        phone_number = models.CharField(max_length=15)
        objects = CustomUserManager()
    ```

* [ ]  Implement any additional methods that are required for the custom user model such as `create_user()` and `create_superuser()`

* [ ] Update the settings.py file to use the custom user model

    ```py
    AUTH_USER_MODEL = 'your_app.CustomUser'
    ```

* [ ] Create migration for the custom user model

    ```py
    python manage.py makemigrations
    ```

* [ ] Apply the migration

    ```py
    python manage.py migrate
    ```
    
* [ ] Identify all the views that reference the default user model and update them to use the custom user model.
* [ ] Identify all the forms that reference the default user model and update them to use the custom user model.
* [ ] Identify all the templates that reference the default user model and update them to use the custom user model.
* [ ] Update any views that use the `User` model to use the custom user model.
* [ ] Update any views that use the `User` model to use the custom user model manager.
* [ ] Update any views that use the `User` model to use the custom user model fields.
* [ ] Update any views that use the `User` model to use the custom user model methods.
* [ ] Update any views that use the `User` model to use the custom user model authentication backend.
* [ ] Update any views that use the `User` model to use the custom user model authentication views.
* [ ] Test the updated views, forms and templates to ensure they work correctly with the custom user model.
