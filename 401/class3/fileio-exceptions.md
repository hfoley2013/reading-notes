# FileIO and Exceptions

## References

* [Read & Write Files in Python](https://realpython.com/read-write-files-python/)
* [Exceptions in Python](https://realpython.com/python-exceptions/)
* [VIDEO : Read & Write Files in Python Companion Video](https://realpython.com/courses/reading-and-writing-files-python/)
* [Reading & Writing Files in Python Quiz](https://realpython.com/quizzes/read-write-files-python/)


## Notes

### Read & Write Files in Python

* **What is a file?**
  * A set of bytes used to store data
  * Modern files have three main parts:
    1. **Header**: metadata about the contents of the file
    2. **Data**: contents of the file
    3. **End of File (EOF)**: special character that indicates the end of the file

    ![File Image](https://files.realpython.com/media/FileFormat.02335d06829d.png)

* **File Paths**
  * All files require a file path
  * Three major parts of a file path:
    1. **Folder Path**: location on the file system where subsequent folders are separated by `\` or `/`
    2. **File Name**: actual name of the file
    3. **Extension**: indicates file type
* **Opening & Closing Files in Python**
  * `file = open('<file_name>')`
  * `file.close()`
  * Two ways to implement:
    1. `try, finally`
       
       ```py
       reader = open('dog_breeds.txt')
       try:
           # Further file processing goes here
       finally:
           reader.close()
        ```
    2. `with`

       ```py
       with open('dog_breeds.txt', 'r') as reader:
       # Further file processing goes here
       ```
  
  * Optional arguments (*mode*) for `open()`
    * `'r'` = open for reading (default)
    * `'w'` = open for writing, truncating (overwriting) the file first
    * `'rb'` or `'wb'` = open in binary mode (read/write using byte data)

* **Reading and Writing Opened Files**
  * `.read(size=-1)`
    * This reads from the file based on the number of size bytes. If no argument is passed or `None` or `-1` is passed, then the entire file is read.
  * `.readline(size=-1)`
    * This reads at most `size` number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or `None` or `-1` is passed, then the entire line (or rest of the line) is read.
  * `readlines()`
    * Reads the remaining lines from the file object and returns them as a list.
    * NOTE: Returns a list object
  * `write(string)`
    * This writes the string to the file.
  * `writelines(seq)`
    * This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).
* **Tips & Tricks**
  * `__file__`
    * Returns the path *relative* to where the initial Python script was called.
      * If you need the full system path, you can use `os.getcwd()` to get the current working directory of your executing code.
  * `'a'` character
    * Append to a file or start writing at the end of an already populated file
      
      ```py
      with open('dog_breeds.txt', 'a') as a_writer:
        a_writer.write('\nBeagle')
      ```

### Python Exceptions

* Occur whenever syntactically correct Python code results in an error.
  * See [list of built in exceptions](https://docs.python.org/3/library/exceptions.html)
* Can create custom exceptions using `raise`

  ```py
  x = 10
  if x > 5:
      raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
  
  #Returns

  Traceback (most recent call last):
    File "<input>", line 4, in <module>
  Exception: x should not exceed 5. The value of x was: 10
  ```

* AssertionError
  * Can have the program throw an error when an assert condition is `false`
  * We `assert` that a condition exists, and if `True` the program will execute

  ```py
  import sys
  assert ('linux' in sys.platform), "This code runs on Linux only."

  #Returns

  Traceback (most recent call last):
    File "<input>", line 2, in <module>
  AssertionError: This code runs on Linux only.
  ```

* `try, except, else, finally`
  * `try` says, "run this block of code if there are no exceptions"
  * `except` says, "run this block of code if there is an exception"
  * `else` says, "run this block of code next if there are no exceptions"
  * `finally` says, "after all of the above, then do this code"
