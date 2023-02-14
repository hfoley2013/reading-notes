# Pythonisms

## Readings

* [Iterators](https://dbader.org/blog/python-iterators)
* [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
* [Generators](https://dbader.org/blog/python-generators)

## Notes

### Iterators

In Python, an iterator is an object that **produces a sequence of values**, typically used in loops

* Implements the ***iterator* protocol**, which requires the methods `__iter__()` and `__next__()` to be defined
  * `__iter__()` returns the iterator object itself
  * `__next__`() returns the next value in the sequence
    * When there are no more values to return, the `__next__`() method should raise the `StopIteration` exception
* Iterators can be created using the `iter()` function or by defining a class that implements the iterator protocol

```py
# Define the class
class EvenIterator:
    def __init__(self):
        self.current = 0
        self.limit = 10
    def __iter__(self):
        return self
    def __next__(self):
        if self.current >= self.limit:
            raise StopIteration
        else:
            self.current += 2
            return self.current

# Use in a for loop like this:
for num in EvenIterator():
    print(num)
# Output: 2,4,6,8,10
```

### Dunder Methods

* Part of Python's **data model** that allow you to define custom behavior of your objects
* Common dunder methods:
  * `__init__(self, ...)`: This method is called when an instance of the class is created. It is used to initialize the object's attributes.
  * `__repr__(self)`: This method returns a string that represents the object in a way that can be used to recreate the object.
  * `__str__(self)`: This method returns a string that represents the object in a human-readable format.
  * `__len__(self)`: This method returns the length of the object.
  * `__getitem__(self, key)`: This method allows the object to be accessed using square brackets, like a list or dictionary.
  * `__setitem__(self, key, value)`: This method allows the object to be updated using square brackets, like a list or dictionary.
  * `__delitem__(self, key)`: This method allows items to be deleted from the object using the del statement.
  * `__iter__(self)`: This method returns an iterator object that can be used to loop over the object.
  * `__next__(self)`: This method returns the next item in the iterator returned by __iter__().
  * `__call__(self, ...)`: This method allows the object to be called like a function.
  * `__enter__(self)`: This method is called when the object is used in a with statement.
  * `__exit__(self, exc_type, exc_value, traceback)`: This method is called when the with block is exited.
  * `__getattr__(self, name)`: This method is called when an attribute is accessed that doesn't exist. It can be used to dynamically create attributes.
  * `__setattr__(self, name, value)`: This method is called when an attribute is set. It can be used to add custom behavior when attributes are set.
  * `__delattr__(self, name)`: This method is called when an attribute is deleted. It can be used to add custom behavior when attributes are deleted.
* `@propery` decorator: allows you access a method in the same manner as a property, i.e. without `()` to call the method

### Generators

A generator is a function that produces a sequence of values, typically used in loops, similar to an iterator. The main difference is that generators use the `yield` keyword to return values one at a time, rather than returning all values at once as iterators do.

When a generator function is called, it returns a generator object, which can be used to iterate over the sequence of values. Each time the `yield` keyword is encountered in the function, the current value is returned to the caller, and the function's state is saved. The next time the generator is called, execution resumes from where it left off, and the function continues until it encounters another `yield` statement.

Generators are useful for generating large sequences of values, particularly when it would be memory-intensive to store all the values at once. Because generators produce values on the fly, they can be more memory-efficient than other approaches.

```py
# Generates the first 5 even numbers
def even_numbers():
    current = 0
    limit = 10
    while current < limit:
        yield current
        current += 2

# Call the even_numbers generator
for num in even_numbers():
    print(num)
# Output: 0,2,4,6,8
```

**NOTE:** The `even_numbers()` function is defined like a normal function, but it uses the `yield` keyword to **generate values one at a time**.
