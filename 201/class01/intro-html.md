# Introduction to HTML

## Readings

* [Intro to HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)
* [Getting Started w/ HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
* [HTML Document Structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
* [Metadata in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)

## Assignment

* [X] What is an HTML attribute?
* [X] Describe the Anatomy of an HTML element.
* [X] What is the Difference between `<article>` and `<section>` element tags?
* [X] What Elements does a “typical” website include?
* [X] How does metadata influence Search Engine Optimization?
* [X] How is the `<meta>` HTML tag used when specifying metadata?

## Intro to HTML

* This landing page provides several guides for using HTML:
  * [Getting Started w/ HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
  * [What's in the head? Metadata in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)
  * [HTML Text Fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)
  * [Creating Hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
  * [Advanced Text Formatting](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)
  * [Document & Website Structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
  * [Debugging HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML)

## Getting Started w/ HTML

* What is HTML?
  * Hypertext Markup Language
  * Tells web browsers *how to structure* the webpage
* HTML Elements
  * Composed of:
    * Opening Tag
    * Content
    * Closing Tag
![Anatomy of an HTML Element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-small.png)
* HTML Attributes
  * Contain extra information about an element that won't appear in the content
  * Attributes should have:
    1. A space between it and the element name
    2. The attribute name, followed by an `=`
    3. An attribute value, wrapping in `" "`
![Attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-attribute-small.png)
  * Attribute Examples
  
  | **Attribute** | **Explanation** | **Example** |
  | --- | --- | --- |
  | `href` | Specifies the web address for a link | `href ="https://www.google.com/" |
  | `title` | Specifies extra info about the link, such as a description of the page being linked to | `title="Google Homepage" |
  | `target` | Specifies the browsing context used to display the link | `target="_blank"` will launch in a new tab |


## HTML Document Structure

* Basic Sections
  * Header `<header>`
    * Big strip across the top with a big heading, logo, and a tagline
    * Usually stays the same from one webpage to another
  * Navigation Bar `<nav>`
    * Links to the site's main sections, usually represented by menu buttons, links, or tabs
    * Usually remains the same across the website
  * Main Content `<main>`
    * Big area in the center that contains most of the content of a given webpage
    * Can be subdivided using `<article>`, `<section>`, and `<div>`
      * `<article>`
        * Represents a self-contained composition within a document that is intended to be independently distributable or reusable
        * Use when the content would make sense as a standalone piece without any additional content from the webpage
        * Can use additional heading elements within the body to create levels of articles to display within the webpage
      * `<section>`
        * Generic standalone section of a document, which does not have a more specific semantic element to represent it
        * **Should only be used if there is not a more specific element to represent it**
      * `<div>`
        * Generic container for flow content
        * Has no effect on the content or layout until styled in some way using CSS
        * **Should only be used when no other semantic element is appropriate**
  * Sidebar `<aside>`
    * Peripheral information, links, quotes, ads, etc.
  * Footer `<footer>`
    * Big strip across the bottom that contains fine print, copyright notices, or contact info

## Metadata in HTML

* Metadata is signified by the `<meta>` tag and is contained in the `<head>` section of an HTML document
* This data is not displayed to site visitors
* Typically contains `<link>` and `<title>` elements to connect to CSS stylesheets and name the browser tab
* Use `charset="utf-8"` to use the universal character code
  * This allows your site to render using just about any character set in any human language
* Adding name and description
  * `<name>` specifies the type of meta element it is; what type of info it contains
  * `<content>` specifies the actual meta content
  * Specifying a description that includes keywords relating to the content of your page is useful as it has the potential to make your page appear higher in relevant searches performed in search engines
  ``` html
  <meta name="author" content="Harper Foley" />
  ```
* Linking to CSS and JavaScript
  * CSS
    * `<link>`
    ``` html
    <link rel="stylesheet" href="my-css-file.css" />
    ```
  * JavaScript
    * `<script>`
    ``` html
    <script src="my-js-file.js"></script>
    ```