# Introducing Constructors

## Reading

* [Constructors](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics#introducing_constructors)

## Notes

* Constructors allow you to **define the shape** of an object using a set of methods and associated properties
* When you use a constructor it will:
  * Create a new object
  * Bind `this` to the new object, so you can refer to this in your constructor code
  * Run the code in the constructor
  * Return the new object.
  
``` js
function Person(name) {
  this.name = name;
  this.introduceSelf = function () {
    console.log(`Hi! I'm ${this.name}.`);
  };
}

```

* This function creates and returns a new object each time we call it
* The object will have two members:
  1. A property called `name`
  2. A method called `introduceSelf()`
* We call `Person()` as a constructor using `new`

``` js
const salva = new Person("Salva");
salva.name;
salva.introduceSelf();

const frankie = new Person("Frankie");
frankie.name;
frankie.introduceSelf();
```
