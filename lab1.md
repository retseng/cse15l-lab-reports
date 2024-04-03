```cd``` : *change directory*
---
# **Share an example of using the command with no arguments.**\
![Image](cd_empty.png)	\
Absolute path: ```/c/Users/rebec```\
Nothing is printed and there is no change in the directory as there is no argument set.\
*No error* 



# **Share an example of using the command with a path to a directory as an argument.**\
![Image](cd_path.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data``` \
Nothing is printed and the directory is changed to the folder, CSE_15L as the argument stated.\
*No error*



# **Share an example of using the command with a path to a file as an argument.**\
![Image](cd_file.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data/Downloads/CSE_15L/lecture1/messages```\
An error was printed, and the directory was *not* changed.\
**_Error:_**```Not a directory``` The argument in ```cd``` should be a file path, not a file. 



```ls``` : *list*
---
# **Share an example of using the command with no arguments.**\
![Image](ls_empty.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data```\
The contents of the Data folder (which is the current directory in the absolute path) are printed.\
*No error*\



# **Share an example of using the command with a path to a directory as an argument.**\
![Image](ls_path.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data```\
The contents of the CSE_15L folder are printed.



*No error*\
# **Share an example of using the command with a path to a file as an argument.**\
![Image](ls_file.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data/Downloads/CSE_15L/lecture1/messages```\
The text file name is repeated.
*No error*



```cat``` : *concatenate*
---
# **Share an example of using the command with no arguments.**\
![Image](cat_empty.png)	\
Absolute path: ```/c/Users/rebec```\
Nothing is printed, but upon user input, the text is repeated.\
**_Error:_** While there is no explicit error printed, the output can be interpreted as an *infinite loop*, as there is no way for the code to stop itself.



# **Share an example of using the command with a path to a directory as an argument.**\
![Image](cat_path.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data/Downloads/CSE_15L/lecture1```\
This states that the given argument is a directory.
*No error*



# **Share an example of using the command with a path to a file as an argument.**\
![Image](cat_file.png)	\
Absolute path: ```/c/Users/rebec/Dropbox/Becky/Data/Downloads/CSE_15L/lecture1/messages```\
This command prints the contents of the file\
*No error*
