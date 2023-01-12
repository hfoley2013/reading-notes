# Automation

## Readings

* [Python Regular Expressions Tutorial](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)
* [shutil](https://pymotw.com/3/shutil/)
* [VIDEO: Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)
* [Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)

## Reference

* [Watchdog](https://pythonhosted.org/watchdog/)

## Notes

### RegEx

* Import from the `re` library
  * `import re`
* Use `r"sequence"` to define the regex expression
  ```py
  pattern = r"Cookie"
  sequence = "Cookie"
  if re.match(pattern, sequence):
      print("Match!")
  else: print("Not a match!")
  ```

* `search`
  * With the search function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match
* `group`
  * The group function returns the string matched by the re
  
  ```py
  re.search(r'Co.k.e', 'Cookie').group()
  # Returns: 'Cookie'
  ```

  * Note: A `.` will match any single character except the newline character
* `^` matches the beginning of a string
* `$` matches the end of a string
* `[abc]` matches `a`, `b`, or `c`
* `[a-zA-Z0-9]` - Matches any letter from (a to z) or (A to Z) or (0 to 9)
* `\w` - Lowercase 'w'. Matches any single letter, digit, or underscore.
* `\W` - Uppercase 'W'. Matches any character not part of \w (lowercase w).
* `\s` - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.
* `\S` - Uppercase 'S'. Matches any character not part of \s (lowercase s).
* `\d` - Lowercase d. Matches decimal digit 0-9.
* `\D` - Uppercase d. Matches any character that is not a decimal digit.
* `\t` - Lowercase t. Matches tab.
* `\n` - Lowercase n. Matches newline.
* `\r` - Lowercase r. Matches return.
* `\A` - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.
* `\Z` - Uppercase z. Matches only at the end of the string.
* `\b` - Lowercase b. Matches only the beginning or end of the word.
* `+` - Checks if the preceding character appears one or more times starting from that position.
* `*` - Checks if the preceding character appears zero or more times starting from that position.
* `?` - Checks if the preceding character appears exactly zero or one time starting from that position.
* `{x}` - Repeat exactly x number of times.
* `{x,}` - Repeat at least x times or more.
* `{x, y}` - Repeat at least x times but no more than y times.
* `{ }`	- Checks for an explicit number of times.
* `( )`	- Creates a group when performing matches.
* `< >` -	Creates a named group when performing matches.
