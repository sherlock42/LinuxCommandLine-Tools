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
   ls -a -l -h -r 
```
This will print all the files and directories in the current directory but -a flag will help us to display the hidden files and directories, -l helps us to show detailed format, -r shows in reverse order and -h for units of memory > B for Bytes etc.

**You can also do like:**
``` terminal
   ls -alhr
```
<br />

* **Pipe (|)**: Pipe ‘|’ this takes the command as standard output on the left of it and pipes it as a standard input to the command on its right.
``` terminal
   env | grep PATH
```

<br />

* **cp command**: *cp* is used to copy single or multiple files in current or another directory.
``` terminal
   cp add.c programs/
```
add.c file will be copied to programs directory which is present in current directory.

<br />

* **mv command**: *mv* is used to move or rename single or multiple files.
``` terminal
   mv add.c interger_add.c 
```
renaming add.c to integer_add.c
``` terminal
   mv add.c programs/
```
moving add.c file to programs directory

<br />

* **cat command**: *cat* displays all the content of a file.
``` terminal
   cat add.c
```
It can be also used for copying and creating a new file and if the file exists and still we are using cat command to copy content then the content of the new file will be deleted and the copied content will be there. Below if the new_add.c exists before then it's content will be deleted and it'll have the copied content of add.c file.
``` terminal
   cat add.c > new_add.c
```

