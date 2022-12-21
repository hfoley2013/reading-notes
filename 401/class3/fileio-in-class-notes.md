# In Class Notes: FileIO

## Reading Files

* Read the `spam.txt` file

```py
with open('spam.txt') as f:
  contents = f.read()
  print(contents)
```
  
  * **NOTE:** Using `with` will automatically close the file when the function is done executing

* `help` command
  * `help(f)` will provide information about the file provided by the file wrapper
* `dir` command
  * `print(dir(f))` will return information about commands able to execute on the file
  * `dir` shows the **attributes** of the file
    * Attributes = the things we can do to the file

## Writing Files

* Write to the `spam.txt` file

```py
with open('spam.txt') as f:
  f.write('Do not like eggs')
```

* Can read non-text files by switching to binary reading
  * Example, a jpeg

  ```py
  with open('brain.jpeg', mode='rb') as f:
    contents = f.read()
    print(contents)
  # Will print a string of bytes the refer to the jpeg
  ```
