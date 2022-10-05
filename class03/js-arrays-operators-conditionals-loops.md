# JavaScript Arrays, Operators, Conditionals, and Loops

## Readings

* [Arrays](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)
* [Operators and Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
* [Conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)
* [Loops](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code)

## Arrays

* `[ ]` designates an `Array`
* Arrays can carry and value, including additional arrays (multidimensional array)
* `.length` will return the number of items inside an array
* Items inside an array can be accessed using `arrayName[#]`
  * **Items start at `0`**
* Multidimensional arrays are accessed using `arrayName[#][#]`
* Finding items in an array
  * `indexOf()`
    * Takes an item as an argument and returns the location inside the array, or `-1` if the item is not in the array

  ```js
  const birds = ['Parrot', 'Falcon', 'Owl'];
  console.log(birds.indexOf('Owl'));   //  2
  console.log(birds.indexOf('Rabbit')); // -1
  ```
* Adding items to an array
  * `.push()`
    * Takes an item as an argument and *pushes* it to the **end** of the array
  * `.unshift()`
    * Takes an item as an argument and *shifts* it to the **beginning** of the array
* Removing items from an array
  * `.pop()`
    * *Pops* off the **last** value in an array
  * `.shift()`
    * Removes the **first** value in an array
  * `.splice()`
    * Takes *two* arguments
      * First is *where to start* **removing**
      * Second is *how many to remove*

  ``` js
    const cities = ['Manchester', 'Liverpool', 'Edinburgh', 'Carlisle'];
    const index = cities.indexOf('Liverpool');
    if (index !== -1) {
      cities.splice(index, 2);
    }
    console.log(cities);     // [ "Manchester", "Carlisle" ]
    ```
* Accessing every item
  * `of`
    * Usually used in conjunction with `for`
    * Will allow you go through each item in an array in a loop
  
  ``` js
  const pets = ['cat', 'dog','bird'];

  for (const pet of pets) {
    console.log(pet);
   }; // >>Will list out each item in pets
  ```
  * `map()`
    * *Invokes a function* on the items in an array and **creates a new array** with the results
* Converting between `strings` and `arrays`
  * `.split()`
    * Takes a delimiter as an argument and *splits* a string into an array
  * `.join()`
    * Takes a delimiter as an argument and *joins* items in an array as a string with the delimiter separating the items
  * `.toString()`
    * Converts an array to a string, but can only use a `,` as the delimiter

## Operators & Expressions

### Shorthand Assignment Operators

| **Name** | **Shorthand operator** |	**Meaning** |
| --- | --- | --- |
| Assignment	| x = f()	| x = f() |
| Addition assignment	| x += f() | x = x + f() |
|Subtraction assignment |	x -= f()	| x = x - f() |
| Multiplication assignment |	x *= f() |	x = x * f() |
| Division assignment |	x /= f() |	x = x / f() |
| Remainder assignment |	x %= f() |	x = x % f() |
| Exponentiation assignment |	x **= f() |	x = x ** f() |
| Left shift assignment |	x <<= f() |	x = x << f() |
| Right shift assignment |	x >>= f() |	x = x >> f() |
| Unsigned right shift assignment |	x >>>= f() |	x = x >>> f() |
| Bitwise AND assignment |	x &= f() |	x = x & f() |
| Bitwise XOR assignment |	x ^= f() |	x = x ^ f() |
| Bitwise OR assignment |	x \|= f() |	x = x \| f() |
| Logical AND assignment |	x &&= f() |	x && (x = f() |) |
| Logical OR assignment |	x \|\|= f() |	x \|\| (x = f()) |
| Logical nullish assignment |	x ??= f() |	x ?? (x = f()) |
