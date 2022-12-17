# Getting Started with Python

## References

* [W3 School Python Tutorial](https://www.w3schools.com/python)
* [Python Exercises](https://www.w3schools.com/python/exercise.asp)

## Submission

* **List any features of Python that you like/dislike most so far.**
  * Python does not require you to use reserved words to declare variables
    * You create a variable whenever you assign something a value
    * I like this because I do not need to worry about forgetting to add a `let`, `const`, or `var` in front of something that I want to use as a variable
  * Python does not require you to define data types and allows mixing of data types together
    * I am neutral on this
    * On one hand, this means I can pack a lot of data into something like an array
    * On the other hand, this means that if I am not careful about remembering what types of data I have inside an array I could end up creating errors in my program
  * Python allows you to explicitly state if a variable is in the global scope via the `global` reserved word
    * I like this because I can create global variables to be reused/referenced by my programs within functions without having to worry about returning the value and passing it back to a global variable
  * Python allows multiple values to be assigned to the same variable and will reference whichever is the most recent
    * I do like that this makes variables easy to update, but the downside is that you need to remember exactly which variable you are calling
      * For example, if you want to call a variable `x` and have many `x`'s throughout the program, you may call the wrong one
  * Python requires you to indent correctly in order to create a block of code
    * I don't like this as much since messing up spacing even a little bit will throw off the code and create errors
* **List some of the ways that Python is similar and different to JavaScript.**
  * Variables
    * Both
      * Variables can be within the global scope of the program or local scope of a function
    * Python
      * Can assign multiple variables values in one line
      * Can reuse variable names and have that name hold multiple values
      * Does not require a variable be declared with a reserved word
      * Can declare a global variable within a function
    * JS
      * Cannot assign multiple variables values in a single line of code
      * Requires variables be declared with reserved words
      * Global variables must be declared within the global scope outside of a function
  * Functions
    * Both
      * Require functions be declared
    * Python
      * Requires proper in dentation for function to be read properly
      * Uses `:`
      * Has `lambda` functions that allow you to create anonymous functions within other functions
    * JS
      * Indentation is for readability only and does not impact the functions execution
      * Uses `;`

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
  * **List** is a collection which is ordered and changeable. Allows duplicate members.
  * **Tuple** is a collection which is ordered and unchangeable. Allows duplicate members.
  * **Set** is a collection which is unordered, unchangeable*, and unindexed. No duplicate members.
  * **Dictionary** is a collection which is ordered** and changeable. No duplicate members.
