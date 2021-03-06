# Linux-Tail

A simplified version of Linux tail utility.

It is used for viewing the last portion of a long text file. tail is generally useful for viewing the last few lines in long log files that the operating system produces (for example the /var/log/kern.log) file in your virtual machine environment). Linux server administrators use the tail utility for checking recent activity in network logs.

ctail   User Commands

Name
  
   ctail - output the part of files

SYNOPSIS
   
   ./ctail [fileName]... [option]...
     or
   ./ctail [option]...
     or
   ./ctail 

Description
   print the last part of the file either from the provided file or the default file. 
   Last part can be specified in the terms of the characters and the number of lines.
  
    Commands:
   
        ./ctail, it reads default file "logfile.txt" from the directory and prints the last 200 characters of the file.
        if the file contains fewer than 200 characters, output the entire the file contents.
        To compile the program, a user can use it on either default file or specified file name.
        e.g ./ctail                : print the last 200 characters from the default file
            ./ctail filename       : print the last 200 characters from the specified file, where the file should be in the same directory.
 
    
        -n,  take a positive integer number as an argument after this command
        This command outputs either number of lines or number of character it depends upon the use
 
        To compile the program, a user can use it on either default file or specified file name.
        e.g ./ctail -n number 
            ./ctail filename -n number  
        where number is the non-negative number and filename is the name of the file which is present in the same directory.
        if the file contains fewer than the number of characters, output the entire the file contents.

        For example, to get the last 20 characters from the default use command should look like ./ctail -n 20
        Similarly for the last 20 characters from the specified file name  ./ctail filename -n 20
         
   
        Limitation:
 
         After the -n there should be always a non-negative number otherwise terminal would throw an error.
         Using the non-default file, it should be in the same directory otherwise terminal will throw an error.
         Similarly any problem in the accessing the file terminal will throw an error.
   

         -L,  This command outputs the last 10 lines either from the default file or the specified file. If the -n argument is
        specified, the value given by the user should be used as the number of lines rather than character.
        if the file contains fewer than 10 lines, output the entire the file contents.
 
        To compile the program, a user can use it on either default file or specified file name.
        e.g    ./ctail -L             : Print the last 10 lines from the default file.
               ./ctail filename -L      : Print the last 10 lines from the specified file, where the file should be in the same directory.
 
         when -n is added in the command for the number of lines if the file contains fewer than the number of lines, output the entire the file contents, here the number of              lines is the non-negative number it is always specified after the -n. 
              ./ctail -L -n number              : Print the last number of lines from the default file.
              ./ctail filename -L -n number     : Print the last number of lines from the specified file, where the file should be in the same directory

         For example, to get the last 20 lines from the specified filename would look like ./ctail filename -L -n 20
         Similarly by default to get 10 lines would look like ./ctail filename -L  , and on the default filename ./ctail -L
       
        
        Limitation:
        Order of the command always look like on the specified the filename; ./ctail filename -L -n number 
        if any difference in the order would lead to an error.
        -n command always come after the -L command
        After the -n there should be always a non-negative number otherwise terminal would throw an error.
        Using the non-default file, it should be in the same directory otherwise terminal will throw an error
        Similarly, any problem in accessing the file terminal will throw an error. 
  
Overall Limitation:
      For any integer value with string-like -n a2 then there is an error, but the string-like 2a it would consider as it 2.
      It is better not to combine the integer with a string, especially for the digit argument.
      For the argument which is more than the number of either total lines or characters in the file, it output everything without any warning or suitable message for it.
