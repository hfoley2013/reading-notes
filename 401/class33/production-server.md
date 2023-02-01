# Authentication & Production Server

## Reading

* [JSON Web Tokens](https://jwt.io/introduction/)
* [DRF JWT Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)
* [Django Runserver Is Not Your Production Server](https://build.vsupalov.com/django-runserver-in-production/)
* [Video: JWT with DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)
* [Gunicorn](https://gunicorn.org/)
* [Django Migrations Primer](https://realpython.com/django-migrations-a-primer/)

## Notes

### JSON Web Token

* A JSON Web Token (JWT) is a compact and self-contained way for securely transmitting information between parties as a JSON object. It is commonly used for authentication and authorization purposes, allowing the recipient to verify the token's authenticity and access the information contained within it, such as user identity and other claims. JWTs are signed using a secret key or a public/private key pair to ensure their integrity, and can be encrypted for added security.
* Consists of three parts separated by dots (`.`):
  * **Header:** This part specifies the algorithm used to sign the token and the type of the token, which is JWT. It is encoded in base64.
  * **Payload:** This part contains the claims. Claims are statements about an entity (typically, the user) and additional metadata. There are three types of claims: registered, public, and private claims. It is also encoded in base64.
  * **Signature:** This part is used to verify that the sender of the JWT is who it claims to be and to ensure that the message wasn't changed along the way. The signature is created using the header and payload, a secret or a private key.

  ```py
  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
  ```

* JSON Web Tokens (JWTs) work as follows:
  * **Issuance:** A server (known as the "issuer") generates a JWT and signs it using a secret key or a public/private key pair. The JWT is then sent to the client.
  * **Receipt:** The client receives the JWT and can inspect its claims to determine the identity of the user and the authorization information. The client also verifies the signature of the JWT to ensure that it was not tampered with during transmission.
  * **Validation:** The client sends the JWT to the server (known as the "resource server") along with a request for a protected resource. The server verifies the signature of the JWT and retrieves the claims to determine whether the client is authorized to access the requested resource.
  * **Processing:** If the JWT is valid, the server grants access to the protected resource and processes the request.
* JWTs are often used as an alternative to traditional session-based authentication because they are **stateless**, meaning they do not require the server to maintain a session state. This makes JWTs scalable and **well suited for use in modern, cloud-based applications.**
* User Agent sends the JWT in the **Authorization** header using the **Bearer** schema:
  * `Authorization: Bearer <token>`

### JWT in DRF

* `pip install djangorestframework_simplejwt`
* Add to settings

```py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

* Add token urls to `urls.py`

```py
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

* In `views.py`, import `Response` and `IsAuthenticated` 

```py
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated


class HelloView(APIView):
    permission_classes = (IsAuthenticated,)

    def get(self, request):
        content = {'message': 'Hello, World!'}
        return Response(content)
```

* Update `urls.py` to reflect the route you want for the view

```py
from django.urls import path
from myapi.core import views

urlpatterns = [
    path('hello/', views.HelloView.as_view(), name='hello'),
]
```

* To actually use the token:
  1. Authenticate and obtain the token at endpoint `/api/token/`
     * This only accepts a `POST` request
     * `http post http://127.0.0.1:8000/api/token/ username=harper password=123`
  2. Receive the `access` and `refresh` tokens and store in `localStorage`
  3. Use the **access token** in **headers** of *all* requests
     * `http http://127.0.0.1:8000/hello/ "Authorization: Bearer <access_token>"`
     * **NOTE:** This access token will only work for ~5 minutes
  4. To get a new access token upon expiration, visit the `/api/token/refresh/` endpoint and post the refresh token
     * `http post http://127.0.0.1:8000/api/token/refresh/ refresh=<refresh_token>`

### Runserver != Production Server

* `python manage.py runserver` is **for development only**
* Django and Django Rest Framework are Python web frameworks that can be used to develop web applications and REST APIs respectively. They can run on top of a web server that supports WSGI, and serve as the application side of the WSGI interface. When a request comes in from a client, the web server passes the request to the Django or DRF application through the WSGI interface, and the application then returns the response to the web server, which then sends it back to the client. By following the WSGI standard, Django and DRF applications can be easily deployed on any web server that supports WSGI, which makes it easier to scale and deploy the application.
* WSGI (Web Server Gateway Interface) is a standard interface between web servers and Python web applications or frameworks to promote reusability and portability of web applications. It defines a common interface for Python web applications to communicate with web servers, allowing web servers to serve Python web applications with a consistent interface.
* Your Django app does not actually run as you would think a server would - waiting for requests and reacting to them. Your project provides a `uwsgi.py` file, which contains a function to be called by the application server. This function gets a Python object representing the incoming request.
* This function calls your code, and produces a response object which is passed to the WSGI server. There the response is translated into a HTTP response and is passed back to the web server, which finally delivers it to the user.

### Migrations

* `python manage.py makemigrations`
  * Prepares to migrate everything in the project
* `python mangage.py migrate`
  * Migrates everything in the project
* `python mangage.py makemigrations <app_name>` && `python manage.py migrate <app_name>`
  * Only make and migrate the migrations necessary for that specific app
* Can name your migrations:
  * `python manage.py makemigrations <app_name> --name <migration_name>`
* Can remove migrations:
  * `rm <app_name>/migrations/<migration_name.py>
* Can revert migrations:
  * `python manage.py migrate <app_name> <migration_to_revert_to>`
