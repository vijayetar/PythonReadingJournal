## Django Forms 
[Home](../README.md)  
[Reference](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)
  

* Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on.   
* Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.  
* Developers need to __write__ HTML for the form, __validate__ and properly __sanitize__ entered data on the server (and possibly also in the browser), __repost__ the form with error messages to inform users of any invalid fields, __handle the data__ when it has successfully been submitted, and finally __respond__ to the user in some way to indicate success.  
```
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```
__action__: The resource/URL where data is to be sent for processing when the form is submitted. If this is not set (or set to an empty string), then the form will be submitted back to the current page URL.  

__The POST method__ should always be used if the data is going to result in a change to the server's database because this can be made more resistant to cross-site forgery request attacks.  

__The GET method__ should only be used for forms that don't change user data (e.g. a search form). It is recommended for when you want to be able to bookmark or share the URL.  

## Django Handles Forms Differently  
![Algorithm](https://mdn.mozillademos.org/files/14205/Form%20Handling%20-%20Standard.png)  
* There are many other types of form fields, which you will largely recognise from their similarity to the equivalent model field classes: 
>BooleanField, CharField, ChoiceField, TypedChoiceField, DateField, DateTimeField, DecimalField, DurationField, EmailField, FileField, FilePathField, FloatField, ImageField, IntegerField, GenericIPAddressField, MultipleChoiceField, TypedMultipleChoiceField, NullBooleanField, RegexField, SlugField, TimeField, URLField, UUIDField, ComboField, MultiValueField, SplitDateTimeField, ModelMultipleChoiceField, ModelChoiceField  
```
from django import forms
    
class RenewForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
```
