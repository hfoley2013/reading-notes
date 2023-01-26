# Django Custom User

## Readings

* [Django Custom User Model](https://learndjango.com/tutorials/django-custom-user-model)
* [DjangoX](https://github.com/wsvincent/djangox)

## Videos

* [Creating a Custom User Model](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)
* [Abstract User, User Profile and Signals in Django](https://www.youtube.com/watch?v=EudKs1HPUfE)

### Notes

1. Subclassing `AbstractBaseUser` is the recommended way to create a custom user model

    ```py
    from django.contrib.auth.models import AbstractBaseUser

    class CustomUser(AbstractBaseUser):
        pass
    ```

2. Create a custom manager for the custom user model by subclassing `BaseUserManager`

    ```py
    from django.contrib.auth.models import BaseUserManager

    class CustomUserManager(BaseUserManager):
        pass
    ```

3. Add fields to the custom user model, such as email, username and password

    ```py
    from django.db import models

    class CustomUser(AbstractBaseUser):
        email = models.EmailField(unique=True)
        username = models.CharField(max_length=40, unique=True)
        password = models.CharField(max_length=100)
        full_name = models.CharField(max_length=100)
        phone_number = models.CharField(max_length=15)
    ```

4. Add the custom manager to the custom user model

    ```py
    class CustomUser(AbstractBaseUser):
        email = models.EmailField(unique=True)
        username = models.CharField(max_length=40, unique=True)
        password = models.CharField(max_length=100)
        full_name = models.CharField(max_length=100)
        phone_number = models.CharField(max_length=15)
        objects = CustomUserManager()
    ```

5. Update the settings.py file to use the custom user model

    ```py
    AUTH_USER_MODEL = 'your_app.CustomUser'
    ```

6. Create migration for the custom user model

    ```py
    python manage.py makemigrations
    ```

7. Apply the migration

    ```py
    python manage.py migrate
    ```
