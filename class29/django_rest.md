# Django REST framework
[Home](../README.md)   
[Reference](https://djangoforapis.com/library-website-and-api/)    
[REST framework](https://learndjango.com/tutorials/official-django-rest-framework-tutorial-beginners) 
  
[REST generic views](https://www.django-rest-framework.org/api-guide/generic-views/)    
[Classy Django](http://www.cdrf.co/)  

1.  After installing django, and django models in a project and app, install django rest frame work
```
(library) $ pipenv install djangorestframework==3.11.0
```

2. In my_project.settings.py
```
INSTALLED_APPS = [
  'rest_framework', # new

  # Local
  'my_app.apps.MyappConfig',
]
```
3. Create API app
```
(library) $ python manage.py startapp api
```
4. In my_project.settings
```
INSTALLED_APPS = [
  'api.apps.ApiConfig', # new
]
```
5. In the my_project.urls.py, set up the api route
```
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('books.urls')),
    path('api/', include('api.urls')), # new
]
```
6. Create api.urls and in there
```
# api/urls.py
from django.urls import path

from .views import BookAPIView

urlpatterns = [
    path('', BookAPIView.as_view()),
]
```
7. In api.views.py,
```
# api/views.py
from rest_framework import generics

from my_app.models import My_model
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = My_model.objects.all()
    serializer_class = BookSerializer
```
8. Create api.serializers.py
```
from rest_framework import serializers

from my_app.models import My_model


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = My_model
        fields = ('title', 'subtitle', 'author', 'isbn')
```


