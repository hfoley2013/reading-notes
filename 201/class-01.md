# Class 1: Reading Note & Assignment Summary

## Assignments

### Getting Started

* **Compose a short poem describing how HTTP sends data between computers.**
  * From client to server requests are sent
  
    From server to client go the responses across the internet

    Do I `GET` or do I `POST`? HTML tells how my data packets flow
* **Describe how HTML, CSS, and JS files are “parsed” in the browser.**
  * Component files are parsed in the following order:
    1. HTML
    2. CSS
    3. JS
    4. Webpage is loaded & user can interact with it
* **How can you find images to add to a Website?**
  * You can choose images off of Google Images
    * Be sure to go to `Tools` >> `Usage Rights` and select `Creative Commons licenses`
      * These images are in the public domain and do not require any rights to use them
  * You can also upload image files to your repository for use as well
  * Placeholder images/shapes can be generated using the [Better Placeholder](https://betterplaceholder.com/) website
* **How do you create a `String` vs a `Number` in JavaScript?**
  * `Strings` are signified by `' '`
  * `Numbers` do not require anything, though you may need to change user inputs into numbers using `parseInt()`
* **What is a `Variable` and why are they important in JavaScript?**
  * A variable is a container that *stores* values
  * Declared using `let`
  * Important because they allow us to reuse and reference blocks of code

### Introduction to HTML

* **What is an HTML attribute?**
  * Contain extra information about an element that won't appear in the content
* **Describe the Anatomy of an HTML element.**
  * Opening Tag
  * Content
  * Closing Tag
  ![Anatomy of an HTML Element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-small.png)
* **What is the Difference between `<article>` and `<section>` element tags?**
  * `<article>` tags are used to identify standalone content
    * Content within these tags should make sense as a standalone document
  * `<section>` tags are used when a more descriptive semantic element is not available
    * This tag should be used when the content cannot be broken out from the `<main>` content, but can be organized to control flow
* **What Elements does a “typical” website include?**
  * Header `<header>`
  * Navigation Bar `<nav>`
  * Main Content `<main>`
    * Can be subdivided by:
      * `<article>` for standalone content
      * `<section>` to identify specific sections of content
      * `<div>` as a generic content holder for styling application with CSS
  * Sidebar `<aside>`
  * Footer `<footer>`
* **How does metadata influence Search Engine Optimization?**
* **How is the `<meta>` HTML tag used when specifying metadata?**

### How to Start to Design a Website

* **What is the first step to designing a Website?**
* **What is the most important question to answer when designing a Website?**

### Semantics
* **Why should you use an `<h1>` element over a `<span>` element to display a top level heading?**
* **What are the benefits of using semantic tags in our HTML?**

### What is JavaScript?
* **Describe 2 things that *require* JavaScript in the Browser?**
* **How can you add JavaScript to an HTML document?**

## Reading Notes Summary

### [Getting Started w/ the Web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)

* This landing page provides access to additional articles on the basics of web development
* Guides included:
  * [Installing Basic Sofware](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Installing_basic_software)
  * [What will you first website look like?](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)
  * [Dealing with files](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files)
  * [HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
  * [CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
  * [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
  * [Publishing your sample code](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Publishing_your_website)
  * [How the web works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
* What happens when you type a web address into your browser?
  1. The browser goes to the DNS server, finds the IP address of the website
  2. The browser sends an HTTP request message to the server storing the webpage and asks for a copy via TCP/IP
  3. If the request is approved, the server sends the client a "200 OK" message, and starts sending the website's files to the browser in a series of data packets
  4. The browser assembles the data packets into a complete webpage and displays it to the user
* Parsing Order of Component Files
  * HTML files ofter contain `<link>` elements that reference external CSS sytlesheets and `<script>` elements referencing external JavaScript scripts
  * The browser parses these in the following order:
    1. HTML
    2. CSS
    3. JavaScript
    4. The browser generates an in-memory DOM tree from the parsed HTML, an CSSOM structure from the parsed CSS, and complies and executes the parsed JavaScript
    5. As the browser builds the DOM tree and applies the styles from the CSSOM tree and executes the JavaScript, a visual representation of the webpage is loaded onto the user's screen
* Website Design & Process
  * Plan
    1. **What is your website about?**
    2. **What information are you presenting on the subject?**
    3. **What does your website look like?**
  * Sketch
    * Wireframe the design and give a high-level overview of where specific elements will go on the webpage
  * Choose Assets
    * Text
    * Colors
    * Images
    * Fonts
* JavaScript Basics
  * JavaScript adds ***interactivity*** to a website
  * JavaScript is referenced by an HTML file via the `<script>` element
    ``` js
    <script src="scripts/main.js"></script>
    ```
  * JS Language Basics
    * Variables
      * Containers that *store* values
      * Declared using `let`
      * Data Types
      
      | **Variable** | **Explanation** | **Example** |
      | --- | --- | --- |
      | String | Text. Signified by `''` | ```let myVar = `Bob`;``` |
      | Number | Number. | `let myVar = 10;` |
      | Boolean | True/False. Used with keywords `true` & `false` | `let myVar = true;` |
      | Array | Multiple values stored in a single reference. Signified by `[]` | `let myVar = ['Bob','Steve','John'];` <br> Refer to each member of the array like this: `myVar[0], myVar[1], etc.` |
      | Object | Everything in JS is an object. | `let myVar = document.querySelector('h1');

### Intro to HTML

* What is HTML?
  * Hypertext Markup Language
  * Tells web browsers *how to structure* the webpage
* Composed of elements
![Anatomy of an HTML Element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-small.png)
* Attributes can provide additional information about an element that *does not* display in the content of the webpage
![Attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-attribute-small.png)
* Basic Document Structure
  * Header `<header>`
  * Navigation Bar `<nav>`
  * Main Content `<main>`
    * Can be subdivided by:
      * `<article>` for standalone content
      * `<section>` to identify specific sections of content
      * `<div>` as a generic content holder for styling application with CSS
  * Sidebar `<aside>`
  * Footer `<footer>`

### Miscellaneous

* [Notes to add]