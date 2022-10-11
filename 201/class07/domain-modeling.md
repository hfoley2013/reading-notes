# Domain Modeling

## Reading

* [Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)

## Notes

### What is Domain Modeling

* Domain modeling is the process of creating a conceptual model in code for a specific problem
* The model describes the entities, attributes and behaviors, as well as constraints governing the problem domain
* **Object-oriented** models store data in properties and encapsulate behaviors in methods
* Tips for building domain models:
  * When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
  * Model its attributes with a constructor function that defines and initializes properties.
  * Model its behaviors with small methods that focus on doing one job well.
  * Create instances using the `new` keyword followed by a call to a constructor function.
  * Store the newly created object in a variable so you can access its properties and methods from **outside**.
  * Use the `this` variable within methods so you can access the object's properties and methods from **inside**.

### Constructors

* A constructor is a function that defines and initializes properties
  * Can basically construct an object consisting of similarly defined objects for later use by the program
* Example:
  
  ``` js
  var EpicFailVideo = function(epicRating, hasAnimals) { //Constructor function
    this.epicRating = epicRating; // Property 1
    this.hasAnimals = hasAnimals; // Property 2
  }

  var parkourFail = new EpicFailVideo(7, false); // Instantiates a new object parkourFail(7,false)
  var corgiFail = new EpicFailVideo(4, true); // Instantiates a new object corgiFail(4,true)

  console.log(parkourFail);
  console.log(corgiFail);
  ```
* This is object-oriented programming in JavaScript at its most fundamental level:
  * The `new` keyword instantiates (i.e. creates) an object.
  * The constructor function initializes properties inside that object using the this variable.
  * The object is stored in a variable for later use.
