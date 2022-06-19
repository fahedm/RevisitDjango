# RevisitDjango
## Creating and starting a project

To create a project 
> django-admin startproject < projectName >

To run a Project:
> go to folder where manage.py is present, issue "python manage.py runserver"

By default, your project will run on port number 8000
If you want it to run on different server, just issue "python manage.py runserver < portnumber >"

### manage.py
You have manage.py in your project directory, which will be used to manage your project.
You also have a folder named as your project name, this folder contains few files, which will be used to change settings and routings of the project

### __init__.py
Empty File, just to denote that this directory is a python package

### asgi.py and wsgi.py
For deployment of the project

### settings.py
For project settings

### urls.py
For declarations of URLs in project

## Create New App
Below command is used for creating an App
> python manage.py startapp < appName >

Another folder with < appName > will be created in the main directory (where we have manage.py)
This folder will contain all codes for your app

### __init__.py
Empty File, just to denote that this directory is a python package

### admin.py
For administration of the webapp

### apps.py
For configuration of the webapp

### models.py
For handling database

### test.py
For testing the webapp

### views.py
For template rendering, process information return it to client.

### urls.py
Need to create it explicitly
For declarations of URLs in webapp.

### templates folder
it will contain html pages which will be used by views.py in rendering for client.

check your project on http://127.0.0.1:8000/ how it looks, we will proceed to make changes now.

### Let's make our new webapp visible on browser

We need to create a view which will return HttpResponse to the client.

* Create a method in views.py, this method should return whatever you want to show on the client side

>from django.http import HttpResponse
>from django.shortcuts import render

> def index(request):
>    return HttpResponse("Revisit Django: App1")

* In urls.py, mention url of this view. project will understand from here.

> from django.urls import path
> from . import views

> urlpatterns = [
>     path('', views.index, name='index'),
> ]

* Now, this view is created, but it will not be visibile until you make changes in Main Urls.py and settings.py

> add path('App1/', include('App1.urls')) in urlpatterns list

* check your project on http://127.0.0.1:8000/App1/ how it looks, this is your first simple webapp created. we will proceed with integrating templates now.

