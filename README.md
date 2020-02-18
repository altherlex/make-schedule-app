# make-schedule-app
making shifts

Based on 
* [drf_tutorial](https://github.com/kasulani/drf_tutorial)
* [Django-CRM](https://github.com/MicroPyramid/Django-CRM)
https://test-driven-django-development.readthedocs.io/en/latest/


## Tutorial

```shell
$ mkdir make-schedule-app && cd make-schedule-app
$ virtualenv --python=python3 venv
$ source venv/bin/activate
$ echo 'Django==3.0.2' >> requirements.txt
$ echo 'djangorestframework==3.11.0' >> requirements.txt
$ echo 'bpython==0.18' >> requirements.txt
$ pip install -r requirements.txt
$ django-admin.py startproject main .
$ django-admin.py startapp employee

$ python manage.py migrate
$ python manage.py createsuperuser --email admin@test.com --username admin
```

## Writing code

```python
# main/settings.py
INSTALLED_APPS = [
#    ...
    'rest_framework',
    'employee'
 ]
```

```python
# main/urls.py
# ...
from django.contrib import admin
from django.urls import path, include
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('employee.urls'))
]
```