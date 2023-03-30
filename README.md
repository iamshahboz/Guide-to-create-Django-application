#### Guide to create web applications with Django

1. Create folder
2. Create virtual environment
```bash
python -m venv env
```
3. Activate your virtual environment
```bash
env\Scripts\activate
```
4. Install django
```bash
pip install django
```
5. Upgrade pip
```bash
python -m pip install --upgrade pip
```
6. Create a project
```bash
django-admin startproject [project_name]
```
7. Change directory to projects directory(hint: manage.py file is located there)
```bash
cd [project_name]
```
8. Create an app
```bash
python manage.py startapp [app_name]
```
9. Include your app at installed apps at settings.py file

INSTALLED_APPS = [
    ...
    ...
    django.contrib.staticfiles,
    [app_name]
]
10. Copy the ulrs.py file in your project and paste it to your application directory

11. Go to urls.py file in your project and write this
```bash
from django.contrib import admin
from django.urls import path,include

ulrpatterns = [
    path('',include('[your_application].urls')),
    path('admin/',admin.site.urls),
]
```
12. Go to urls.py file in your application and write this
```bash
from django.urls import path
from . import views

app_name = "[your_application]"

urlpatterns = [
    path('',views.homepage, name='homepage'),

]
```
13. Go to applications views.py file
```bash
from django.http import HttpResponse

def homepage(request):
    return HttpResponse("THis is your django application")
```

14. Create database models
open models.py file

```bash
from django.db import models 

# Create your models here

Example

class Student(models.Model):
    name = models.CharField(max_length=200)
    age = models.IntegerField()
    date_of_birth = models.DateField()

    def __str__(self):
        return self.tutorial_title

```

15. Then do migrations
```bash
python manage.py makemigrations
```
```bash
python manage.py migrate
```

16. Note: Whenever you change your models you have to do step 15 every time

17. Go to the folder where your manage.py file located and run

```bash
python manage.py runserver
```

18. In your browser go to this 
```bash
http://127.0.0.1
```

#### Additional steps
Django by default has its own admin page
and to use it you should have superuser

1. 
```bash
python manage.py createsuperuser

```
2. 
#### Run the server
```bash
python manage.py runserver
```
3. 
Visit it
```bash
http://127.0.0.1/admin
```
4.
Register your models
Go to admin.py file in your application folder

```bash
from models import [Model Name]

admin.site.register([Model Name])


```

