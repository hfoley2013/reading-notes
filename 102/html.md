# HTML & Webpage Structure

[Wireframing & Design](#wireframing--designhttpscareerfoundrycomenblogux-designhow-to-create-your-first-wireframe)

[HTML Basics](#html-basicshttpsdevelopermozillaorgen-usdocslearngettingstartedwiththewebhtmlbasics)

[Semantics](#semanticshttpsdevelopermozillaorgen-usdocsglossarysemantics)

## [Wireframing & Design](https://careerfoundry.com/en/blog/ux-design/how-to-create-your-first-wireframe/)

### What is a wireframe?

* Wireframing is a practice used by UX designers to sketch out the structure of a webpage before coding it
* The purpose is to plan the information hierarchy of the page and how the owner wants the information displayed

![Wireframing Example](https://dpbnri2zg3lc2.cloudfront.net/en/wp-content/uploads/old-blog-uploads/versions/samuel-student-wireframe---x----972-715x---.png)

### Steps to Make a Wireframe

1. Do your research
   * Understand who your audience is
   * Create user personas
   * Define use cases
   * Compile this info with industry research
2. Prepare your research for quick reference
   * Document your research in a way such that it is easy to retrieve information and notes during the design process
3. Map your user flow
   * How will the user move through the website?
   * Where do you want to ultimately guide the user to?
   * How can you best channel them to the desired end point?
4. Draft, don't draw. Sketch, don't illustrate
   * The wireframe is on outline, not the end product
   * Don't bog yourself down in the details too early
   * Define your work in chunks or blocks
   * Questions to ask your self while sketching:
     * How can you organize the content to support your users’ goals?
     * Which information should be most prominent? Where should your main message go? What should the user see first when arriving at the page?
     * What will the user expect to see on certain areas of the page?
     * Which buttons or touch points does the user need to complete the desired actions?
5. Add some detail and get testing
   * Start adding in some detail, top to bottom, left to right
   * Conduct an initial test batch of code and send to the owner/users for feedback
6. Start turning your wireframes into prototypes
   * Begin iterating on prototypes and seek feedback frequently

## [HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)

### What is HTML?

* HyperText Markup Language
* Used to structure a web page and its content
* Consists of a series of elements that you use to enclose, or wrap, different parts of the content to make it appear or act a certain way

### Anatomy of an HTML Element

![HTML Element](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

* The **opening tag** designates the element type
* The **closing tag** designates where the effect of the element ends and consists of the *forward slash* `/`
* **Content** is what will be affected by the HTML tags
* The **element** is everything put together

Elements can also have **attributes** that contain extra information about the element that will not appear as content

![Attribute Example](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

### Anatomy of an HTML Document

* ***Always*** starts with `<!DOCTYPE html>`
* All html content is contained between `<html> </html>` tags
* A header `<head></head>` tag acts as a container for things that you want to include on the HTML page that ***are not*** the content you display
* A title `<title></title>` tag sets the title of your page, which will be displayed in the browser tag
* A `<body></body>` tag contains all the content that you want to show to web users when they visit the page

``` html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>
```

### Basic HTML Markups

| **Element** | **Syntax** |
| --- | --- |
| Headings |  `<h#></h#>` |
| Paragraph | `<p></p>` |
| Unstructured List | `<ul></ul>` |
| Links | `<a href="url">Text</a>` |
| Images | `<img src="soruce" alt="Alt Text" />` |

## [Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)

* In programming, **Semantics** refers to the meaning of a piece of code
  * "What effect does running that line of JavaScript have?"
  * "What purpose or role does that HTML element have"
  * Focus is on "what is this", rather than "what does it look like?"