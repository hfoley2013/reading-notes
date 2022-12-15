# The Command Line

## Reference

* [Bash Command Line Tutorial](https://ryanstutorials.net/linuxtutorial/)
* [The Command Line](https://ryanstutorials.net/linuxtutorial/commandline.php)
* [Basic Navigation](https://ryanstutorials.net/linuxtutorial/navigation.php)
* [More About Files](https://ryanstutorials.net/linuxtutorial/aboutfiles.php)
* [Manual Pages](https://ryanstutorials.net/linuxtutorial/manual.php)
* [File Manipulation](https://ryanstutorials.net/linuxtutorial/filemanipulation.php)
* [Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)

## Notes

### The Command Line

* What is the terminal?
  * A text based interface that allows you to enter commands by typing them
* What is a shell, bash?
  * A part of the OS that defines how the terminal will behave and look after running commands
  * BASH = Bourne again shell

### Basic Navigation

* `pwd` = present working directory = where am I now?
* `ls [options][location]` = list = what is in my current directory?
  * Options
    * `-l` = list format
    * `-a` = all files, including hidden items
* Paths
  * Absolute = type in the exact path for where you want to go
  * Relative = type in directions that are relative to the current location
  * `~` = go straight to home directory
  * `./` = current directory
  * `../` = go back one to parent directory
* `cd [location]` = change directory = change to [location]

### More About Files

* Everything is a file in Linux
* `.exe` = executable file or program
* `.txt` = text file
* `.png, .gif, .jpg` = image
* `file [path]` = tell me what type of file this is
* Spaces in file names
  * Must put `''` around files with spaces in their names
    * `cd 'Holiday Photos'`
    * Alternatively, can use '\`
      * `cd Holiday\ Photos`

### Manual Pages

* `man ls`
  * Essentially opens the operating manual for the command line interface
* `man -k <search term>`
  * Search the manual for the term
* `/<term>`
  * Within a manual page, search for the term
* `n`
  * After performing a search within a manual page, select the next item found

### File Manipulation

* `mkdir [options] <Directory Name>` = make this directory
  * Options
    * `-p` = make parent directories as needed
    * `-v` = makes mkdir tell us what it is doing (i.e. it will say `created directory: <name>`)
* `rmdir [options] <Directory Name>` = delete a directory
* `touch <file name>` = create a file
* `cp [options] <source> <destination>` = copy this source and move it to destination
* `mv [options] <source> <destination>` = move a file from source to destination
  * **NOTE:** Can use `mv` to rename a file if the destination is the same directory as the source
* `rm [options] <file>` = remove file
