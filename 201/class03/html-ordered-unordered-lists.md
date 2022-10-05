# HTML Ordered vs. Unordered Lists


## Readings

* [Ordered Lists](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
* [Unordered Lists](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)

## Notes

### Ordered Lists

* `<ol>` element designates an ordered list
* Ordered lists should be used when there is a sequence of events or steps that need to be followed in order
* These can be represented as a number, roman numeral, or letter sequence

#### Attributes of Ordered Lists

| **Attribute** | **Explanation** |
| --- | --- | 
| `reversed` | Boolean value that indicates if the numbers will present in reverse order | 
| `start` | An Arabic numeral that designates from what number the list will start |
| `type` | What type of list it will be:<br><ul><li>`a` lowercase letters</li><li>`A` uppercase letters</li><li>`i` lowercase Roman numerals</li><li>`I` uppercase Roman numerals</li><li>`1` number (default)</li></ul> |

### Unordered Lists

* `<ul>` element designates an unordered list
* Used when the order of the items in the list is of no consequence
* Bullets can be modified by changing the `type` to represent `circle`, `disc`, and `square`

#### Attributes of Unordered Lists

| **Attribute** | **Explanation** |
| --- | --- | 
| `compact` | Boolean value that determines if the list will display in a compact way or expanded |
| `type` | Changes the bullet styles:<br><ul type="circle"><li>`circle`</li></ul><ul type="disc"><li>`disc`</li></ul><ul type="square"><li>`square`</li></ul> |
