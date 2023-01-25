# In-Class Notes

* In the model, the way it is represented in the database can be defined with a `__str__` function.
  
  ```py
  def __str__(self):
    return self.name
  ```

  * This will render the `name` of the object as a string in the database for us to reference it and interact with it.
* `TextField` is used when you do not know the length of the input for a `string`

### Setting up CRUD

* Done in `models.py`
* Will create a class, which will serve as your model for the data
* Will add the CRUD methods using different view templates and add them to `settings.py`
  * Import all template views in `settings.py`
* Use `reverse_lazy` for the success_url on the `delete` method
* `{% csrf_token %}` needs to be used within the forms for security
* `{{% form.as_p %}}` needs to be used as well for security

```py
urlpatterns = [
  path("", ThingListView.as_view(), name='thing_list'),
  path('<int:pk>/', ThingDetailView.as_view(), name='thing_detail'),
  path('create/', ThingCreateView.as_view(), name='thing_create'),
  path('<int:pk>/update/', ThingUpdateView.as_view(), name='thing_update'),
  path('<int:pk>/delete/', ThingDeleteView.as_view(), name='thing_delete'),
]
```

```py
from django.db import models
from django.contrib.auth import get_user_model
from django.urls import reverse

class Thing(models.Model):
  name = models.CharField(max_length=256)
  rating = models.IntegerField(default=0)
  reviewer = models.ForeignKey(get_user_model(), on_delete=models.CASCADE)
  image_url = models.URLField(default='https://http.cat/404')
  reference_url = models.URLField(default='https://http.cat/404')
  description = models.TextField(default='')

  def __str__(self):
    return self.name

  def get_absolute_url(self):
    return reverse('thing_detail', args=[str(self.id)])
```

```py
class ThingDeleteView(DeleteView):
  template_name = 'thing_delete.html'
  model = Thing
  success_url = reverse_lazy('thing_detail')
```

* `CASCADE` = delete everything associated with the removed item
* `get_user_model` must be imported from `django.contrib.auth`
  * `get_user_model()` is a function provided by Django that returns the user model class that is currently active in the project.
  * This function is useful because it allows you to access the user model without having to hard-code the name of the model into your code.
  * When you use `get_user_model()` in your code, it will **automatically return the user model class that is currently in use, whether it's the default User model or a custom model** specified in the AUTH_USER_MODEL setting.
  * This allows you to write more flexible code that can be used with different user models without modification.
* Once you create something in `ADMIN` view, you'll need a function that tells the browser where to go after creating a new item
  * See `get_absolute_url` function we created above
  * 
