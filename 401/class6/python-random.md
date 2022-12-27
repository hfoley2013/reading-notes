# Python Random

## Readings

* [How to use Random Module](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)
* [What is Risk Analysis](https://www.edureka.co/blog/risk-analysis-in-software-testing/)
* [Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)
* [What is Dependency Injection?](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)

## Reference

* [Python Random](https://docs.python.org/3/library/random.html)

### How to Use the Random Module

* Must import the `random` module
  * `import random`
* Pick a random number within a range
* Create random strings while choosing **passwords** to make your password database more secure or power a random page feature of your website
* `randint()`
  * Takes two parameters:
    * First num: start number
    * Second num: end number
  * Will generate random numbers within the range
  `randint(0,5)` will generate random numbers between 1 & 5
* `random()`
  * Generates random number between 0 & 1
  * Takes no arguments
  * If you want a larger number, just multiply by some factor
  * `random.random() * 100`
* `choice()`
  * Selects a random element from a collection object like a list, set, tuple, etc
  * Takes a collection object as an argument and returns a random element
  * `random.choice( ['red', 'black', 'green'] )`
* `shuffle()`
  * Shuffles a list
  
  ```py
  from random import shuffle
  x = [[i] for i in range(10)]
  shuffle(x)
  ```

* `randrange()`
  * Selects a random element from a given range
  * `random.randrange(start, stop[, step])`
  * start = starting number in range
  * stop = last number in range
  * step = incremental step between start and stop value

### Dependency Injection

Dependency injection is a **software design pattern** that allows a programmer to **specify the dependencies for a class in a separate location** from the class itself. The main idea behind dependency injection is to reduce the tight coupling between software components by allowing the dependencies of a class to be **injected at *runtime***, rather than being hard-coded into the class.

There are several benefits to using dependency injection:

* It allows a programmer to specify the dependencies of a class in a separate location, which can make the class easier to test and maintain.

* It makes it easier to change the dependencies of a class without modifying the class itself.

* It can help to decouple the dependencies of a class from the class itself, which can make it easier to reuse the class in different contexts.

There are several different ways to implement dependency injection, including:

* **constructor injection**
* **setter injection**
* **interface injection**

The specific technique used may depend on the programming language and the specific needs of the application.

#### Example: Constructor Injection

Constructor injection is a common way to implement dependency injection, because it allows the dependencies of a class to be specified when the class is instantiated. This can be especially useful when the dependencies are required for the class to function properly.

Say we have a class called `Person` that has a dependency on a `Car` class. We can use dependency injection to specify the `Car` dependency in a separate location from the Person class itself. In this case, the dependency is injected through the constructor of the class (`Person`).


1. Define the `Car` class

```py
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
    
    def drive(self):
        print(f"Driving a {self.make} {self.model}")
```

2. Define the `Person` class with a `drive` method that has a `Car` dependency

```py
class Person:
    def __init__(self, car):
        self.car = car
    
    def drive(self):
        self.car.drive()
```

3. Can now create an instance of `Car` and pass it to the `Person` constructor as a dependency

```py
car = Car("Toyota", "Camry")
person = Person(car)
person.drive()

# Outputs: 'Driving a Toyota Camry'
```

By using dependency injection, we were able to specify the `Car` dependency in a separate location from the `Person` class, which makes it easier to test and maintain the `Person` class.
