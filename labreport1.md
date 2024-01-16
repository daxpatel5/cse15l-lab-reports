# Lab Report 1
> Last Edited: 11 January, 2024

## The `cd` command

1. Using `cd` with no arguments.  
   Code:
   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ cd
   [user@sahara ~]$ pwd
   /home
   ```
   Working directory: `/home/lecture1` changes to `/home`  
   Output: We go out of the lecture1 folder back to its parent directory `/home`  
   Error or not: No error!  
   
2. Using `cd` with a path to a *directory* as an argument.  
   Code:
   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   ```
   Working directory: `/home` changes to `/home/lecture1`  
   Output: We go into the lecture1 folder within the working directory as passed as argument in the terminal  
   Error or not: No error!  
   
3. Using `cd` with a path to a *file* as an argument.  
   Code:
   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ cd Hello.java
   bash: cd: Hello.java: Not a directory
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   ```
   Working directory: `/home/lecture1` remains unchanged  
   Output: No change in directory  
   Error or not: Error; the `cd` command is used to change the current working directory and passing a file as an argument results in an error because the terminal cannot navigate into a file and set it as the new working directory.  

## The `ls` command

1. Using `ls` with no arguments.  
   Code:
   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ ls
   lecture1
   [user@sahara ~]$ pwd
   /home
   ```
   Working directory: `/home` remains unchanged  
   Output: All the directories and files within the working directory (in this case just the lecture1 directory) are shown  
   Error or not: No error!  
   
2. Using `ls` with a path to a *directory* as an argument.  
   Code:
   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ ls lecture1/
   Hello.class  Hello.java  messages  README
   [user@sahara ~]$ pwd
   /home
   ```
   Working directory: `/home` remains unchanged  
   Output: All the directories and files within `/home/lecture1` are displayed  
   Error or not: No error!  
   
3. Using `ls` with a path to a *file* as an argument.  
   Code:
   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ ls Hello.java
   Hello.java
   [user@sahara ~/lecture1]$ ls messages/en-us.txt 
   messages/en-us.txt
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   ```
   Working directory: `/home/lecture1` remains unchanged  
   Output: Terminal just reads the name and type of the file being passed as the argument  
   Error or not: No error!  

## The `cat` command

1. Using `cat` with no arguments.  
   Code:
   ```
   code
   ```
   Working directory:  
   Output:  
   Error or not:  
   
2. Using `cat` with a path to a *directory* as an argument.  
   Code:
   ```
   code
   ```
   Working directory:  
   Output:  
   Error or not:  
   
3. Using `cat` with a path to a *file* as an argument.  
   Code:
   ```
   code
   ```
   Working directory:  
   Output:  
   Error or not:  
