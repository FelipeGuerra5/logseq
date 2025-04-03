- # Rock Paper Scissors
	- First you want to set up your HTML
	- ```HTML 
	  <!DOCTYPE html>
	  <html lang="en">
	  <head>
	      <meta charset="UTF-8">
	      <meta http-equiv="X-UA-Compatible" content="IE=edge">
	      <meta name="viewport" content="width=device-width, initial-scale=1.0">
	      <title>Rock Paper Scissors</title>
	  </head>
	  <body>
	  
	      <h2>Computer Choice:<span id="computer-choice"></span></h2>
	      <h2>Your Choice<span id="user-choice"></span> </h2>
	      <h2>result<span id="result"></span></h2>
	  
	      <button id="rock">Rock</button>
	      <button id="paper">Paper</button>
	      <button id="scissors">Scissors</button>
	  
	      <script scr="app.js" charset="utf-8"></script>
	  </body>
	  </html>
	  ```
	- After that you should make the logic for it in the JS file so when you click the button can display your choice and the computer can calculate a choice ass well.
	- Get the location for Your choice, computer's choice and result
		- ```JS 
		  const computerChoiceDisplay = document.getElementById('computer-choice')
		  const userChoiceDisplay = document.getElementById('user-choice')
		  const resultDisplay = document.getElementById('result')
		  const possibleChoices = document.querySelectorAll('.button')
		  let userChoice
		  let computerChoice
		  let result
		  
		  possibleChoices.forEach(possibleChoice => possibleChoice.addEventListener('click', (e) => {
		      userChoice = e.target.id
		      let userChoiseStr = userChoice.toString()
		      userChoiceDisplay.innerHTML = userChoiseStr.toUpperCase()
		      generateComputerChoice()
		      getResult()
		  }))
		  
		  function generateComputerChoice() {
		      const randomNumber = Math.floor(Math.random() * possibleChoices.length) + 1
		      
		      switch(randomNumber) {
		          case 1:
		              computerChoice = 'rock'
		              break
		          case 2:
		              computerChoice = 'paper'
		              break
		          case 3:
		              computerChoice = 'scissors'
		              break
		      }
		  
		      computerChoiceDisplay.innerHTML = computerChoice
		  }
		  
		  function getResult() {
		      console.log(userChoice)
		      console.log(computerChoice)
		      if (userChoice === computerChoice) {
		          result = 'Draw!'
		      }
		      
		      result = userChoice ==='rock' && computerChoice === 'scissors' ? "You win": ""
		  
		      if (userChoice === 'paper' && computerChoice === 'rock') {
		          result = 'You win!'
		      }
		      if (userChoice === 'paper' && computerChoice === 'scissors') {
		          result = 'You Loose!'
		      }
		      if (userChoice === 'scissors' && computerChoice === 'paper') {
		          result = 'You win!'
		      }
		      if (userChoice === 'scissors' && computerChoice === 'rock') {
		          result = 'You loose!'
		      }
		      resultDisplay.innerHTML = result
		  }
		  ```
	- ## **Evaluation** By Nate
		- Qualidade do codigo
			- Bons nomes de variaveis (green flag)
			- Simples e direto ao ponto (green flag)
			  Pontos a melhorar
			- Variaveis globais sendo usadas em todas as funcoes em vez de as funcoes terem seus proprios parametros (big red flag)
			- Logica verbosa quando poderia ser bem mais conciso (yellow flag)
			  
			  Dev junior --
			  
			  Sem o big red flag: Dev junior ++
		- Com logica concisa: dev pleno
		-
		- Com um unico addEventListener para todos os botões e talvez usando "data-" e tendo css: dev senior