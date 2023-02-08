- Find all files with a name that matches a given pattern in some target directory.
  
  ```sh
  find <target directory> -name <pattern>
  ```
  
  example:
  
  ```sh
  find zxing -name '*.java'
  ```
- ### wc command
  
  Count the number of lines (or words, or characters, depending on parameters) in some target file.
  
  ```sh
  wc -l <target file>
  ```
  
  example:
  
  ```sh
  wc -l zxing/pom.xml
  ```
- ###  `grep command ` 
  
  Search and list the occurrence(s) of some pattern within a file (or several files). The '-i' flag means "ignore case".
  
  ```sh
  grep -i <pattern> <target>
  ```
  
  The target can be a file or a stream of text output from other commands (as is the case with wc).
  
  example:
  
  ```sh
  find zxing -name '*.java' | grep -i qr
  ```
  
  The '|' operator above takes the output from the find command and feeds that as input into the grep command.
- ### Piping
  
  pipe ('>') send output into text file
  
  ```sh
  find zxing -name '*.java' > javaFiles.txt
  ```
- ### head command 
  
  ```sh
  head -<number of lines> <target file>
  ```
  
  example:
  
  ```sh
  head -50 zxing/pom.xml
  ```
- ###### Combining Bash commands in a Bash script
  
  Bash commands can be combined into a script (commonly in a text file with a ".sh" suffix). Here is an example:
  
  ```sh
  #!/bin/bash
  
  for file in `find $1 -name $2`
  do
  	total=$(wc -l < $file)
  	echo "$file,$total"
  done
  ```
- The first line is the "shebang" - a directive that shows which interpreter needs to be used for this script.
- In the for loop, $1 and $2 refer to arguments given when calling the script file. So in this case, $1 contains the name of the location in which we want the find command to execute, and $2 contains the pattern that we're looking for.
- The results are stored as a variable `file'. For each value of `file', the loop is run.
- The loop runs the `wc -l' command on the file variable (i.e. finds out how many lines are in the file), and stores the result as a variable `total'.
- The second line uses the "echo" command to print the file name and number of lines out to the terminal.
  
  Store the code in a file, such as "lineCount.sh". Store it in the parent directory of the zxing directory (for example).
  
  In the Bash prompt, run the following command to make the script executable:
  
  ```sh
  chmod +x lineCount.sh
  ```
  
  Then try to run it.
  
  ```sh
  ./lineCount.sh zxing *.java > fileSizes.csv
  ```
  
  This creates a csv file, containing all of the java files and their file sizes (in terms of lines of code).