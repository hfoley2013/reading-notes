# Class 11: Reading Notes & Assignment Summary

## Assignments

### Video and Audio Content

* **Explain how the ability to use video and audio on the web has evolved since the early 2000s.**
  * Old plug-in technologies like *Flash* and *Silverlight* have given way to native HTML solutions for embedding content and JavaScript APIs for controlling them
* **Describe the use of the src and controls attributes in the `<video>` element.**
  * `src` links to the source file for the audio/video content
  * `controls` presents the user with the basics controls need to start and stop the content
* **Why is it important to have fallback content inside the `<video>` element?**
  * Different browser types support different file types and your format might be unsupported
  * In this case, your fallback content would display to the user
  * The fallback content could contain a link to another version of the file that the user could follow, or provide a set of instructions for downloading an audio/video player that supports the file format
* **Write a very short story where `<audio>` and `<video>` are characters.**
  * Audio hated video because of his vivid display. But beyond `width`, `height`, and a `poster` attribute, what difference was there really?

### A Complete Guide to Grid

* **How does Grid layout differ from Flex?**
  * Grid is a 2D layout, while Flex is a 1D layout
  * Meaning, whereas you can only manipulate elements horizontally *or* vertically with `flex`, you can manipulate elements both horizontally *and* vertically with `grid`
* **Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences.**
  * **Grid Container**
    * The element on which the display is applied
    * It is the *direct parent* of **all** grid items
  * **Grid Item**
    * The *children* elements of the container
  * **Grid Line**
    * The dividing lines that make up the structure of the grid

### Responsive Images

* **Besides making a site visually appealing across different screen sizes, why should developers make images responsive?**
  * Having the appropriately sized image called to display on your site will reduce the bandwidth required to load the page
  * Speeding up load times provides for a better UX, therefore the use of responsive images should be considered for these performance reasons
* **Define the following `<img>` attributes `srcset` and `sizes`. Write an example of how they are used.**
  * `<img>` tells the browser that the file is an image file
  * `srcset` defines the set of images for the browser to choose between and what the size of each image is
    * Each image is separated by a `,`
  * `sizes` defines a set of screen widths (*media conditions*)
* **How is `srcset` more helpful for responsive images than CSS or JavaScript?**
  * Using CSS or JS to detect the screen width then adjust images wouldn't make sense due to the order of parsing by the browser
  * Since the HTML is parsed first by the browser, then CSS, then JavaScript, images will begin to download as soon as the webpage is opened
  * By the time the CSS or JS began working, the original image would have already downloaded
  * You would then have to download the appropriate image and switch out that image for the original image
  * This would slow load times and likely create the effect of the image "jumping" around on the webpage
