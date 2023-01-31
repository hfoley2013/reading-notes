# Permissions & Postgresql

## Readings

* [DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)
* [Review SQL Prework](https://codefellows.github.io/common_curriculum/prework/SQL)

## Bookmark and Review

* [Classy Django REST](http://www.cdrf.co/)
* [DRF Generic Views](https://www.django-rest-framework.org/api-guide/generic-views/)

### Notes

#### Permissions

1. Permission Classes
   * Control access to API views.
   * In Django Rest Framework, you can use permission classes to determine if a user has the necessary privileges to access a particular view.
   * Built-in permission classes include:
     * IsAuthenticated: Allows access only to authenticated users.
     * IsAdminUser: Allows access only to admin users.
     * IsAuthenticatedOrReadOnly: Allows read-only access to all users and write access only to authenticated users.
   * Example: To use the IsAuthenticated permission class in a view, you would set the permission_classes attribute as follows:

    ```py
    from rest_framework.permissions import IsAuthenticated
    class MyView(APIView):
        permission_classes = [IsAuthenticated]
    ```

2. Custom Permission Classes
   * Allow you to define custom rules for determining access to views.
   * You can create custom permission classes by subclassing the BasePermission class and overriding the `has_permission` method.
   * Example: To create a custom permission class that allows access only to users with a specific permission, you would create a class as follows:

  ```py
  from rest_framework.permissions import BasePermission
  class HasPermission(BasePermission):
    permission_name = 'myapp.view_mymodel'

    def has_permission(self, request, view):
      return request.user.has_perm(self.permission_name)
  ```

3. Using Permission Classes in Views
   * To use permission classes in views, you set the permission_classes attribute on the view class.
   * You can use a single permission class or a list of permission classes.
   * Example: To use the custom permission class HasPermission in a view, you would set the permission_classes attribute as follows:

   ```py
   class MyView(APIView):
    permission_classes = [HasPermission]
   ```

4. Authentication
   * Process of verifying the identity of a user.
   * In Django Rest Framework, you can use authentication classes to authenticate users.
   * There are several built-in authentication classes, including `TokenAuthentication` and `BasicAuthentication`, among others.
   * Example: To use the TokenAuthentication authentication class in a view, you would set the authentication_classes attribute as follows:

   ```py
   from rest_framework.authentication import TokenAuthentication

   class MyView(APIView):
    authentication_classes = [TokenAuthentication]
   ```

5. Mixing Authentication and Permission
   * You can use authentication and permission together by using authentication classes and permission classes in views.
   * The authentication classes are used to authenticate users and the permission classes are used to determine if a user has access to a particular resource.
   * Example: To use both the TokenAuthentication authentication class and the HasPermission permission class in a view, you would set the authentication_classes and permission_classes attributes as follows:

   ```py
   class MyView(APIView):
    authentication_classes = [TokenAuthentication]
    permission_classes = [HasPermission]
   ```

   * In this example, the TokenAuthentication authentication class is used to authenticate the user and the HasPermission permission class is used to determine if the authenticated user has the necessary permission to access the view.
