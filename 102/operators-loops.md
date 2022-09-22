# Operators and Loops in JavaScript

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

# Adding JS Strings

* The `+` operator can also be used to concatenate strings
* This also applies adding numbers and strings together, however, the final output will be a ***string***, *NOT* a number

``` js
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2;

// output of text3 = 'John Doe'
```

# Comparison Operators


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
