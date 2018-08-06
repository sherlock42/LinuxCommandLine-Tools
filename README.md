# Command-Line-Guide

### Symbols and Uses
1. **>** redirects standard output of a command to a file, overwriting previous content.
2. **>>** redirects standard output of a command to a file, appending new content to old content.
3. **<** redirects standard input to a command.
4. **|** redirects standard output of a command to another command.

### Some General terms and keywords
1. **sort**: sorts lines of text alphabetically.
2. **uniq**: filters duplicate, adjacent lines of text.
3. **grep**: searches for a text pattern and outputs it.
4. **sed** : searches for a text pattern, modifies it and outputs it.
5. **export** VARIABLE="Value" sets and exports an environment variable.
6. **USER** is the name of the current user.
7. **PS1** is the command prompt.
8. **HOME** is the home directory. It is usually not customised.
9. **PATH** returns a colon separated list of file paths. It is customised in advanced cases.
10. **env** returns a list of environment variables. <br />
    *e.g., env | grep PATH*

### Now Understanding above commands or keywords and even more

* **ls command**: Display all the files and directories in the current directory.
**-**: This is called as flag, we can add more specifications and properties to out commands using these flags like in case of *ls*. e.g.,

``` terminal
   $ ls -a -l -h -r 
```
This will print all the files and directories in the current directory but -a flag will help us to display the hidden files and directories, -l helps us to show detailed format, -r shows in reverse order and -h for units of memory > B for Bytes etc.

**You can also do like:**
``` terminal
   $ ls -alhr
```
<br />

* **Pipe (|)**: Pipe ‘|’ this takes the command as standard output on the left of it and pipes it as a standard input to the command on its right.
``` terminal
   $ env | grep PATH
```

<br />

* **cp command**: *cp* is used to copy single or multiple files in current or another directory.
``` terminal
   $ cp add.c programs/
```
add.c file will be copied to programs directory which is present in current directory.

<br />

* **mv command**: *mv* is used to move or rename single or multiple files.
``` terminal
   $ mv add.c interger_add.c 
```
renaming add.c to integer_add.c
``` terminal
   $ mv add.c programs/
```
moving add.c file to programs directory

<br />

* **cat command**: *cat* displays all the content of a file.
``` terminal
   $ cat add.c
```
It can be also used for copying and creating a new file and if the file exists and still we are using cat command to copy content then the content of the new file will be deleted and the copied content will be there. Below if the new_add.c exists before then it's content will be deleted and it'll have the copied content of add.c file.
``` terminal
   $ cat add.c > new_add.c
```
**If you want contents of both files then use >> operator instead of >**

<br />

* **wc command**: wc stands for words, character, and it prints the number of lines, words and characters and file name of a file.
``` terminal
   $ wc script.python
```

<br />

* **sort command**: sorts the content of a file in alphabetical order.
``` terminal
   $ sort names.txt
```

<br />

* **uniq command**: uniq stands for "unique" and filters out only adjacent, duplicate lines in a file and hence it will not remove those repeating lines which are not adjacent and are coming after some lines so to overcome this we can first sort the lines and then use the uniq command if we don’t want even a single line repeated.
``` terminal
   $ sort names.txt | uniq > sorted_names.txt
```

<br />

* **grep command**: grep stands for "global regular expression print". It searches in a files for lines that match a pattern and returns the results. It is also case sensitive. Here, grep searches for "stdio" in code.c and print all lines which contains it. But it will not print the consecutive "stdio" if any.
``` terminal
   $ grep cout code.cpp
```
**Tip:** *grep -i flag will remove the case sensitivity of the pattern being searched.*
<br />

* **sed command**: sed stands for "stream editor". It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to "find and replace".
<br />

**Let's look at the expression 's/snow/rain/':**
   * s: stands for "substitution". It is always used when using sed for substitution.
   * snow: the search string, the text to find.
   * rain: the replacement string, the text to add in place.
``` terminal
   $ sed 's/snow/rain/' forests.txt
```
but note one thing it will only replace the first snow word with rain if you want to do it in the whole file then you have to use 
``` terminal
   $ sed 's/snow/rain/g' forests.txt
```
<br />

* **nano command**: nano is a command line text editor. It works just like a desktop text editor like TextEdit or Notepad, except that it is accessible from the command line and only accepts keyboard input. It can edit or create a new file for you.
``` terminal
   $ nano hello_world.js
```
**
   1. Ctrl + O, saves a file, O stands for output
   2. Ctrl + X, exits the nano program, X stands for exit
   3. Ctrl + G, opens a help menu
**

<br />

### Bash Profile file

<br />


### Environment
Each time we launch the terminal application, it creates a new session. The session immediately loads settings and preferences that make up the command line environment. We can configure the environment to support the commands and programs we create. This enables us to customise greetings and command aliases, and create variables to share across commands and
programs.

<br />

**env command**: The env command stands for "environment", and returns a list of the environment variables for the current user. Here, the env command returns a number of variables, including PATH, PWD, PS1, and HOME.
``` terminal
   $ env
```
You can also try
``` terminal
   $ env | grep PATH
```
This will print the PATH environment vairable from the environment using grep command. I hope now you are able to use these commands simultaneously. *Congratulate yourself!!*.

#### Environment Variables
Environment variables are variables that can be used across commands and programs and hold information about the environment.
Some of the environment variables are given below, rest you can explore on your own.

1. **USER variable**: export USER="Farhan" sets the environment variable USER to a name "Farhan". Usually the USER variable is set to the name of the Computer's owner.
``` terminal
   $ export USER="Farhan"
   $ echo $USER
```
   * The line export makes the variable to be available to all child sessions initiated from the session you are in. This is  a way to make the variable persist across programs.
   * At the command line, the command echo $USER prints the value of the variable. **Note that $ is always used when we are using an environmental**. Here, the command echo $USER prints the name set for the variable.
   
<br />


2. **PS1 variable**: PS1 is a variable that defines the makeup and style of the command prompt.
``` terminal
   $ export PS1="I am developer >> "
   I am developer >> ls
```
export PS1="I am developer >> " will change the styling of your command prompt to this.
<br />

3. **HOME variable**: The HOME variable is an environment variable that displays the path of the home directory.
``` terminal
   $ echo $HOME
```
<br />

4. **PATH variable**: PATH is an environment variable that stores a list of directories separated by colons(:). Each directory contains scripts for the command line to execute. The PATH variable simply lists those directories that contain scripts.
``` terminal
   $ echo $PATH
```
For example, many commands we've learned are scripts stored in the /bin directory. 
> This is the script that is executed when you type the pwd command. /bin/pwd.
<br />

> This is the script that is executed when you type the ls command.  /bin/ls
