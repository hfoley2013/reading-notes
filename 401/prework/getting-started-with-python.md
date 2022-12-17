# Getting Started with Python

## References

* [W3 School Python Tutorial](https://www.w3schools.com/python)
* [Python Exercises](https://www.w3schools.com/python/exercise.asp)

## Submission

* **List any features of Python that you like/dislike most so far.**
* **List some of the ways that Python is similar and different to JavaScript.**

## Notes

* Assignment
  * Python Syntax to Python Lambda Functions
  * Complete Python Exercises
  * Complete remaining Python Tutorial

### Indentation

* Python uses indentation to indicate a block of code
  * Therefore, indentation is important to the ***functionality*** of Python, not just for readability
* Indentation is usually **4** spaces

### Variables

* There are no commands for declaring a variable in Python
* You create a variable whenever you assign a value to something (i.e. `x = 5`)

### Comments

* Comments are created with `#`
* Python has no syntax for multiline comments
  * A `#` must proceed each comment line
* There is a work around that will allow you to use a string literal not assigned a variable to create a multiline comment

  ```py
  """
  This is a comment
  written in
  more than just one line
  """
  print("Hello, World!")
  ```

### Variables

* Created by assigning something a value
* You can specify the type of data a variable should be via **casting**

  ```py
  x = str(3)    # x will be '3'
  y = int(3)    # y will be 3
  z = float(3)  # z will be 3.0
  ```

* String variables can use double or single quotes
* Variable names ***are*** **case-sensitive**
* Python will allow you to assign values to multiple variables in one line

  ```py
  x, y, z = "A", "B", "C"
  print(x) #prints x
  print(y) #prints y
  print(z) #prints z
  ```

* You can assign the same value to multiple variables

  ```py
  x = y = z = "Orange"
  print(x)
  print(y)
  print(z)
  ````

* You can **unpack** a *collection* of values and extract each value into variables

  ```py
  fruits = ["apple", "banana", "cherry"]
  x, y, z = fruits
  print(x)
  print(y)
  print(z)
  ```

* `print()` is the **output variable** in Python
* Variables created outside a function are in the **global scope** of the program
* Variables created within a function are in the **local scope** of the function
  * **NOTE:** can use the `global` keyword to create a global variable inside a function

### Data Types

| **Type** | **Name** |
| --- | --- |
| Text | `str` |
| Numeric	| `int, float, complex` |
| Sequence |	`list, tuple, range` |
| Mapping | `dict` |
| Set	| `set, frozenset` |
| Boolean	| `bool` |
| Binary | `bytes, bytearray, memoryview` |
| None |	`NoneType` |

### Numbers

* `int` = whole number
* `float` = decimal number
* `complex` = combo of letters and numbers
* Random number generation:

  ```py
  import random
  print(random.randrange(1, 10)) #prints random numbers between 1 and 10
  ```

### Strings

* Single or double quotes
* Assign multiline strings using triple quotes `"""<string>"""`
* Strings are treated as arrays by Python
* Loop through string

  ```py
  for x in "banana":
    print(x)
  ```

* String Length

  ```py
  a = "Hello, World!"
    print(len(a))
  ```


* Check contents of string

  ```py
  # Contains value
  txt = "The best things in life are free!"
  print("free" in txt)

  # Does NOT contain value
  txt = "The best things in life are free!"
  print("expensive" not in txt)
  ```

* Sting slicing

  ```py
  b = "Hello, World!"
  #From beginning
  print(b[:5]) #Hello
  #From end
  print(b[6:]) #World!
  #Between
  print(b[2:6]) #ello
  ```

* Modify strings
  * `.upper()` = to uppercase
  * `.lower()` = to lowercase
  * `.strip()` = remove whitespace
  * `.replace(val1, val2)` = replace `val1` with `val2`
  * `.split("delimiter")` = break the string apart at the `delimiter` (i.e. `,`, ` `, `:`, etc.)
* Concatenate strings
  * `str1 + str2 = str1str2`
  * `str1 + " " + str2 = str1 str2`
* Insert numbers into string
  * Use `{}` as place holders combined with `.format(variable)`
  
  ```py
  age = 36
  txt = "My name is John, and I am {}"
  print(txt.format(age))
  ```
* Escape Characters for strings

  | **Code** | **Result** |
  | --- | --- |
  | \'	| Single Quote |
  | \\ | Backslash |
  | \n | New Line	|
  | \r | Carriage Return |
  | \t | Tab |
  | \b | Backspace |
  | \f | Form Feed |
  | \ooo | Octal value |
  | \xhh | Hex value |

### Python Assignment Operators

| **Operator** | **Example** | **Same As** |
| --- | --- | --- |
| =	| x = 5	| x = 5	|
| += | x += 3 |	x = x + 3 |	
| -= | x -= 3	| x = x - 3	|
| *= | x *= 3	| x = x * 3	|
| /= | x /= 3	| x = x / 3 |
| %= | x %= 3	| x = x % 3	|
| //=	| x //= 3 |	x = x // 3 |
| **=	| x **= 3 |	x = x ** 3 |
| &= | x &= 3	| x = x & 3 |
| \|=	x | \|= 3 |	x = x \| 3 |
| ^= | x ^= 3 |	x = x ^ 3	|
| >>= |	x >>= 3 |	x = x >> 3 |
| <<=	x | <<= 3	| x = x << 3 |

### Lists

* 4 Types
  * List
  * Tuple
  * Set
  * Dictionary
