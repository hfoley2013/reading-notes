# Class 7: Reading Notes & Assignment Summary

## Assignments

### Domain Modeling

* **Explain why we need domain modeling.**
  * We need domain modeling to conceptualize how to best solve a problem
  * Creating an object-oriented model allows us to store data in properties and show the data should behave using methods
  * A well build model serves as a means by which teams can verify and validate their understanding of the problem and define the vocabulary used within and between the tech and business teams

### HTML Table Basics

* **Why should tables not be used for page layouts?**
  * Table layouts reduce accessibility for visually impaired users since table tags are harder to interpret for screen readers
  * Tables produce a lot of tags that define specific elements within the table, creating confusion
  * Tables are not automatically response, you must manually update their formatting when content changes since they auto-fit to their content by default
* **List and describe 3 different semantic HTML elements used in an HTML `<table>`.**
  * `<th>` defines a tables headers
  * `<tr>` defines the rows of data
  * `<td>` defines the data in the table

### Introducing Constructors

* **What is a constructor and what are some advantages to using it?**
  * A function that creates and returns a new object with the properties that you define
  * This allows you to makes your code more efficient and reuseable by *binding* `this` to the properties you define within the constructor
* **How does the term `this` differ when used in an object literal versus when used in a constructor?**
  * When used in an object literal, `this` can only refer to the object in which it is embedded
  * When used in a constructor, all new properties *bind* to `this`, allowing you to use it throughout all objects created by the constructor

### Object Prototypes Using A Constructor

* **Explain prototypes and inheritance via an analogy from your previous work experience.**
  * *NOTE: This is a very common front end developer interview question*
  * Prototypes are a mechanism by which JS objects inherit features from other objects
  * When you try to access a property of an object and it can't be found in the object itself, the prototype is searched for the property. If it still can't be found, the prototypes prototype gets searched (and so on, and so on, until the property or `null` is returned)
  * This would be like trying to find the nationality of a child if it wasn't documented in their records. The prototype would reference back to the parent of the child and look for `nationality`. If it couldn't find it in the parents' records, it would look at the grandparents, and keep going back until it ran out of ancestor prototypes to search or it found an answer.
