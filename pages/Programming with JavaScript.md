- #[[Meta - Front-end Development, Professional Certificate]]
- # Module 1
  collapsed:: true
	- ## Introduction to Programming with JavaScript
	  collapsed:: true
		- # Course syllabus
		  
		  This course is the second of a series that aims to help you learn more about web development. 
		  
		  In this course, you will explore the following:
			- **Module 1: Introduction to JavaScript**
			  
			  In this module, you are introduced to JavaScript. You'll learn why JavaScript is so integral to software development. And you'll get an overview of how to write JavaScript code inside the browser. Furthermore, you will learn about the most common operators as well as conditional statements and loops.
			  
			  After completing this module, you will be able to:
				- Explain the importance of JavaScript in software development
				- Demonstrate how to write JavaScript code inside the browser
				- Demonstrate how to write basic JavaScript code
				- List common operators, conditional statements and loops
				- Demonstrate how to use variables and output their value in the console
			- **Module 2: The building blocks of a program**
			  
			  Here you'll learn how to use objects, arrays and functions. In addition, you will learn about the most common built-in methods, and the difference between undefined, null and empty strings. And you'll explore both error handling and defensive programming.
			  
			  After completing this module, you will be able to:
				- Build and use objects, arrays, and functions
				- List some common built-in methods on built-in objects
					- Describe handling bugs and errors using try, catch, throw, and defensive programming
				- Explain the difference between undefined, null, and empty strings
				- Demonstrate how to write basic code using arrays, objects and functions
			- **Module 3: Programming paradigms**
			  
			  This module is about functional programming and the object oriented programming paradigm. You will learn what scope is in JavaScript. You'll explore the differences between var, let and const. And you'll learn how to use classes and inheritance in object oriented programming. Additionally, you'll explore how to use write JavaScript using modern features like spread and rest.  You will build code that can manipulate the DOM and handle events. And you will use JSON in JavaScript.
			  
			  After completing this module, you will be able to:
				- Outline the tenets of the functional programming and object oriented programming paradigm
				- Describe how scope works in JavaScript
				- List the differences between var, let, and const
				- Use classes and inheritance in OOP in JavaScript
				- Write JavaScript code using more modern features like spread, rest, template strings and modules
				- Build code that manipulates the DOM and handles events
				- Use JSON in JavaScript
			-
			- **Module 4: Testing and compatibility**
			  
			  Here you will learn about Node.js and npm. And you will explore how to install npm packages and how to work with package.json. Furthermore, you will learn about testing in JavaScript and you'll code a simple unit test in Jest.
			  
			  After completing this module, you will be able to:
				- Describe Node.js and npm
				- Explain how to install npm packages
				- Describe how to work with package.json
				- Explain the process of testing in JavaScript
				- List the three most prevalent kinds of testing
				- Demonstrate how to code a simple unit test in Jest
			- **Module 5: Graded assessment**
			  
			  In the final module, you'll learn about the graded assessment. After you complete the individual units in this module, you'll synthesize the skills you gained from the course to create code for the "Little lemon receipt maker ". 
			  
			  You'll also have to opportunity to reflect on the course content and the learning path that lies ahead
		-
	- ## Writing you first JS code
	  collapsed:: true
		- **ASI** -> Automatic Semi-Colon Insertion #[[Developer - Glossary]]
		- **ECMA** -> European Computer Manufactures Association #[[Developer - Glossary]]
		-
		-
- # Module 2
  collapsed:: true
	- ## Quiz
	  collapsed:: true
		- Question 1
		  collapsed:: true
		  What will be printed when the following code runs?
		  
		  ```JS 
		  var result = null;
		  console.log(result);
		  ```
		  1. undefined
		  2, null
		  3. 0
		  4. Correct #card
			- Null
		- Question 2
		  collapsed:: true
		  When the following code runs, what will print out?
		  
		  ```js 
		  try {
		  
		    console.log('Hello');
		  
		  } catch(err) {
		  
		    console.log('Goodbye');
		  
		  }
		  ```
		  1. Hello
		  2. Goodbye #card
			- Since there is no error thrown inside the  try  block, the catch  block  will not run. Therefore, "Hello" will print out.
		- Question 3
		  collapsed:: true
		  If you pass an unsupported data type to a function, what error will be thrown?
		  
		  1. RangeError
		  2. SyntaxErrror
		  3. TypeError #card
			- TypeError will be thrown when an incorrect data type is passed to a function.
		- Question 4
		  collapsed:: true
		  What will print out when the following code runs?
		  
		  ```js 
		  var x;
		  
		  if(x === null) {
		  
		    console.log("null");
		  
		  } else if(x === undefined) {
		  
		    console.log("undefined");
		  
		  } else {
		  
		    console.log("ok");
		  
		  }
		  
		  ```
		  
		  
		  1. null
		  2. undefined
		  3. ok #card
			- Since the value is not initialised, it will have the undefined data type.
		- Question 5
		  collapsed:: true
		  What will print out when the following code runs?
		  
		  ```js 
		  throw new Error();
		  
		  console.log("Hello");
		  ```
		  
		  1. Hello
		  2. Nothing will print out. #card
			- Throwing an error will stop the execution of the code, therefor Nothing will print out.
- # Module 3
  collapsed:: true
	- ## Functional Programming
	  collapsed:: true
		- ### Paradigms
			- **Functional Programming**
				- Functions and variables  are set and used outside objects
			- **Object-oriented Programming**
				- Both variables and methods are declared and used inside the object.
	- ## High-order Function, Functional Programming
	  collapsed:: true
		- A **higher-order function** is one that either:
			- *Receives a function* as param
			- *Return a function* as Response
		- Pure Function and Side-effects
			- **Pure function** -> Return the same for same Params
			- **Side-Effect** -> Every change a function does outside itself, console.log or changing variables.
	- ## Constructor
	- ## Regular Expressions
	  collapsed:: true
		- #regularexpressions
			- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
			- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp
	- ## De-structuring
	  collapsed:: true
		- You can extract the value of a object from it using a variable as the following:
			- ```js 
			  let {PI} = Math
			  PI //3.1415 ...
			  ```
			- This extract the value of the Math.PI to the PI Variable and although equal is not the same value.
		- ## Iterate Objects in | of
			- ```js 
			  for (prop in sportsCar) {
			    ... will run all the props on SportsCar and Super
			  }
			  
			  for (prop of Object.keys(sportsCar)) {
			    ... will iterate all the props only of sportsCar
			    MUST use the Object.keys(sportsCar) to make it possible
			  }
			  ```
	- ## Spread Operator
	  collapsed:: true
		- ```js 
		  const isSummer = false;
		  const fruits = {
		    apple: 10,
		    banana: 5,
		    ...(isSummer && { watermelon: 30 }),
		  };
		  ```
	- ## DOM Manipulation
	- ## JavaScript Selectors
	  collapsed:: true
		- ```js 
		  document.querySelector('p') // -> will Select the FIRST p tags in the page
		  
		  document.querySelectorAll('p') // -> will select all the p tags in the page
		  
		  // You can use also id and class to target a element
		  document.getelementById('heading')
		  document.getElementsByClassName('txt')
		  
		  //only caviat is that the element is singular in id and is plural in class
		  ```
		-
	- ## Event Handling
	  collapsed:: true
		- AddEventListener
			- ```js 
			  const target = document.querySelector('body')
			  
			  function handleClick() {
			    console.log("clicked the body")
			  }
			  
			  target.addEventListener('click', handleClick)
			  ```
	- ## Json
		- ```js 
		  const jsonStr = '{"greeting": "hello"}'
		  
		  const aPlainObj = JSON.parse(jsonStr)
		  aplainObj.greeting = 'hi'
		  
		  const data = {
		    fistName: "John",
		    lastname: "Doe",
		    greeting: "Hello",
		  }
		  
		  JSON.stringfy(data)
		  
		  ```
- # Module 4
  collapsed:: true
	- ## NodeJS
	  collapsed:: true
		- Is the JS adapted to be used in the back-end
		- **NPM** -> Node Package Manager #[[Developer - Glossary]]
	- ## Testing
	  collapsed:: true
		- JEST
			- ```js 
			  expect(concatStrings("123", "456")).toBe("123456")
			  ```
	- ## Types of Testing
	  collapsed:: true
		- Usually a requirement is the base of a testing
			- E2E -> Imitate how a user would interact with the app, entire finished product, (slow, costly)
			- Integration -> How two parts of a software work together (average, moderated cheap)
			- Unit -> Smallest peace of code that can be tested, usually a function, method (fast, cheap)
	- ## Introduction to Jest
	  collapsed:: true
		- Jest is a framework for testing maintained by Meta, can also test TypeScript.
		- **Mocking** -> Separating code from related dependencies during testing
			- Using data, simulating the back-end to test the front-end.
			- Compatible with async functionality
		- **Snapshot Testing** -> Use by web developers to verify that are no regressions in the DOM
			-
	- ## Writing tests with Jest
	  collapsed:: true
		- Confirm if you have Jest installed `jest --version`
		  logseq.order-list-type:: number
		- Start a Node project with `npm init -y`
		  logseq.order-list-type:: number
		- Install Jest locally with `npm install --save-dev jest`
		  logseq.order-list-type:: number
		- On packege.json change the param: `script.test` from: `"test": "echo \"Error: no test specified\" && exit 1"` to: `"test": "jest"`
		  logseq.order-list-type:: number
		- First Jest Testing Script
			- File addFive:
				- ```js 
				  function addFive(val) {
				      return val + 5
				  }
				  
				  module.exports = addFive
				  ```
			- File AddFive.test.js
				- ```js 
				  const { default: TestRunner } = require("jest-runner")
				  const addFive = require("./addFive")
				  
				  test('Returns the number plus 5', () => {
				      expect(addFive(1)).toBe(6)
				  })
				  
				  ```
			- **Run it**
				- `npm run test` or `npx jest`
			- Results:
				- ```js
				  $ npm run test
				  
				  > jest_testing@1.0.0 test
				  > jest
				  
				   PASS  ./addFive.test.js
				    √ Returns the number plus 5 (3 ms)
				                                                                                                                                                                    
				  Test Suites: 1 passed, 1 total                                                                                                                                    
				  Tests:       1 passed, 1 total                                                                                                                                    
				  Snapshots:   0 total
				  Time:        0.364 s, estimated 3 s
				  Ran all test suites.
				  ```
			- **Code Coverage**
				- `npx jest --coverage` or `yarn jest --coverage`
				-
	- ## TDD -> Test Driven Development
	  collapsed:: true
		- Make a test that is going to fail, based on the requierements
		  logseq.order-list-type:: number
		- Make the functionality to fulfil the test
		  logseq.order-list-type:: number
		- Run the test, pass Expected
		  logseq.order-list-type:: number
		-
- # Module 5
	- ## Exertcice
		- FAILED Test Case: getPrices method applies tax when taxBoolean parameter is true
		  background-color:: red
		  collapsed:: true
			- **Your Code Produced:**
				- Dish: Italian pastaPrice: $11.46\nDish: Rice with veggiesPrice: $10.38\nDish: Chicken with potatoesPrice: $18.66\nDish: Vegetarian PizzaPrice: $7.74\n
			- **Expected Output Is:**
				- Dish: Italian pasta Price: $11.46
				  Dish: Rice with veggies Price: $10.38
				  Dish: Chicken with potatoes Price: $18.66
				  Dish: Vegetarian Pizza Price: $7.74
		- FAILED Test Case: getPrices method does not apply tax when taxBoolean parameter is false
		  background-color:: red
		  collapsed:: true
			- **Your Code Produced:**
				- Dish: Italian pastaPrice: $9.55\nDish: Rice with veggiesPrice: $8.65\nDish: Chicken with potatoesPrice: $15.55\nDish: Vegetarian PizzaPrice: $6.45\n
			- **Expected Output Is:**
				- Dish: Italian pasta Price: $9.55
				  Dish: Rice with veggies Price: $8.65
				  Dish: Chicken with potatoes Price: $15.55
				  Dish: Vegetarian Pizza Price: $6.45
		- Passed: getPrices method logs expected error message when taxBoolean is not supplied
		  background-color:: green
		- FAILED Test Case: getDiscount method when tax is applied and guests less than 5
		  background-color:: red
		  collapsed:: true
			- **Your Code Produced:**
				- Dish: Italian pastaPrice: $11.46\nDish: Rice with veggiesPrice: $10.38\nDish: Chicken with potatoesPrice: $18.66\nDish: Vegetarian PizzaPrice: $7.74\nDiscount is: $5\n
			- **Expected Output Is:**
				- Dish: Italian pasta Price: $11.46
				  Dish: Rice with veggies Price: $10.38
				  Dish: Chicken with potatoes Price: $18.66
				  Dish: Vegetarian Pizza Price: $7.74
				  Discount is: $5
		- FAILED Test Case: getDiscount method when tax is applied and guests more than 5
		  background-color:: red
		  collapsed:: true
			- Your Code Produced:
				- Dish: Italian pastaPrice: $11.46\nDish: Rice with veggiesPrice: $10.38\nDish: Chicken with potatoesPrice: $18.66\nDish: Vegetarian PizzaPrice: $7.74\nDiscount is: $10\n
			- ExpectedOutput Is:
				- 'Dish: Italian pasta Price: $11.46
				  Dish: Rice with veggies Price: $10.38
				  Dish: Chicken with potatoes Price: $18.66
				  Dish: Vegetarian Pizza Price: $7.74
				  Discount is: $10
		- FAILED Test Case: getDiscount method when tax is not applied and guests less than 5
		  background-color:: red
		  collapsed:: true
			- **Your Code Produced:**
				- Dish: Italian pastaPrice: $9.55\nDish: Rice with veggiesPrice: $8.65\nDish: Chicken with potatoesPrice: $15.55\nDish: Vegetarian PizzaPrice: $6.45\nDiscount is: $5\n
			- **Expected Output Is:**
				- Dish: Italian pasta Price: $9.55
				  Dish: Rice with veggies Price: $8.65
				  Dish: Chicken with potatoes Price: $15.55
				  Dish: Vegetarian Pizza Price: $6.45
				  Discount is: $5
		- FAILED Test Case: getDiscount method when tax is not applied and guests more than 5
		  background-color:: red
		  collapsed:: true
			- Your Code Produced:
				- Dish: Italian pastaPrice: $9.55\nDish: Rice with veggiesPrice: $8.65\nDish: Chicken with potatoesPrice: $15.55\nDish: Vegetarian PizzaPrice: $6.45\nDiscount is: $10\n
			- Expected Output Is:
				- Dish: Italian pasta Price: $9.55
				  Dish: Rice with veggies Price: $8.65
				  Dish: Chicken with potatoes Price: $15.55
				  Dish: Vegetarian Pizza Price: $6.45
				  Discount is: $10
		- FAILED Test Case: getDiscount method logs expected error message when guests count not in range
		  background-color:: red
			- Your Code Produced:
				- Dish: Italian pastaPrice: $11.46\nDish: Rice with veggiesPrice: $10.38\nDish: Chicken with potatoesPrice: $18.66\nDish: Vegetarian PizzaPrice: $7.74\nThe second argument must be a number between 0 and 30\n
			- Expected Output Is:
				- Dish: Italian pasta Price: $11.46
				  Dish: Rice with veggies Price: $10.38
				  Dish: Chicken with potatoes Price: $18.66
				  Dish: Vegetarian Pizza Price: $7.74
				  The second argument must be a number between 0 and 30