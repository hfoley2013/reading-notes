# Class 5: Reading Notes & Assignment Summary

## Assignments

### HTML Media

* **What is a real world use case for the `alt` attribute being used in a website?**
  * Used when the browser does not display the image
  * Allows user or screen reader to read the text of the image and understand what is supposed to be presented
* **How can you improve accessibility of images in an HTML document?**
  * Name them in a short, but descriptive manner using `alt`
  * Add a `title` attribute that displays info the user when they hover over the image
  * Place the image inside a semantic element like `<figure>` or `<figcaption>` for ease of understanding its rol
* **Provide an example of when the `figure` element would be useful in an HTML document.**
  * When you have many figures inside a doc you could give each on a sepecific `id` or create a `class` of images for ease of formatting in CSS
* **Describe the difference between a `gif` image and an `svg` image, pretend you are explaining to an elder in your community.**
  * `gif` can be use for animations while `svg` supports static images
  * `svg` contains all the code required to make the image and can be drawn to scale at any size
* **What image type would you use to display a screenshot on your website and why?**
  * For a screenshot, I'd use `PNG` because of lossless compression. This means that my text within my image will stay sharp, as opposed to becoming fuzzy as with a JPEG

### CSS

* **Describe the difference between foreground and background colors of an HTML element, pretend you are talking to someone with no technical knowledge.**
  * Foreground colors are the colors of the lines used to draw an element on the page
  * Background color is the color of the space that the lines of the element are drawn on
  * Think of foreground colors as the color of your pen and background colors as the color of your paper
* **Your friend asks you to give his colorless blog website a touch up. How would you use color to give his blog some character?**
  * I would start by understanding the colors associated with their website
    * What's the topic of the site?
    * Does that topic have associated colors?
    * Is there a mood the owner wants to project?
  * With that info, I could choose a base color and build accent colors around it
  * I would use brighter colors to attract the eyes of the reader towards anything that is important to the owner, especially monetization elements like pay buttons
  * I would use accent color to highlight any links contained in the text
  * I would also experiment with the color palette a bit to see which combination of colors is less stressful on the eyes
* **What should you consider when choosing fonts for an HTML document?**
  * dd
* **What do `font-size`, `font-weight`, and `font-style` do to HTML text elements?**
  * `font-size`: changes the size of the font
  * `font-weight`: changes how thick the font is
  * `font-style`: sets it normal, *italic*, or oblique
* **Describe two ways you could add spacing around the characters displayed in an `h1` element.**
  * `letter-spacing` could be increased to increase the space between individual letters
   `word-spacing` could be increased to increase the space between words in the header

## In Class Notes

### Code Review

* General Order in a JS File
  * Declare global variables
  * Declare functions
  * Executable code - the code that run
    * I.E. invoke the functions
* Specific notes for the Lab 2/3/4 code:
  * Invoke the functions in the .js file
    * Invoking the functions with `<script>` in html file is ok given what we've learned so far, but we will be adding `.eventListener` functions into our code to make it execute based on events in the browser
* *Helper Functions* can be added to the JS script to be invoked by other functions if they recycle code
  * Specific example from Lab:
    * For correct responses code block used in each question set is:

    ``` js
    // if correct >>
    alert(`Correct! ${responseAlert[i]}`);
    countCorrect = countCorrect + 1;

    //Those two lines could be placed into a single function like so:
    function correct() {
      alert(`Correct! ${responseAlert[i]}`);
      countCorrect = countCorrect + 1;
    }
    // This function could then be referenced by each branch of the 'correct' logic tree
    ```
