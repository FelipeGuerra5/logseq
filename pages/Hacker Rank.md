# Month Preparation
	- ## Lonely Integer
	  collapsed:: true
		- Find the lonely integer of a given array
		  collapsed:: true
		  only odd array and with only one lonely integer 
		  Difficulty: Easy
		  #card
			- ```js 
			  function lonelyinteger(a) {
			      // Write your code here
			      
			      const count = {}
			      
			      for (let num of a)     {
			          count[num] = (count[num] || 0) + 1
			      }
			      
			      for (let num in count) {
			          if ( count[num] === 1) {
			              return (num)
			          }
			      }
			  }
			  ```
			- I forgot that to go through the actual numbers in a array you can use the `for(let item of arr) {}`
			  background-color:: red
- # Cards
	- {{cards [[Hacker Rank]]}}
	-