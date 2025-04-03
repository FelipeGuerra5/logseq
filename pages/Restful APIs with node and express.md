# Module 1
	- REST Representation State Transfer
		- For it represents states through data and the state is changed with transfer of this representations between clients and servers. Term coined by **Roy Fielding in 2000**]
		- REST does not enforce any rule regarding how it should be implemented at the lower level, it just put high-level design guidelines and leaves us to think of our own implementation.
		- ```JS 
		  GET
		  POST
		  PUT
		  DELETE
		  ```
- # Module 2
	- ## Detailing
	  collapsed:: true
		- **MongoDB** Stands for **Humongous**, was developed by *Dwight Merriman* and *Eliot Horowitz* in 2007 to supply the market with a horizontally and vertically scalable 
		  DB.
		- It's a NoSQL solution that provides flexible, scalable and high-performance solution for storing and retrieving data.
		- **Suitable for:**
			- Content Management Systems
			  logseq.order-list-type:: number
			- IoT
			  logseq.order-list-type:: number
			- Social Networking Platforms
			  logseq.order-list-type:: number
			- E-commerce Systems
			  logseq.order-list-type:: number
	- ## RDBMS vs MongoDB
	  collapsed:: true
		- RDBMS tables with indexes
			- Data Integrity
			- SQL -> Structured Query Language
			- ACID transactions
			- Joins and Relationship
		- ### Differences
			- **Data Model:** while the RDBMS uses tables with indexes to store data the MongoDB used JSON like structures to store it
			- **Scalability:** whereas RDBMS are quite difficult to scale horizontally the MongoDB can be simpler to scale for the data does not requires defining tables and it's constrains
			- **Schema and Flexibility:** RDBMS uses predefined schemas whereas MongoDB does not need a predefined schema to work.
			- **Querying and Joins:** While SQL and joins are used to merge data together in RDBMS the MongoDB uses embedding, inserting the data into another data structure
				- ```SQL 
				  SELECT * FROM users WHERE age > 25;
				  ```
				- ```js 
				  db.users.find({ age: { $gt: 25 } });
				  ```
			-
	- ## Covered Queries
		- Optimization techniques that retrieve query results using only the index data, without accessing the actual documents.
		- Usually used with large collections and were performance optimization is required.
		-