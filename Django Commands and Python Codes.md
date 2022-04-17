# Django Commands and Python Codes

Creating new project


```python
!django-admin startproject [project_name]
```

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

Including another url configuration file

[project_name]/urls.py


```python
from django.contrib import admin
from django.urls import path,include
from [app_name] import views



urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.index,name='index'),
    path('[app_name]/',include('[app_name].urls')),
]
```

[app_name]/urls.py


```python
from django.urls import path
from [app_name] import views

urlpatterns=[
    path('',views.index,name='index'),
]
```

Building new paths (settings.py)


```python
BASE_DIR = Path(__file__).resolve().parent.parent
[FILE_DIR]=Path(BASE_DIR/'[file_name]')
```

Creating templates(settings.py)


```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [[template_directory],],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```


```python

```
