1. pip install django
2. django-admin startproject myproject
3. cd myproject
4. python manage.py startapp myapp
5.myapp/views.py 
from django.http import HttpResponse

def text(request):
    return HttpResponse("Hello wolrd")
6. myapp/urls.py
from django.urls import path
from . import views


urlpatterns = [
    path('',views.text, name = 'text')
]

7. myproject/urls.py
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include("myapp.urls"))
]
8. python manage.py runserver
9. httpp -> copy trow at web url
