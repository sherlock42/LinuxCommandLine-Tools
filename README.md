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
**If you want contents of both files then use >> operator instead of >**

<br />

* **wc command**: wc stands for words, character, and it prints the number of lines, words and characters and file name of a file.
``` terminal
   wc script.python
```

<br />

* **sort command**: sorts the content of a file in alphabetical order.
``` terminal
   sort names.txt
```

<br />

* **uniq command**: uniq stands for "unique" and filters out only adjacent, duplicate lines in a file and hence it will not remove those repeating lines which are not adjacent and are coming after some lines so to overcome this we can first sort the lines and then use the uniq command if we don’t want even a single line repeated.
``` terminal
   sort names.txt | uniq > sorted_names.txt
```

<br />

* **grep command**: grep stands for "global regular expression print". It searches in a files for lines that match a pattern and returns the results. It is also case sensitive. Here, grep searches for "stdio" in code.c and print all lines which contains it. But it will not print the consecutive "stdio" if any.
``` terminal
   grep cout code.cpp
```
**Tip:** *grep -i flag will remove the case sensitivity of the pattern being searched.*
<br />

* **sed command**: sed stands for "stream editor". It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to "find and replace".
<br />

**Let's look at the expression 's/snow/rain/':**
   * s: stands for "substitution". It is always used when using sed for substitution.
   * snow: the search string, the text to find.
   * rain: the replacement string, the text to add in place.
