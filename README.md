This program has one class with a main method (the class name - "Hello") and package "com.leverx".
Structure of folders in my example: /Users/a1/IdeaProjects/hello/src/com/leverx

1. For compiling and running the program under the console you need:
   1) Specify the path to the folder where the java file is located, you can use the command "cd";
   2) Сompile the file with the command: javaс Hello.java;
   3) Then you need to go to the folder src and run the program:
      1. java -classpath ./ com.leverx.Hello
 
2. Build jar file:
   1) In src folder add manifest.txt file and write the name of the main class in it, for example:
      1. Main-Class: com.leverx.Hello
   2) Create jar file:
      jar cfm Hello.jar manifest.txt com/leverx/Hello.class
      1. -c, --create               Create the archive
      2. -f, --file=FILE            The archive file name. When omitted, either stdin or stdout is used based on the operation
      3. -m, --manifest=FILE        Include the manifest information from the given manifest file
   3) Run jar file:
      1. java -jar Hello.jar
      
3. Connect third-party library:
   1) Downloads a third-party library, for example commons-collections4-4.4
      (https://commons.apache.org/proper/commons-collections/download_collections.cgi)
   2) Сompile the file from src folder with the command: 
      1. javaс -cp commons-collections4-4.4.jar com/leverx/Hello.java
   3) Run the program from src folder with command: 
      1. java -cp ./ com.leverx.Hello commons-collections4-4.4
   4) Add the name of the third-party library to the manifest.txt which you want to connect:
      1. Class-Path: commons-collections4-4.4
   5) Create jar file:
      1. jar cfm Hello.jar manifest.txt com/leverx/Hello.class
   6) Run our jar file:
      1. java -jar Hello.jar
