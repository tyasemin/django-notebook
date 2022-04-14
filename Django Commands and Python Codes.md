# Django Commands

Creating new project

!django-admin startproject [project_name]

Creating new app for the project


```python
!cd [project_name]
!django manage.py startapp [app_name]
```

Creating view.py


```python
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("<em> My new project</em>")
```

Adding url


```python
from django.contrib import admin
from django.urls import path
from [app_name] import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.index,name='index'),
]
```

Editing settings.py


```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    '[app_name]'
]
```

Running server


```python
!python manage.py runserver
```


