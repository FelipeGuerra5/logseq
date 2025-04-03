- [[Mackenzie]] [[3_Semester]] [[Data]]
-
- ## Information
	- Teacher: SOLANGE DUARTE PALMA DE SA BARROS
-
- # Aula 1
  collapsed:: true
	- ![Text](../assets/mack/Estrutura de Dados/N_EST DAD_A1 – Texto de Apoio.pdf)
	-
	- ### TAD - tipo abstrato de dados
		- Is the part of the data that is a representation of the real life data in the Data Base
		- #### Características típicas de TADs #card
		  collapsed:: true
			- 1. Independe da linguagem de programação.
			  2. É conceito básico para programação Orientada a Objetos.
			  3. A manipulação do dado se faz unicamente por meio das operações definidas para ele.
			  4. Não é preciso saber a forma exata de implementação do tipo ou de suas operações para conseguir utilizá-los.
			  5. A definição é independente da implementação, podendo ser alterada sem que o uso se modifique.
			  6. A aplicação não precisa (e não deve) ter acesso à forma de implementação. Portanto, somente após a definição estar completa é que devemos começar a pensar na implementação exata do tipo e suas operações.
	- ### Algorithms
		- The cost of each type of algorithm can be calculated either by testing it (bring variability with different hardware) and Mathematically.
		- When we get a function that compare all the numbers in one Array we are dealing with a (n - 1) problem, which means the operation will happen n - 1 times were n is the number of items in the array.
		- For a function that find the number index in the array the operation will happen (n +1)/2 that is because, although the function has to check each number of the array, probability dictates that most of the times will be in the middle so we take the average of all the possibilities
	- ### Asymptotic Math
		- Is the math that studies the n^2 type of functions
		- To facilitate the understanding the Big O notation as is usually called studies how fast a function will tend to infinity.
		- E.g.
			- f(n) = O(1) Constant complexity
			- f(n) = O(n) Linear Complexity
			- f(n) = O(n^2) Quadraticall Complexity
			- f(n) = O(log n) Logarithmic Complexity
			- f(n) = O(n log n) Logarithmic Liner Complexity
			- f(n) = O(2^n) Exponential Complexity
			- f(n) = O(n^3) Cubic Complexity
			-
			- If we have to repeat the same function for 10^5 time:
				- | **Ordem de complexidade** | **Tempo consumido** |  |
				  | ---- | ---- | ---- |
				  | O (log n) |            2*10^-4 | segundo |
				  | O(n) |            0,1 | segundo |
				  | O(n log n) |            2 | segundos |
				  | O(n2) |            3 | horas |
				  | O(n3) |            32 | anos |
				  | O(2n) |  | séculos |
	- ### Ponto de Partida
		- **Unsolvable problems:**
		- The problem of the travelling merchant
			- He has to visit 4 cities and we have to find the smaller route
			- For each possibility the permutations bring (n-1)!
			- Which means that for only 25 cities a function would take 47.500 years
		- **Solvable problems**
	- ![](https://eadgrad.mackenzie.br/pluginfile.php/661315/mod_hvp/content/1134/images/image-607f23d48c91e.jpg)
	-
-
- # Aula 2
  collapsed:: true
	- ### Listas
		- General linear arrays-> No discipline of access
		- Quantity of elements is lower than the capacity of the array
		- `empty(7)` -> return am array with 7 places
		- `isEmpty()` -> returns Boolean and if false does not mean is full
		- `add(possition, element)` -> only adds to an array cannot skip positions
		- `set(position, element)` -> it changes the item in this position for the give one
		- `search(i)` -> either returns the index for the item or -1 for not found value
		- `.equals(n)` -> means == for strings
		-
		-
	- ### Texto de apoio
		- ![text](.../assets/mack/Estrutura de Dados/N_EST DAD_A2 – Texto de Apoio.pdf)
		-
	- ### Professor resolve
		- Exercise: receives an csv with criteria for Netflix in different countries
		- ```java 
		  package projectnetflix;
		  
		  public class Pais {
		    String nomePais;
		      double tarifaBasica;
		      double tarifaStandart;
		      double tarifaPremium;
		  
		    public Pais(String nomePais, double tarifaBasica, double tarifaStandart, double tarifaPremium) {
		      this.nomePais = nomePais;
		      this.tarifaBasica = tarifaBasica
		      this.tarifaStandart = tarifaStandart
		      this.tarifaPremium = tarifaPremium
		    }
		  	public void  mostraPais(){
		        System.outt.println("Pais " + nomePais);
		        System.outt.println("Tarífa Basica: " + tarifaBasica);
		        System.outt.println("Tarífa Strandeard: " + tarifaStandard);
		        System.outt.println("Tarífa Premium: " + tarifaPremium);
		      }
		  
		  }
		  ```
		- ```java 
		  import java.util.*;
		  import java.io.*;
		  
		  public class ReadTxt {
		      public static void main(String[] args) throws Exception {
		          ArrayList <Aluno> lista = new ArrayList<>();
		          
		          // carga do arquivo txt.
		          FileReader data = new FileReader("./_files/alunos.txt");
		          try (BufferedReader linha = new BufferedReader(data)) {
		              String aux = linha.readLine();
		  
		              while (aux != null) {
		  
		                  String[] dados = aux.split(";");
		                  Aluno novo = new Aluno(
		                      Integer.parseInt(dados[0]),
		                      dados[1],
		                      Double.parseDouble(dados[2])
		                  );
		                  lista.add(novo);
		                  aux = linha.readLine();
		              }
		          }
		          mostrarLista(lista);
		          Double media = calcularMedia(lista);
		          notasMaioresMedia(lista, media);
		      
		      }
		  
		      public static void mostrarLista(ArrayList<Aluno> lista){
		          for (int i =0; i<lista.size();i++) {
		              lista.get(i).mostrarAluno();
		              var nota = lista.get(i).getNota();
		              System.out.println(nota);
		          }
		      }
		  	
		    	//  Calculate and retuns the Average for the grades.
		      public static Double calcularMedia(ArrayList<Aluno> lista) {
		          Double soma = 0.0;
		          int lenght = lista.size();
		  
		          for (int i=0; i<lista.size() ; i++) {
		              soma += lista.get(i).getNota();        
		          }
		          Double media = soma / lenght;
		          System.out.println("Media das notas = " + media);
		          return media;
		      }
		  
		      // Print's the asked response.
		    	public static void notasMaioresMedia(ArrayList<Aluno> lista, Double media) {
		          for (int i = 0; i<lista.size(); i++) {
		              Double nota = lista.get(i).getNota();
		              if (nota >= media) {
		                  System.out.println("Nota maior que a media => " + nota);
		              }
		          }
		      }
		  
		  }
		  
		  ```
		- STOPED at https://rec.elos.vc/playback/presentation/2.3/50e7e188c65853c3344110005cdcfda445e233d1-1677534782727
		- -10:40
		-
-
- # Aula 3
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Estrutura de Dados/N_EST DAD_A3 – Texto de Apoio.pdf)
	- ## Ponto de Partida
		- ### **Linear Search vs. Binary Search**
			- the linear search increases the number of comparisons depending on the size of the sample, as the binary search increase as of (log N)  for the size of the sample, as the sample doubles the number of comparations increase only a constant.
		- ### **Sorting vectors** - BubbleSort, InsertionSort and SelectionSort.
			- Although the Insertion Sort has a half of the comparisons of the Bubble Sort and the Selection Sort they all belong to the O(n^2) category, that because for each time the sample doubles the comparisons increase 4 time.
		- ### Some useful websites for algoritms.
			- ### Sorting Algorithms Animations
				- Neste site, é possível comparar o desempenho de diversos algoritmos de ordenação (de forma separada ou com todos ao mesmo tempo). Faça alguns testes e conheça a performance dos algoritmos frente a diferentes tipos de entrada.
				- [Sorting Algorithms Animations](https://www.toptal.com/developers/sorting-algorithms)
			- ### Algostructure
				- Neste site, você pode escolher um algoritmo de ordenação, conhecer sua complexidade, bem como seu código fonte, e interagir com o programa, fazendo diferentes simulações.
				- [AlgoStructure](http://www.algostructure.com/index.php)
			- ### Comparison Sorting Algorithms
				- Aqui você também pode escolher um algoritmo de ordenação e visualizar em detalhes seu funcionamento.
				- [Comparison Sorting Algorithms](https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html)
			- ### Searching Sorted Lists
				- Descrição do recurso: Neste site, você poderá comparar o desempenho e o funcionamento dos métodos de busca (linear e binária).
				- [Searching Sorted Lists](https://www.cs.usfca.edu/~galles/visualization/Search.html)
-
- # Aula 4
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Estrutura de Dados/N_EST DAD_A4 – Texto de Apoio.pdf)
		-
	- ## Ponto de Partida
		- **Concept of piles**: Piles are the object where you can only see and manipulate the last element of the sequence, usually using:
			- 1. `push(item)` -> Insert on the sequence
			  2. `pop()` -> Extract
			  3. `top(); returns: item` -> Consults the top element
		- ### Useful Link
			- ### Stack (Array Implementation)
				- Simule a execução de uma Pilha e visualize o efeito das operações push, pop e top em vetores.
				- [Stack Array Simulation](https://www.cs.usfca.edu/~galles/visualization/StackArray.html)
-
- # Aula 5
  collapsed:: true
	- ## Texto de Apio
		- ![Texto de Apoio](../assets/mack/Estrutura de Dados/N_EST DAD_A5 – Texto de Apoio.pdf)
		-
	- ## Ponto de Partida
		- ### Queue concept
			- **FIFO** -> First In First Out
			- Elements can only be added on the end and removed on the front of the Queue using the commands bellow:
				- `enqueue(item)` -> insert a item ion the queue
				- `dequeue()` -> remove the first element of the queue
				- `front(); returns: item` -> returns the first element on the line.
			- For information -> there is s double ended queue Deque that can accept the insertion, consultation and removal on both ends.
			- **Circular queue** -> Is when the vector reserved for this particular queue in the memory after insertions and extractions the start of the queue is at the end o the vector and the end of the queue is at the start of the vector.
		- ### Useful link:
			- ### Queue (Array Implementation)
				- Simule a execução de uma Fila e visualize o efeito das operações enqueue, dequeue e front em vetores.
				- [Queue Array Implementation](https://www.cs.usfca.edu/~galles/visualization/QueueArray.html)
-
- # Aula 6
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Estrutura de Dados/)
	- ## Ponto de Partida
-
- # Aula 7
  collapsed:: true
	- # Texto de Apoio
		- ![|Texto de Apoio](..assets/mack/Estrutura de Dados/N_EST DAD_A7 – Texto de Apoio.pdf)
	- # Ponto de Partida
		- ## Threes
			- Each item receive the name of **knot**
			- The **root** is the only knot that **does not have parent**
			- **Intern Knot** -> Have a child
			- **External Knot** -> (Or leaf) doe s not have a child
			- **Level**  -> It is how many knots exist from the root to the given knot, Starting at 0
		- ###
		- ### Binary three
			- It a three that does not have more than two children for given knot, they can call them Left child and right child.
			- **Last level** -> isn't required to be full, however it must be filled from the left to right way
			- #### Ways to run it
				- **Preorder** -> First the root then all the left three following this format for all the other readings.
				- **Postorder** -> From the bottom up, first the **left knot**then the **right knot** then the **root**
				- **inorder** ->**From the base** up, the **left**, then the **right** and after the root, repeating this method till the top root.
			- What are the Binary Three methods:
			  1. Preorder
			  2. Posorder
			  3. inorder #card
				- **Preorder** -> First the root then all the left three following this format for all the other readings.
				- **Postorder** -> From the bottom up, first the **left knot**then the **right knot** then the **root**
				- **inorder** ->**From the base** up, the **left**, then the **right** and after the root, repeating this method till the top root.
		- ## Professor Resolve
			- ###  Java Implementation
				- What kind of data will be stored in it.
			- ```Java 
			  public class Node {
			    String nomePasta; //stores knot
			    Node left, right, parent; // point to knot
			    
			    public Node(String nomePasta) {
			      this.nomePasta = nomePasta;
			      left - right =parent = null;
			    }
			    
			    public void mostraNo(){
			      System.out.print(nomePasta + "-");
			    }
			  }
			  ```
			-
-
- # Aula 8
	- # Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Estrutura de Dados/N_EST DAD_A8 – Texto de Apoio.pdf)
	- # Ponto de Partida
		- ### **Hash Tables**
			- `{key: value}`
			- Concept:
				- M -> is the number of position on the hash table.
				- N -> Is the number of key stored
				- Alfa -> N/M is the load factor
				- Register (key, value) -> function hash(k) ->Register position
			- #### Module function:
				- For every given number the function divide it by 10, then the remain of the division will be the key for storing the value.
			- #### Mid Square
				- it takes the given number and make it square, then take the 2 numbers 4th and 5th position from the right.
			- #### Binnig
				- Divide all the positions by the number of registers / HT size.
				- for 1000 numbers in a 10 position HT you would divide each number by 100 so all the number most probably will have a single spot.
			- #### Funcition for Strigns
				- Using ASCII transform the first two letters in ascII table numbers then multiply both and get the last 2 digits.
			- ## Momento com o Professor
				- How to deal with the collision problem?
				- the importance of the hash table is for the speed in which the script can retrieve information. for a given search the script just needs to apply the hash function and then see if there is a value there, if isn't the script already can return null instead of going through all the values on the table.
				-
				- #### Separate Chaining
					- For each given key to be stored will pass through a hash function and be mapped in to a given place. In the occurrence of other key collide with the last one the value can be linked in to a linked list.
					-
				-
				-