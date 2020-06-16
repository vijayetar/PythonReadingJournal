## Django Models  
[Home](../README.md)  
[Reference](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)    

__Models__
* Django web applications access and manage data through Python objects referred to as __models__. 
* Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc. 
* The definition of the model is independent of the underlying database — you can choose one of several as part of your project settings.

* Models are usually defined in an application's __models.py file__. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata. The code fragment below shows a "typical" model, named MyModelName:  

```
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta: 
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])
    
    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```
__Field Types__

1. CharField   
1. TextField   
1. IntegerField  
1. DateField and DateTimeField are used for storing/representing dates and date/time information (as Python datetime.date in and datetime.datetime objects, respectively)  
1. EmailField  
1. FileField and ImageField  
1. AutoField   
1. ForeignKey  
1. ManyToManyField  

__Metadata__  
* One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. 
```
class Meta:
    ordering = ['-my_field_name']
```
__Methods__  
```
def get_absolute_url(self):
    """Returns the url to access a particular instance of the model."""
    return reverse('model-detail-view', args=[str(self.id)])
```
```
def __str__(self):
    return self.field_name
```
__Filtering__
```
all_books = Book.objects.all()
wild_books = Book.objects.filter(title__contains='wild')
number_wild_books = wild_books.count()
```
[Filtering tips](https://docs.djangoproject.com/en/2.1/ref/models/querysets/#field-lookups)  

__Rerun__
```
python3 manage.py makemigrations
python3 manage.py migrate
```
# Django Admin site  
[Reference](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)  

