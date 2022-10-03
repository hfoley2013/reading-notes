# Miscellaneous

## Readings

* [How to Start to Design a Website](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Thinking_before_coding)
* [Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
* [What is JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)


## Assignment

* How to Start to Design a Website 
  * [X] What is the first step to designing a Website?
  * [X] What is the most important question to answer when designing a Website?
* Semantics
  * [X] Why should you use an `<h1>` element over a `<span>` element to display a top level heading?
  * [X] What are the benefits of using semantic tags in our HTML?
* What is JavaScript?
  * [X] Describe 2 things that *require* JavaScript in the Browser?
  * [X] How can you add JavaScript to an HTML document?
  
## How to Start to Design a Website

* **Project Ideation**
  * What *exactly* do I want to accomplish?
  * How will a website help me reach my goals?
  * What needs to be done, and in what order, to reach my goals?

## Semantics

* Semantics refers to the *meaning* of code
  * What effect does running that line of JS have?
  * What purpose or role does that HTML element have?
* Semantic Elements
  
  ``` html
  <article>
  <aside>
  <details>
  <figcaption>
  <figure>
  <footer>
  <header>
  <main>
  <mark>
  <nav>
  <section>
  <summary>
  <time>
  ```

## What is JavaScript

* JavaScript is a lightweight interpreted scripting language that allows you to interact with a webpage
* Allows the website to store values inside variables and use them to provide outputs to the user or change the webpage
* Common use of JS is to dynamically modify HTML and CSS to update a user interface via the Document Object Model API
* Added into the HTML document via the `<script>` tag
* Using `addEventListener`
  
  ``` js
    const buttons = document.querySelectorAll('button');

  for (const button of buttons) {
    button.addEventListener('click', createParagraph);
  }
  ```

* Script Loading Strategies
  
  ``` js
  document.addEventListener('DOMContentLoaded', () => {
  // …
  });
  ```

  * `defer` attribute tells the browser to continue downloading the HTML content once the `<script>` tag element has been reached
  
  ``` js
  <script src="script.js" defer></script>
  ```

* `async` attribute tells the browser to download the script without blocking the page while the script is being fetched
  * Best to use `async` when the scripts in the page run independently from each other and depend on no other script on the page
    * Ex: When you have a bunch of background scripts to load in, and you want them loaded as soon as possible