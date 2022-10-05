# Operators and Loops in JavaScript

[Expressions & Operators - Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

[Loops & Iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)

## Arithmetic Operators

| **Operator** | **Description** |
| --- | --- |
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| ** | Exponential |
| / | Division |
| % | Modulus (Division Remainder) |
| ++ | Increment |
| -- | Decrement |

## Assignment Operators


| **Operator** |	**Example** |	**Same As** |
| --- | --- | --- |
| =	| x = y	| x = y  |
| +=	| x += y |	x = x + y |
| -=	| x -= y	| x = x - y |
| *=	| x *= y	| x = x * y |
| /=	x | /= y	| x = x / y |
| %=	| x %= y	| x = x % y |
| **=	x | **= y	| x = x ** y |

## Adding JS Strings

* The `+` operator can also be used to concatenate strings
* This also applies adding numbers and strings together, however, the final output will be a ***string***, *NOT* a number

``` js
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2;

// output of text3 = 'John Doe'
```

## Comparison Operators


| **Operator** |	**Description** |
| --- | --- |
| ==	| equal to |
| ===	| equal value and equal type |
| !=	| not equal |
| !==	| not equal value or not equal type |
| >	| greater than |
| <	| less than |
| >=	| greater than or equal to |
| <=	| less than or equal to |
| ?	| ternary operator |

## Logical Operators

| **Operator** | **Description** |
| --- | --- |
| && | logical and |
|<code>&#124;&#124;</code> | logical or |
| ! | logical not |

## Type Operators

| **Operator** | **Description** |
| --- | --- |
| typeof | Returns the type of a variable |
| instanceof | Returns true if an object is an instance of an object type |

## Bitwise Operators

* Bit operators work on 32 bits numbers
* Any numeric operand in the operation is converted into a 32 bit number and the result is converted back to a JS number

| **Operator** | **Description** | **Example** | **Same As** | **Result** | **Decimal** |
| --- | --- | --- | --- | --- | --- |
| &	| AND	| 5 & 1	| 0101 & 0001	| 0001	| 1 |
|<code>&#124;</code> | OR	| 5 <code>&#124;</code> 1 |	0101 <code>&#124;</code> 0001	| 0101	| 5 |
| ~	| NOT	| ~ 5	| ~0101	| 1010	| 10 |
| ^	| XOR	| 5 ^ 1	| 0101 ^ 0001	| 0100	|  4 |
| <<	| left shift	| 5 << 1	| 0101 << 1	| 1010 | 10 |
| >>	| right shift	| 5 >> 1	| 0101 >> 1	| 0010	|  2 |
| >>>	| unsigned right shift	| 5 >>> 1 | 0101 >>> 1 | 0010 |  2 |

## Loops and Iteration

* Loops allow you to execute a piece of code to do something repeatedly given a set of conditions
* Types of Loops
  * Do
  * For
  * While

### For Statement

* A `for` loop repeats until a specified condition evaluates to `false`

Syntax:

``` js
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement
```

Example:

``` js
let countDown = 10 // Set initial condition in variable
for (let i = countDown; i >= 0; i--) // While i >= 0, decrement by 1, then exit the loop
  {
    console.log(`${i} second${i !== 1 ? 's' : ''} until lift off!`) // Logs count of i
   }
console.log('Lift Off!') // When i < 0, log 'Lift Off!'
```

### Do...While Statement

* The `do...while` statement repeats until a specified condition evaluates to `false`

Syntax:

``` js
do
  statement
while (condition);
```

Example:

``` js
let i = 0; // Set initial condition
do {  // Do the statement below
  i += 1;
  console.log(i);
} while (i < 5); // While i is < 5
```

### While Statement

* A `while` statement executes its statements as long as a specified condition is `true`
* If the `condition` becomes `false`, `statement` within the loop stops executing and control passes to the statement that follows the loop
  * **NOTE:** The condition test occurs *before* `statement` is the loop is executed
    * If the condition is `true` the loop continues, if `false`, the loop ends and the program moves on to the next block of code

Syntax:

``` js
while (condition)
  statement
```

Example:

``` js
let i = 10
while (i >= 0){ // While i is >= 0, the statement will execute
  console.log(`Countdown: ${i}`) // First log value of i
  i-- // Then decrement i by 1
}
console.log('Blast off!') // When i drops below 0, log 'Blast Off'
```
