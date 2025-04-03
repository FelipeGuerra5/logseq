- # The main difference
  collapsed:: true
	- ## Renderig
		- The main difference between the React and the NextJS framework is the Rendering
			- React -> renders in the client side,
			- Next.JS -> you can choose where.
		- The main problem s not only speed but the SEO as well, so the engines suffer with the client side renders only.
	- ## Routing
		- Next.JS -> The routing in the Next.JS uses the name of the files as the path to the pages in the website.
		- React -> Have to download the React Router Dom to make the routes to your webSite
	- ## FullStack Application
		- ### API routes
			- Servless APIs in the Next.JS are a way of creating API endpoints.
			- Just create a `route.js` in the desired folder you need.
	- ## Automatic code Splinting
		- React -> the process is manual
		- Next.JS -> only the code for the chosen page is loaded resulting a much faster application.
	- ## Best Feature
		- Still just React. More like a extension of react.
<<<<<<< HEAD
- # Building the App
	- ## First Steps
		- `npx create-next-app@latest ./` -> to create in the current directory
	- ## Layout.js file
		- This file is responsible for:
			- The configuration of HTML and Metadata
			- It access all the pages on your application. It should be used in case of a footer or a navbar
			-
||||||| 82b5cf4
		-
=======
- # Building
  collapsed:: true
	- ## Layout.js
		- In this file you can insert the code that should be present in all the pages on your application.
			- foote, navbar, asides and so on.
			- Also you can add change configuration for you main HTML in this file an change metadata as well.
	- ## App dir.
		- All the .js files in the App folder are considered react server components.
		- to change it to render in the client side you need to insert the `"Use client"` on the top of the file.
	- ## State management
		- Is a client side always.
	- ## Client vs, Server Side
		- Always use server side components until there is a  necessity to use client side components.
	- ## Routing
		- The routing is as simple as creating a page in the App folder.
		- For each folder you create a `domain</pagename>` will be added to your website.
		- In order to make nested paths you just need to create a new directory inside the already created folder for that given path.
		- ### Dynamic paths:
			- To achieve dynamic routes you need to create a dir encapsulated in brackets:
				- `[nameofvar]` and then insert you code in a file inside it.
		- ### Recycle components on a specific route
			- You can create a new `layout.js`, this will make it available in every page you need under that path (directory).
	- ## Especial file names
		- ### Loading
			- You can create a `loading.js` and that will be displayed in the case of a slow loading page.
		- ### Errors
			- You can create a `errors.js` file so when a error occurs it can be displayed to the client without problem.
	- ## Data Fetching
		- ### Server Side rendering (SSR)
			- It's rendered fresh in each request on the server side.
			- Won't cache the data fetched
			- ```js 
			  async function Page ({ params }){
			    const rest = await fetch(
			    	"http.../${params.id}",
			    	{cache: 'no-store'}
			    );
			    const data = await res.json()
			  
			    return (
			    	<div>data.title</div>
			    )
			  }
			  ```
		- ### Static Side Generation (SSG)
			- Will fetch the data and also cache it -> ideal when using content that doesn't change frequently
			- ```js 
			  async function Page ({ params }){
			  	const rest = await fetch(
			  		"http.../${params.id}",
			  		// by supressing the no-cache statement it will be cached automatically
			  	);
			  	const data = await res.json()
			  	return (
			  		<div>data.title</div>
			  	)
			  }
			  ```
		- ###  Incremental Static Generation (ISG)
			- It combines the benefits of the previous two
			- The data will be cached, however after a predetermined time it will be refreshed again.
			- ```js 
			  async function Page ({ params }){
			  	const rest = await fetch(
			  		"http.../${params.id}",
			        	// This will make it fetch again after 10 sec if changed.
			  		{next: { revalidate: 10 } } 
			  	);
			  	const data = await res.json()
			  	return (
			  		<div>data.title</div>
			  	)
			  }
			  ```
		- ## FullStack Functionality
			- Using the same routing system as the pages you can create the API's.
			- You can create a ExpressJS back-end server, importing managing the data and them listening to a specific port.
			- ### In Next.JS
				- #### Defining a rout handling
					- You can both create a rout for back-end just besides the page file, however the Next.JS won't know what is the correct rout it should display and it will clash both
					- Alternatively you can use a specific `api` directory that contain all the code and API for the back-end of your page.
					- Next.JS already support the following HTTP methods:
						- GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS.
					- **To use this method you just have to**
						- make a GET function and start writing you back-end code
						- ```js 
						  export async function GET(request) {
						    // Handle the GET request for /api/users
						    // Retrive users from the data base or any data source
						    const users = [
						      {id: 1, name: 'Bob'},
						      {id: 2, name: 'Jonh'},
						      {id: 3, name: 'Mike'}
						    ]
						    // Send the users as a response
						    return new Response(JSON.stringify(users))
						  }
						  ```
						- In the same file you can also make use all the other http verbs.
						-
		- ## Improving SEO
			- using the metadata you can give a title for a page or even with a async function you can generate multiple title for multiple products improving the SEO for the given page.
			- ```js 
			  const metadata = {
			    title : 'Home'
			  }
			  
			  // this will make:
			  // <head>
			  //   <title>Home</title>
			  // </head>
			  ```
- # The actual build
	- Installing dependencies
		- `npm install bcrypt`
>>>>>>> fd39df65dcdb0d5bd42cc53ea3da392a98dac28a
