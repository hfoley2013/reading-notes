# The Coder's Computer

## Assignment
Go through resources below and create a page in reading-notes that summarizes what you learned as though you were presenting the material to a non-technical friend interested in learning about it.

### Readings
[Choosing a Text Editor](https://codefellows.github.io/code-102-guide/curriculum/class-02/Choosing-A-Text-Editor--The-Older-Coder.pdf)  

[The Command Line](https://ryanstutorials.net/linuxtutorial/commandline.php)  

[Basic Navigation](https://ryanstutorials.net/linuxtutorial/navigation.php)  

[About Files](https://ryanstutorials.net/linuxtutorial/aboutfiles.php)

### Notes

#### Choosing a Text Editor
##### Summary
In order to write coding in a **clean, clear, concise, efficient**, and **easily auditable** manner, you need to use a good text editor. This text editor should have the ability to **suggest endings to your code snippets (_code completition)** as you type to improve speed and reduce redundant typing. It should also **highlight each element within a block of code (_syntax highlighting_)** so that you can quickly distinguish what is text, comments, variables, functions, etc. Furthermore, the text editor should be ***customizable*** through the use of ***extensions*** and a variety of themes. This allows you to make the editor more comfortable for you use and speed up your ability to deliver flawless code.

##### Notes
* What is a text editor?
  - A text editor is software that allows you to write and manage text
* Characteristics of a "_good_" text editor
  - *Code Completion*
    - Allows you to start typing and offers suggestions based on what you typed
    - Automatically enters closing `()`, `[]`, or appropriate ending `</>`
  - *Syntax Highlighting*
    - Colorizes text based on its function
    - This allows you to quickly distinguish different elements of a code block
  - *Variety of Color Themes*
    - You stare at your computer all day; make sure that the screen is comfortable for you eyes
    - Light vs. Dark mode, color variations, etc.
  - *Availability of Extensions*
    - Extensions are "plug-ins" for text editors that allow you to have functionality that you otherwise would not
    - These include functions like bracket highlighting and ability to live share code, along with hundreds of other functions depending on the specific text editor
* What is an IDE?
  - Integrated Development Environment
    - A suite of software that includes a text editor, file manager, compiler, and debugger all in one package
    - Basically, it's a software package that includes everything you need to write code with enhanced functionality

#### Using the Terminal 

##### The Command Line
- What is the command line (a.k.a. the terminal)?
  - A **text based method of interacting with your computer**
  - Instead of using the Graphical User Interface (GUI), i.e. icons and the mouse, to execute programs, you type text commands into the terminal window
- What do I type in the command line?
  - The **first thing you type in the _command line_ is a _command_**, such as `ls`, which will look inside your current directory and display the files in there
  - Commands can be modified with *command line arguments* to execute more specific commands
    - These arguments, aka options, follow the command and are preceded by a `space`; they typically start with a `-`
    - Ex: `ls -l` will look inside the current directory (`ls`) and then generate a long list of contents (`-l`)

##### Basic Navigation
- Where are we now?
  - `pwd` = Print Working Directory
- What's in out current location?
  - `ls` = List the contents of a directory
- How do I change directories?
  - `cd [directoryName]` = Change Directories to `directoryName`
- How do I go back a level?
  - `cd ..` = Change Directories back to parent directory
- Paths (examples assume starting in `Documents` directory)
  - `~` = Home directory >> Ex: `ls /home/hfoley/Documents` == `ls ~Documents`
  - `.` = Current directory >> Ex: `ls ./Documents` == hfoley: `ls Documents`
  - `..` = Parent directory  >> Ex: `ls ../` == `ls hfoley`
  - Absolute Path
    - A file or directory location in relation to the root of the file system
  - Relative Path
    - A file or directory location relative to where we currently are in the file system

##### About Files
- Everything is a file, even directories, in Linux
- A file type is defined by its 2-4 character extension (.txt, .png, .gif, .exe, .py, .js, etc.)
- Linux is case sensitive; you must enter the correct case to find your file
- To find a directory with spaces in the name use `` `[directoryName] ` `` or `[firstWord]\ [secondWord]`
  - Ex: `` cd `Holiday Photos` ``or `cd Holiday\ Photos` 