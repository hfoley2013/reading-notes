# In Class Notes: Classes & Objects

## Notes

### What is a class?

* A blueprint for creating objects in Python

### What is an object?

* Everything is an object in Python
* Python is an Object Oriented Programming Language

## Examples

* Initiate a new class

```py
# base class
class Dog:
  def __init__(self, name):
    self.name = name

# derived class
class Boxer(Dog):
  pass

class Pug(Dog):
  pass
```

* Analogy to JS React
  * `self` is like the contextual `this`
    * `self` is inherent to the class, like `this`
    * It allows you to pull contextual information out of the class using .dot notation

* Example tests

![Class Test Examples](./img/class_and_objects.png)
