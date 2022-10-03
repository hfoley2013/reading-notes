# Getting Started

## Readings

* [Getting Started](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)
* [How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
* [Website Design & Process](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)
* [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

## Assignment

* [X] Compose a short poem describing how HTTP sends data between computers.
* [X] Describe how HTML, CSS, and JS files are “parsed” in the browser.
* [X] How can you find images to add to a Website?
* [X] How do you create a `String` vs a `Number` in JavaScript?
* [X] What is a `Variable` and why are they important in JavaScript?

## Getting Started w/ the Web

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

## [How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

* Clients & Servers
  * Clients are internet-connected devices and web-accessing software
  * Servers are computers that store webpages, sites or apps
  * When a client wants to access a webpage, a copy of that webpage is downloaded from the server onto the client machine and displayed in their web browser
    * **Clients send requests** to servers; **servers send responses** back to the client
* Definitions
  * [Hypertext Transfer Protocol (HTTP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
    * It is *the* protocol for fetching resources such as HTML documents and is the foundation of any data exchange on the Web
    * Defines the language for clients and servers to speak to each other
    ![HTTP Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/fetching_a_page.png)
    ![Foundations of a Webpage](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http-layers.png)
  * Domain Name System (DNS)
    * An address book of websites
    * Browser looks at the DNS of the webpage to find the IP address and return a copy of the webpage
  * Transmission Control Protocol / Internet Protocol (TCP/IP)
    * Define *how* data should travel across the internet
* What happens when you type a web address into your browser?
  1. The browser goes to the DNS server, finds the IP address of the website
  2. The browser sends an HTTP request message to the server storing the webpage and asks for a copy via TCP/IP
  3. If the request is approved, the server sends the client a "200 OK" message, and starts sending the website's files to the browser in a series of data packets
  4. The browser assembles the data packets into a complete webpage and displays it to the user
* Parsing Order of Component Files
  * HTML files ofter contain `<link>` elements that reference external CSS sytlesheets and `<script>` elements referencing external JavaScript scripts
  * The browser parses these in the following order:
    1. HTML
        * This leads the browser to recognize any `<link>` and `<script>` elements
    2. CSS
        * Browser sends requests back to the server for CSS files found in `<link>` elements
    3. JavaScript
        * Browser sends requests back to the server for JS files found in `<script>` elements
    4. The browser generates an in-memory DOM tree from the parsed HTML, an CSSOM structure from the parsed CSS, and complies and executes the parsed JavaScript
    5. As teh browser builds the DOM tree and applies the styles from the CSSOM tree and executes the JavaScript, a visual representation of the webpage is loaded onto the user's screen
  
## [Website Design & Process](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)

* Planning
  1. **What is your website about?**
  2. **What information are you presenting on the subject?**
  3. **What does your website look like?**
* Sketching
  * Sketch out the general layout of the webpage
  * Keep it high-level
    * Generally, where do you want your logo, menu items, main text, etc.
* Choosing Your Assets
  * Text
    * The actual words you want displayed on the webpage
  * Colors
    * You can use tools like the [Adobe Color Wheel](https://color.adobe.com/create/color-wheel) to pick colors are retrieve their *hex codes*
    * Copy down the color codes and keep them for reference
  * Images
    * You can choose images off of Google Images
      * Be sure to go to `Tools` >> `Usage Rights` and select `Creative Commons licenses`
        * These images are in the public domain and do not require any rights to use them
    * You can also upload image files to your repository for use as well
    * Placeholder images/shapes can be generated using the [Better Placeholder](https://betterplaceholder.com/) website
  * Font

## [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

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
    | Object | Everything in JS is an object. | `let myVar = document.querySelector('h1'); |