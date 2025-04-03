- [[Web Dev]] [[JavaScript]]
-
- ## Scope
	- Beginners:
		- Block Scope
		- Function Scope
		- Globe Scope
	- For the case of nested functions:
		- The functions declared inside other can access the variables declared on their parents scope
		- Take the code bellow for example of **Scope**: #card
			- ```javascript 
			  let a = 10
			  function outer() {
			      let b = 20
			      function inner() {
			          let c = 30
			          console.log(a, b, c)
			      }
			      inner()
			  }
			  outer()
			  ```
			- it will log => 10 20 30. that is because all the **nested functions** have **access** to it's **parents scope** variables.
- ## Closure
	- A closure is the combination of a function bundle together with references to its surrounding state. Closure are created every time a function is created, at function creation time
	- Take the **Closure** example: #card
		- ```javascript 
		  function outer() {
		    let counter = 0
		    function inner() {
		      counter++
		      console.log(counter)
		    }
		    inner()
		  }
		  outer()
		  outer()
		  ```
		- The result of this log is 1 and 1 for each time the outer function is called the counter variable is started again on that call
	- To take the best of this we can return the inner function on the outer function like this:
		- Example of Closure 02 => Returning Functions #card
			- ```javascript 
			  function outer() {
			    let counter = 0
			    function inner() {
			      counter++
			      console.log(counter)
			    }
			    return inner
			  }
			  
			  const fn = outer()
			  fn()
			  fn()
			  ```
			- It will log => 1 and 2 for the function inner is return on the outer that can be made a variable and reused.
			- The function when returned not only returns a function but the function scope variables as well
	-
- ## Function Currying
	- Makes f(a, b, c) => f(a)(b)(c)
	- The problem is that we need a way to reuse functions and call multiple times without changing the result each time. or group all variable and pass it one single time.
	- ```Javascript 
	  function curry(fn) {
	    return function(a) {
	      return function(b) {
	        return function(c){
	        	 return fn(a, b, c)
	        }
	      }
	    }
	  }
	  
	  const curryedSum = curry(sum)
	  const add2 = curriedSum(2)
	  const add3 = add2(3)
	  const add5 = add5(5)
	  ```