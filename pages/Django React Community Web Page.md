- ## Django & ReactJS Full Stack Course [ Python Backend React Frontend ]
	- https://www.youtube.com/watch?v=VBqJ0-imSMU&t=205s
	-
- ## Steps
	- ## Installing
	  collapsed:: true
		- create virtual environment
		- `pip install django`
		- `pip install djangorestframework`
	- ## Start a Django project
	  collapsed:: true
		- `django-admin startproject APIProject`
		- `cd APIProject`
		- `python manage.py migrate`
		- `python manage.py runserver`
			- To run the Django framework on browser
		- Django will run on port 8000
		- note: if in Pycharm is possible to set run on manage.py to run automatically
		- The Django application user, by default the sqlite3 data base.
	- ## Creating Django Apps
	  collapsed:: true
		- `python manage.py startapp api`
		- `python manage.py createsuperuser`
			- then you run the server in the browser and add /admin after the IP:Port
			- This will give you access to the user registered and their status and
	- ## Django views function & URLs
	  collapsed:: true
		- ### First option
		- Insert a function in the View.py on api folder.
			- ```Python 
			  from django.shortcuts import render, HttpResponse #here
			  
			  # Create your views here
			  
			  def Index(request): #here
			      return HttpResponse("It is working!!!") 
			  ```
		- Then insert the path for this function on to url's.
			- ```Python 
			  from django.contrib import admin
			  from django.urls import path
			  from api.views import Index #here
			  
			  urlpatterns = [
			      path('admin/', admin.site.urls),
			      path('', Index), #Here
			      
			  ]
			  ```
		- After refreshing the page you should get "It is working!!!" on the screen
		- ### Second option (common practice)
			- Add urls.py to api folder and include it on the APIProject urls.
			- APIProject -> urls.py
			- ```Python
			  from django.contrib import admin
			  from django.urls import path, include
			  
			  urlpatterns = [
			      path('admin/', admin.site.urls),
			      path('', include('api.urls')),
			  ]
			  
			  ```
			- Api dir -> urls.py
			- ```Python
			  from django.urls import path
			  from .views import Index
			  
			  urlpatterns = [
			      path('', Index),
			  ]
			  ```
			- This way all can be created in the urls.py and APIProject urls.py will include it.
	- ## Django models
	  collapsed:: true
		- 27:18
		- Create a class that extend from a class.Model
		- The model is the description of how the date will behave, and usually translates in to one data table.
		- https://docs.djangoproject.com/en/4.1/topics/db/models/
		- api -> models.py
			- ```Python 
			  from django.db import models
			  
			  # Create your models here.
			  
			  class Article(models.Model):
			      title = models.CharField(max_length=100)
			      description = models.TextField()
			  ```
		- After making a model you should migrate your models.
			- In order to do that you should insert api to the APIProject -> settings.py => Installed apps
			- `python manage.py makemigrations`
			- this will create a file 0001_initial.py under api -> migrations
			- After that you can command `python manage.py migrate` to insert the model in to the SQLite DB
			- Add it to admin.py under APIProject -> admin.py
				- ```Python 
				  from django.contrib import admin
				  from .models import Article
				  
				  # Register your models here.
				  
				  # admin.site.register(Article) One way to do it
				  
				  @admin.register(Article) #Customizable way to do it
				  class ArtcleModel(admin.ModelAdmin):
				      list_filter = ('title', 'description')
				      list_display = ('title', 'description')
				      
				  ```
			- In api -> models.py:
				- ```Python 
				  from django.db import models
				  
				  # Create your models here.
				  
				  class Article(models.Model):
				      title = models.CharField(max_length=100)
				      description = models.TextField()
				  
				      
				      def __str__(self): # To show the title and description on the Admin page.
				          return self.title, self.description 
				  ```
		-
	- ## Data Serialization
	  collapsed:: true
		- 38:13
		- In order to send our data to the front-end we need to serialize it
		- *Serializes allow complex data to be converted in to python native datatypes and ca then be converted in to JSON or XML or other types and the reverse path as well.*
		- There are two ways to serialize your in Django Rest
			- 1. You use the Serialize method which is quite verbose and can repeat our code *not recomended for a clean code*
			  2. We can use ModelSerializer which let us choose what information we want to serialize from the data in the models.py
		- You should install Django rest framework and then add it to the APIProject -> settings.py => installed apps
		- ### ModelSerializer
			- 54:25
			- on the serializers.py file you should insert:
			- ```Python 
			  from rest_framework import serializers
			  from .models import Article
			  
			  class ArticleSerializer(serializers.ModelSerializer):
			      class Meta:
			          model = Article
			          fields = ['id', 'title', 'description']
			          
			  ```
			- Which will work using the already created Article model
	- ## Function Base API Views
		- 59:20
		-
	-