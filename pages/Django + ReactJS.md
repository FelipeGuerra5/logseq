- [[Web Dev]]
-
- ### Full Stack Project with React.js and Django (Task Manager Application)
	- https://www.youtube.com/watch?v=F5OUT3ijk8M&t=9s
-
- ## Steps for Back-end
	- ### Usual stuff
		- virtual enviroment:
			- `python -m venv venv`
			- `venv/Scripts/activate`
			- `python -m pip install --upgrade pip`
	- ### Installing
		- `pip install django`
		- `django-admin startproject backend`
	- ### Start Dajngo App
		- `cd backend`
		- `python manage.py startapp todo`
		- `python manage.py migrate`
		- Add the todo to the INSTALLED APPS on the backend -> setting.py
	- ### Create a model under todo app dir:
	  id:: 63f36382-dfe1-43ff-82eb-5b9d428db3f1
		- ```python 
		  from django.db import models
		  
		  # Create your models here.
		  
		  # Model with all the typess of data types
		  class Todo(models.Model):
		      title = models.CharField(max_length=120)
		      description = models.CharField(max_length=120)
		      completed = models.BooleanField(default=False)
		  
		      # Return the string for each model, in this case the title above.
		      def __str__(self):
		          return self.title
		  ```
		- Note: every time you change anything that concerns DB you should do:
			- `python manage.py makemigrations`
			- `python mange.py migrate`
		- ### Insert the model under todo -> admin.py
			- ```Python 
			  from django.contrib import admin
			  from .models import Todo
			  
			  # Register your models here.
			  
			  class TodoAdmin(admin.ModelAdmin):
			      list_display = (
			          'title',
			          'description',
			          'completed'
			      )
			  
			  # Register model
			  admin.site.register(Todo, TodoAdmin)
			  
			  ```
	- ### Create Super User.
		- `python manage.py createsuperuser`
			- insert the required information
			- run server: `python manage.py runserver`
			- on the local host port: 8000/admin
				- Log in and see if the user is created as well as the todo model
	- ### Creating the API
		- `pip install djangorestframework`
		- `pip install django-cors-headers`
		- Add it to INTALLED_APPS in Backend -> settings.py
		- Make a CORS_ORRIGIN-WHITELIST in settings.py as well
			- ```Python 
			  # Application definition
			  
			  INSTALLED_APPS = [
			      'django.contrib.admin',
			      'django.contrib.auth',
			      'django.contrib.contenttypes',
			      'django.contrib.sessions',
			      'django.contrib.messages',
			      'django.contrib.staticfiles',
			      'todo',
			      'rest_framework',
			  ]
			  ```
			- Somewhere on this file insert a whitelist for the default port for React
				- ```python 
				  # Whitelisting React Port
				  CORS_ORIGIN_WHITELIST = (
				      'http://localhost:3000'
				  )
				  ```
	- ### Serializing
		- Under todo -> `touch serializers.py`
			- ```Python 
			  from rest_framework import serializers
			  from .models import Todo
			  
			  class TodoSerializer(serializers.ModelSerializer):
			    class Meta:
			      model = Todo
			      field = (
			        'id',
			        'title',
			        'description',
			        'completed'
			      )
			  ```
		- Under view.py insert the serializer:
			- ```python 
			  from django.shortcuts import render
			  
			  from rest_framework import viewsets
			  from .serializers import TodoSerializer
			  from .models import Todo
			  
			  # Create your views here.
			  
			  class TodoView(viewsets.ModelViewSet):
			      serializer_class = TodoSerializer
			      queryset = Todo.objects.all()
			      
			  ```
		- Under Backend -> urls.py include the serialization for the todo
			- ```python 
			  from django.contrib import admin
			  from django.urls import path, include
			  from todo import views
			  from rest_framework import routers
			  
			  router = routers.DefaultRouter()
			  router.register(r'tasks', views.TodoView, 'task')
			  
			  urlpatterns = [
			      path('admin/', admin.site.urls),
			      path('api/', include(router.urls))
			  ]
			  ```
		- Under Backend -> settings.py:
			- MIDDLEWARE =>
			- `'corsheaders.middleware.CorsMiddleware'`
		-
- ## Steps for Front-End
	- Understand JavaScript
		- [[JavaScript]]
	- In the main file:
		- `npx create-react-app`
		- `npm install reactstrap boostrap`
		- Import boostrap under src -> index.js
			- ```JavaScript
			  import 'bootstrap/dist/css/bootstrap.min.css'
			  ```
		- Main focus of work in the src -> App.js file
			- ```javascript 
			  import React, {component} from 'react'
			  import './App.css';
			  
			  // For building purpose only
			  const tasks = [
			    {
			      "id": 1,
			      "title": "Todo test 001",
			      "description": "Description of test 001",
			      "completed": false
			    },
			    {
			      "id": 2,
			      "title": "Todo Test 002",
			      "description": "Todo Description 002",
			      "completed": false
			    },
			    {
			      "id": 3,
			      "title": "Todo Test 003",
			      "description": "Todo Description 003",
			      "completed": true
			    }
			  ]
			  
			  class App extends Component {
			    constructor(props) {
			      super(props);
			      this.state = {
			        viewCompleted:false,
			        taskList: tasks // For building purpose only after will be changed for the API data
			      }
			    }
			  }
			  
			  export default App;
			  ```
		- Inside the class App insert the component:
			- #### Display completed
				- ```javascript 
				    displayCompleted = status => {
				      if (status) {
				        return this.setstatus({ viewCompleted:true });
				      }
				      return this.setstatus({ viewCompleted:false });
				    }
				  ```
			- #### RenderTabList
				- ```javascript 
				    renderTabList = () => {
				      return (
				        <div className='my-5 tab-list'> // Bootstrap class for Y axis margin
				          <span
				            onClick={() => this.displayCompleted(true)}
				            className={this.state.viewCompleted ? "active" : ""}
				  		>
				            Completed
				          </span>
				          <span
				          onClick={() => this.displayCompleted(false)}
				          className={this.state.viewCompleted ? "" : "active"}
				          >
				            Incompleted
				          </span>
				        </div>
				      )
				  ```
			- #### RenderItems
				- ```javascript 
				    // rendering item in the list (Completed || Incompleted)
				    renderItems = () => {
				      const { viewCompleted } = this.state;
				      const newItems = this.state.taskList.filter(
				        item => item.completed == viewCompleted
				      )
				    }
				  ```
			- #### render
				- So the items can be shown in the screen
				- ```javascript 
				    // Showing on the screen
				    render() {
				      return (
				        <main className="context">
				        <h1 className="text-black text-uppercase text-center my-4"> task Manager </h1>
				        <div className="row">
				          <div className="col-md-6 clo-sma-10 mx-auto p-0">
				            <div className="card p-3">
				              <div>
				                <button className="btn btn-warning">Add task</button>
				              </div>
				              {this.renderTabList()}
				              <ul className="list-group list-group-flush"></ul>
				                {this.renderItems()}
				            </div>
				          </div>
				        </div>      
				      </main>
				      )
				    }
				  ```
			- #### Render Items add a Return
				- ```JavaScript 
				  return newItems.map(item => (
				        <li key={item.id} className="list-group-item d-flex justify-content-between align-items-center">
				          
				          <span className={`todo-title mx-2 ${this.state.viewCompleted ? "completed-todo" : ""}`}
				            title={item.title}>
				              {item.title}
				          </span>
				          <span>
				            <button className="btn btn-info mr-2">Edit</button>
				            <button className="btn btn-danger m-2">Delete</button>
				          </span>
				        </li>
				      ))
				  
				  ```
			- On the **index.css** file:
				- ```css 
				  body {
				    margin: 0;
				    padding: 0;
				    font-family: sans-serif;
				  }
				  
				  .todo-title{
				    cursor:pointer;
				  }
				  
				  .completed_todo{
				    text-decoration: line-through;
				  }
				  
				  .tab-list > span {
				    padding: 5px 8px;
				    border: 1px solid rgb(13, 159, 204);
				    border-radius: 10px;
				    margin-right: 20px;
				    cursor:pointer;
				  }
				   .tab-list>span.active {
				    background-color: rgb(13, 159, 204);
				    color: #fff;
				   }
				  ```
			- On the **src dir** `mkdir components` and `touch Modal.js`
				- Them import for reactstrap and make the handleChange
				- ```javascript 
				  import React, { Component } from 'react'
				  
				  import {
				      Button,
				      Modal,
				      ModalHeader,
				      ModalBody,
				      ModalFooter,
				      Form,
				      Formgroup,
				      Input,
				      Label
				  } from 'reactstrap'
				  
				  class customModal extends Component {
				      constructor(props) {
				          super(props);
				          this.state = {
				              activeItem: this.props.activeItem
				          };
				      }
				  
				      handleChange = e => {
				          let { name, value } = e.target;
				          if (e.target.type === "checkbox") {
				              value = e.target.checked;
				          }
				          const activItem = {...this.state.activeItem, [name]: value};
				          this.setState({ activItem })
				      };
				    
				  }
				  ```
				- STOPED at 52:39
				- Running in to not understanding so I think I should get a better understanding of JS
				-