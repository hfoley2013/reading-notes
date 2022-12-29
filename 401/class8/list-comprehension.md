# List Comprehension

## Reading

* [List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)
* [AUDIO: Debugging with PySnooper](https://www.pythonpodcast.com/pysnooper-python-debugging-episode-241/)

## Reference

* [Primer on Decorators](https://realpython.com/primer-on-python-decorators/)

## Notes

### List Comprehensions

* Can be used to replace loops when needing to create new lists
* Syntax

```py
my_new_list = [ expression for item in list ]
```

  * First is the expression we’d like to carry out
    * `expression` inside the square brackets
      * Expression just means **do something to the item** in the list
        * EX: `multiples_of_three = [x*3 for x in range(10)]`
        * You can even call functions within the list comprehension to act as your expression
  * Second is the object that the expression will work on
    * `item` inside the square brackets
  * Finally, we **need an iterable list of objects** to build our new list from
    * `list` inside the square brackets.

## Python Decorators

* A decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it
  * A decorator *wraps* a function, *modifying* its behavior
* Functions are **first-class objects** in Python
  * This means that **functions can be passed around and used as arguments**
* Uses `@` symbol as syntactic sugar, referred to a [pie syntax](https://www.python.org/dev/peps/pep-0318/#background) to show the decorator function and pass it to the function below

  ```py
  def my_decorator(func):
      def wrapper():
          print("Something is happening before the function is called.")
          func()
          print("Something is happening after the function is called.")
      return wrapper

  @my_decorator
  def say_whee():
      print("Whee!")
  ```
  
  * `@my_decorator` is the same as setting `say_whee = my_decorator(say_whee)`

* If you want to pass a function that takes arguments into a decorator function, you will need to use `*args and **kwargs`
  * These will accept an arbitrary number of positional and keyword arguments
  * **Make sure that the wrapper function returns the return value of the decorated function**

  ```py
  def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs) # wrapper function needs to return the return value of the decorated function
    return wrapper_do_twice

  @do_twice
  def return_greeting(name):
      print("Creating greeting")
      return f"Hi {name}"

  return_greeting("Adam")
  # Creating greeting
  # Creating greeting
  # 'Hi Adam'
  ```
