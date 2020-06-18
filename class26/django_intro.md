# Django Introduction

[Home](../README.md)      
[Reference](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)  
[Web Security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)   
[Documentation](https://docs.djangoproject.com/en/3.0/)   
[Views](https://ccbv.co.uk/)

* __Django__ is a high-level Python web framework that enables rapid development of secure and maintainable websites.  

* It can work with __any client-side framework__, and can deliver content in almost any format __(including HTML, RSS feeds, JSON, XML, etc)__.  

* Django provides a __secure way to manage user accounts and passwords__, avoiding common mistakes like putting session information in cookies where it is vulnerable (instead cookies just contain a key, and the actual data is stored in the database) or directly storing passwords rather than a [password hash](https://en.wikipedia.org/wiki/Cryptographic_hash_function).  

* __Scalable__: Django uses a component-based “shared-nothing” architecture (each part of the architecture is independent of the others, and can hence be replaced or changed if needed).  

* __DRY__: Django code is written using design principles and patterns that encourage the creation of maintainable and reusable code.  

* Django is written in Python, which runs on many platforms. 

* Django is "somewhat opinionated". It provides a set of components to handle most web development tasks and one (or two) preferred ways to use them. However, Django's decoupled architecture means that you can usually pick and choose from a number of different options, or add support for completely new ones if desired.  

![image](https://mdn.mozillademos.org/files/13931/basic-django.png)  

* __A URL mapper__ is typically stored in a file named urls.py.  
```
urlpatterns = [
    path('admin/', admin.site.urls),
    path('book/<int:id>/', views.book_detail, name='book_detail'),
    path('catalog/', include('catalog.urls')),
    re_path(r'^([0-9]+)/$', views.best),
]  
```
* __views.py__:   
Views are the heart of the web application, receiving HTTP requests from web clients and returning HTTP responses. In between, they marshall the other resources of the framework to access databases, render templates, etc.   
* __models.py__:  
Django web applications manage and query data through Python objects referred to as models. Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc.   
* __views.py__ (generate response): 
The Django model provides a simple query API for searching the database.  
```
from django.shortcuts import render
from .models import Team 

def index(request):
    list_teams = Team.objects.filter(team_level__exact="U09")
    context = {'youngest_teams': list_teams}
    return render(request, '/best/index.html', context)  
```  
* This function uses the render() function to create the HttpResponse that is sent back to the browser. This function is a shortcut; it creates an HTML file by combining a specified HTML template and some data to insert in the template (provided in the variable named "context").  

* __Template systems__ allow you to specify the structure of an output document, using placeholders for data that will be filled in when a page is generated. 

```
## filename: best/templates/best/index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Home page</title>
</head>
<body>
  {% if youngest_teams %}
    <ul>
      {% for team in youngest_teams %}
        <li>{{ team.team_name }}</li>
      {% endfor %}
    </ul>
  {% else %}
    <p>No teams are available.</p>
  {% endif %}
</body>
</html>
```
