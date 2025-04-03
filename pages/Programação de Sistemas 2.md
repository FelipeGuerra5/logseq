# Aula 1
collapsed:: true
	- Done
- # Aula 2
	- ## Texto de apoio
		- ![Texto de apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A2 - Texto de apoio.pdf)
		- ### Reading a files with Java
			- In order to read a file in Java we need to `import java.io.*;` so we have access to this API
			- 1. You open the file
			  2. You read the file
			  3. You close the file
			- E. g.:
				- ```Java 
				  import java.io.*;
				  
				  public class TestFiles {
				    public static void main(String[] args)throws IOException {
				      // Open file.txt
				      InputStream is = new FileInputStream("file.txt");
				      // Read one Byte from file.txt
				        int b = is.read();
				      // Print the readen byte
				      System.out.println ("Output" + b);
				      // Closes the file.txt
				      is.close();
				  	System.out.println("Script End");
				    }
				  }
				  ```
				-
				- If the file is not found the error displayed to the final user is the fulll message it gives for developers so bellow we are going to make it more friendly
				- ```Java 
				  import java.io.*;
				  
				  public class FileTester {
				    public static void main(String[] args){
				      
				      try {
				        // Opens file
				        InputStream is = new FileInputStream("file.txt");
				        // Reads file byte
				        int b = is.read();
				        // Print on the screen such byte
				        System.out.println("output" + b);
				        // Closses the file
				        is.close(;)
				      } catch (IOException ex){
				        System.out.println("Error on the file opening.")
				      }
				      System.out.println("End of script!")
				    }
				  }
				  ```
				- Now the script can catch the errors but does not print the actual number on the screen for the user, let's fix it.
				- ```Java 
				  import java.io.*;
				  
				  public class FileTester {
				    public static void main(String[] args) {
				      try {
				        // Open file
				        InputStream is = new FileInputStream("file.txt");
				        // Make an actual character from the alphabet
				        InputStreamReader isr = new InputStreamreader(is);
				        // Read file byte
				        char c = (char) isr.read();
				        // Print it on the screen
				        System.out.println("File text: " + c);
				        // Closes the file
				        isr.close();
				      } catch (IOException ex){
				        System.out.println("The file was not found!");
				      }
				      System.out.ptitln("Scrip has ended!");
				    }
				  }
				  ```
				- Now the output will be the first letter, however is usual to read a line at a time, so let's make more easy to read the file.txt
				- ```Java 
				  import java.io.*;
				  
				  public class FileTester{
				    public static void main(String[] args){
				      try {
				        // Open file
				        InputStream is = new FileInputStream("file.txt");
				        InputStreamReader isr = new InputStreamReader(is);
				        BufferedReader br = new BufferredReader(isr)
				        // Reads a string of the file
				        String output = br.read();
				        // Print the string on the screen
				        System.out.println("Output:" + output);
				        // Closes the file
				        is.close();
				      } catch (IOException ex){
				        System.out.println("File not found!");
				      }
				      System.out.println("End of script!");
				    }
				  }
				  ```
				- Now the script will read line by line and when the lines are empty will return `null` to the program, this way you can use an infinite loop to go through all the lines in the file.txt.
	- ## Professor Resolve
		- Now fi we want to save the results to a new file instead of only displaying it on the screen.
		- ```Java 
		  import java.io.*;
		  
		  public class FileTester{
		  public static void main(String[] args){
		    try {
		      // Open file
		      InputStream is = new FileInputStream("file.txt");
		      InputStreamReader isr = new InputStreamReader(is);
		      BufferedReader br = new BufferredReader(isr)
		      // Reads a string of the file
		      String output = br.read();
		      // Print the string on the screen
		      System.out.println("Output:" + output);
		      
		      //make the file
		      OutputStream os = new FilePoutputStream("outfile.txt");
		      OutputStreamWriter ow = new OutputStreaWriter(os);
		      BufferedWriter bw = new BufferedWriter(ow);
		      
		      String line = "";
		      while(true) {
		        line = br.line;
		        bw.write(line);
		      }
		          // Closes the file.txt and the outfiel.txt
		      is.close();
		     	os.close(); 
		      // If you sdo not close the file after writing it the cahnges wont be saved!
		          
		    } catch (IOException ex){
		      System.out.println("File not found!");
		    }
		    System.out.println("End of script!");
		  }
		  }
		  ```
- # Aula 3
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A3 - Texto de apoio.pdf)
	- ## Ponto de Partida
		- ### Beginning of the Client Server
			- Commercial Archtecture.
			- client | web service | data base and server.
	- ## Professor Responde
		- Done
	- ## Praticando
		- After making the progress listed on the PDF form Texto de Apoio, but not needed to install everything only the NetBeans Apache and it already will download and install all the correct versions for you to use.
		- After that use the code bellow to make a Table -> Funcionario, and insert the workers bellow.
			- ```SQL 
			  -- Creating the table
			  CREATE TABLE funcionario(
			      numat BIGINT NOT NULL,
			      nome VARCHAR(255) NOT NULL,
			      salario DECIMAL(10,1) NOT NULL,
			      sexo CHAR NOT NULL,
			      ndepto INTEGER NOT NULL,
			      nsuper BIGINT,
			      PRIMARY KEY (numat)
			  );
			  
			  -- Inserting the data
			  INSERT INTO funcionario VALUES (1234,'João B Silva',30000.0,'M',5,3334);
			  INSERT INTO funcionario VALUES (3334,'Franco T Welss',400000.,'M',5,8886);
			  INSERT INTO funcionario VALUES (9998,'Alice J Zeus',25000.0,'F',4,9876);
			  INSERT INTO funcionario VALUES (9876,'Janice S Costa',43000.0,'F',4,8886);
			  INSERT INTO funcionario VALUES (6668,'Rildo K Neves',38000.0,'M',5,3334);
			  INSERT INTO funcionario VALUES (4534,'Joice A Santos',25000.0,'F',5,3334);
			  INSERT INTO funcionario VALUES (9879,'Amo B Jahvi',25000.0,'M',4,9876);
			  INSERT INTO funcionario VALUES (8886,'Jaime E Boulos',55000.0,'M',1,NULL);
			  
			  -- Retriving information
			  SELECT * 
			  FROM APP.FUNCIONARIO 
			  WHERE SALARIO >= 40000.0 
			  ORDER BY SALARIO DESC
			  
			  ```
- # Aula 4
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A4 - Texto de apoio.pdf)
	- ## Ponto de Partida
		- In order to get a connection to your database you will have to:
		  ```Java 
		  // Inside a class:
		  Connection conexao = DriverManager.getConnction("LInk_For DB", "User", "password");
		  String SQL = "INSERT INTO <table> VALUES(?, ?, ?)";
		  PreparedStatement stmt = conexao.prepareStatement(SQL);
		  stmt.setInt(1, <int>); // Where the 1 is the position, <int> is the value for it.
		  stmt.setString(2,"<string>");
		  stmt.setDouble(3, <Double>);
		  
		  ```
- # Aula 5
  collapsed:: true
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A5 - Texto de apoio.pdf)
	- ## Ponto de Partida
		- First pattern for API -> SOAP still used today
		- REST -> Uses URI to make requests and can converse Data in JSON or XML
		-
- # Aula 6
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A6 - Texto de apoio.pdf)
	- ## Ponto de Partida
		- Creating a web application with java in netBeans
		- create a web service.
		- on top of the web Application create a restful webservice.
		- on the folder libraries import java RS 2.0
		-
- # Aula 7
	- ## Texto de Apoio
		- ![Texto de Apoio](../assets/mack/Programacao de Sistemas 2/N_PROG SIST II_A7 - Texto de apoio.pdf)
	- ## Ponto de Partida
		-