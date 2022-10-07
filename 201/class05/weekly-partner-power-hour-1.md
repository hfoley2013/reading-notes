# Partner Power Hour 1: Wes Reid

## Assignment

* **Who was the speaker(s) and what company or companies were they from? What was the topic of the talk?**
  * *Speaker*: Wes Reid
  * *Topic*: Refactoring
* **Share 1 or 2 ways the speaker’s information will change your approach to your career transition.**
  * After watching the presentation, I took the following as action items for Lab 2/3/4 code:
    1. Create *helper functions* for repeated chunks of code for correct & incorrect answers
    2. *Utilize maps* to simplify the lines of code needed to pose the 7 questions, answers, and responses
* **Do you have any other key take-aways, or observations about this Partner Power Hour?**
  * You should consider refactoring if:
    * A function or file is so large that it has become unreadable by anyone but the owner
    * Code is being duplicated in multiple files
    * Number of comments needed to understand the code is greater than the number of lines of code
    * If you are constantly using some bit of hard to understand code

## Notes

### Refactoring

* *The process of reorganizing, renaming, or rewriting code in an attempt to improve:
  * **Efficiency**: How many lines of code it takes to run
  * **Readability**: How easy it is for someone to look at, understand, and audit the code
  * **Reusability**: How easy it is to update

### You Code Sucks

* You should consider refactoring if:
  * A function or file is so large that it has become unreadable by anyone but the owner
  * Code is being duplicated in multiple files
  * Number of comments needed to understand the code is greater than the number of lines of code
  * If you are constantly using some bit of hard to understand code

### Tips

* Avoid magic numbers
  * Any numbers used in the code block should be tied to some variable name
  
  ``` js
  // Bad >> What is 10?
  cost = quantity * 10

  // Good >> 10 is defined as price
  let price = 10
  cost = quantity * price
  ```

* Leverage Maps
  * Switch statements or long conditional statements can sometimes be replaced with an object
* Rename Boolean Variables
  * Give boolean variables names that imply they are boolean

  ``` js
  //Bad >> subscriber could be anything
  subscriber = true

  // Good >> is_subscriber implies y/n question
  is_subscriber = true
  ```

* Use more variables
  * Break apart complex statements with variables
