# # Class 10: Reading Notes & Assignment Summary

## References

* [Debugging HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML)
* [Debugging CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Debugging_CSS)

## Assignments

### Troubleshooting JavaScript

* **Name some key differences between a Syntax Error and a Logic Error.**
  * Logic Errors occur when the code runs, but produces the wrong answer
    * This hard to debug since there are no error codes to point out where the problem may be
    * You will have to trace out the logic of the code to find the issues
  * Syntax Errors are spelling or marker mistakes that cause your code to break
    * These are easier to fix since they generate error codes that specify the type of error and what line and character the error begins on
* **List a few types of errors that you have encountered in past lab assignments and explain how you were able to correct them.**
  * Almost all of my errors have been various syntax errors resulting from misspelling a word or two
  * To fix these, I read the error message presented in the console and went straight to the line where the error occurred
  * Generally speaking, these errors were obvious enough that a minute or two checking spelling resolved the issue
* **How will this topic continue to influence your long term goals?**
  * Efficiently debugging is a critical skill to a developer
  * Code is going to break or produce the wrong output from time to time, so being able to quickly diagnose where an error is and why it occurred in order to resolve it will be a key part of the job

### The JavaScript Debugger

* **How would you describe the JavaScript Debugger tool and how it works to someone just starting out in software development?**
  * The Debugger tool is a developer tool that run in your browser that you can access in order to inspect your JS code when it isn't working properly
  * You can do this by setting breakpoints in your code to diagnose exactly what line of code the problem begins
  * Additionally, you can watch the value of variables change as your script runs through the code block up until the breakpoints you set
* **Define what a breakpoint is.**
  * A manually selected line in your code at which you want the code to stop running
* **What is the call stack?**
  * A section in the Debugger that shows you what code was executed to get to the current line

## In Class Notes

### Code Review

* DRY out code by creating a helper function
  * function `createElement(element, content)`


### Debugging

* [When Stuck, Talk to the Duck](https://www.mindovermachines.com/when-you-get-stuck-talk-to-the-duck/)
  * Talk it out to yourself and explain it your rubber duck
* Lots of `console.log`
* Google syntax issues
* Ping classmates and talk it out; get a second set of eyes
* Compare changes to previous version of the code on GitHub that was working

## Image Files

* Pixel based
  * Bunch of little dots clumped together that at a distance look like an image
  * Great for photographs
* Vector based
  * Match makes the image
  * Great for line art used
  * Doesn't lose definition as you change size

### Which Image Type Should I Use?

![Image Selection](201/images/image-type-selection.png)

* Use Font Awesome to get icons
  * Link to Font Awesome in `<head>`
  * Insert a `<span class="sr-only">HoverMessage</span>` within the `<i>` tag to announce the info to a Screen Reader
