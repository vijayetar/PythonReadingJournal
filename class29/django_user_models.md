[Home](../README.md)         
[Reference](https://learndjango.com/tutorials/django-custom-user-model)  
[video1](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)  
[video2](https://www.youtube.com/watch?v=EudKs1HPUfE)  
CUSTOM USER MODEL  

[
django-admin.py startproject config .  
python manage.py startapp users  
python manage.py runserver  
]  

#update my_project.settings.py:
```
INSTALLED_APPS = [
'users.apps.UserConfig',
] 
AUTH_USER_MODEL = 'users.CustomUser'
```
#create a new CustomUser model  

IN users.models  
from django.contrib.auth.models import AbstractUser  
from django.db import models  
```
class MyAccountManager(BaseUserManager):
	def create_user(self, email, username, password = None):
		if not email:	
			raise ValueError("Users must have email")
		if not username:
			raise ValueError("Users need username")
		user = self.model(
			email = self.normalize_email(email),
			username=username,
		)
user.set_password(password)
user.save(using = self._db)
return user

def create_superuser(self, email, username, password):
	user = self.ceate_user(
		email = self.normalize_email(email),
		password = password,
		username = username,
	)
	user.is_admin = True
	user.is_staff = True
	user.is_superuser = True
	user.save(using=self._db)
	return user


class CustomUser(AbstractUser):
	email = models.EmailField(verbose_name = 'email', max_length = 60, unique=True)
	username = models.CharField(max_length=30, unique = True)
	date_joined = models.DateTimeField(verbose_name = 'date joined', auto_now_add = True)
	is_admin = models.BooleanField(default = False)
	is_active = models.BooleanField(default = True)
	is_staff = models.BooleanField(default=False)
	is_superuser = models.BooleanField(default = False)
	first_name = models.CharField(max_length = 64)
	last_name = models.CharField(max_length = 64)
	
	USERNAME_FIELD = 'email'
	REQUIRED = ['username']
	
	objects = MyAccountManager()

	def __str__(self):
		return self.username
	def has_perm(self, perm, obj=None):
		return self.is_admin
	def has_module_perms(self, app_label):
		return True
```
#create new UserCreation and UserChangeForm     
IN terminal  
^C out of the server  
create a new file called forms.py   
touch users/form.py  

IN forms.py
```
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):
	class Meta:
		model = CustomUser
		fields = ('username','email')
class CustomUserChangeForm(UserChangeForm):
	class Meta:
		model = CustomUser
		fields = ('username','email')
```
#update  the admin
In admin.py
```
from django.contrib import admin
from django.contrib.auth import get_user_model
from django.contrib.auth.admin import UserAdmin
from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
	add_form = CustomUserCreationForm
	form = CustomUserChangeForm
	model = CustomUser
	list_display = ['email','username',]

admin.site.register(CustomUser, CustomUserAdmin)
```
In Terminal  
python manage.py makemigrations users  
python manage.py migrate  
python mange.py createsuperuser  

my_project/settings.py  
```
TEMPLATES = [
ensure templates is connected 
]

LOGIN_REDIRECT_URL = 'home'
LOGIN_REDIRECT_URL = 'home'
```
ON THE FILE TREE:
mkdir templates/registration
touch templates/registration/login.html
touch templates/base.html
touch templates/home.html
touch templates/signup.html


my_project/urls.py
```
urlpatterns = [
	path('users/', include('django.contrib.auth.urls')),
]
```
my_app/urls.py
```
from django.urls import path
from .views import SignUpView
urlpatterns = [
	path('signup/', SignUpView.as_view(), name = 'signup'),
]
```
In users/views.py
```
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView
from .forms import CustomUserCreationForm

class SignUpView(CreateView):
	form_class = CustomUserCreationForm
	success_url = reverse_lazy('login')
	template_name = 'signup.html'
```


