# Responsive Images

## Reading

* [Responsive Images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

## Notes

### Why Responsive Images?

* Responsive images allow you to display the appropriate image based on screen size at the appropriate resolution
* Solves the **art direction problem** and the **resolution switching problem**
  * Art Direction Problem
    * Serving different cropped images for various layouts based on screen size
  * Resolution Switching Problem
    * Switching between images of higher and lower resolutions to save bandwidth and display an appropriate image to the user

### Resolution Switching: Different Sizes

```html
<img
  srcset="elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w"
  sizes="(max-width: 600px) 480px,
         800px"
  src="elva-fairy-800w.jpg"
  alt="Elva dressed as a fairy" />
```

* Order of Operations:
  * Look at its device width.
  * Work out which media condition in the sizes list is the first one to be true.
  * Look at the slot size given to that media query.
  * Load the image referenced in the `srcset` list that has the same size as the slot or, if there isn't one, the first image that is bigger than the chosen slot size.

### Resolution Switching: Same Size, Different Resolutions

* Similar to different sizes, but adds **x-descriptors** and removes the `sizes` attribute

```html
<img
  srcset="elva-fairy-320w.jpg, elva-fairy-480w.jpg 1.5x, elva-fairy-640w.jpg 2x"
  src="elva-fairy-640w.jpg"
  alt="Elva dressed as a fairy" />
```

### Art Direction

* Direction of art can be changed with the use of the `<picture>` tag

```html
<picture>
  <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg" />
  <source media="(min-width: 800px)" srcset="elva-800w.jpg" />
  <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva" />
</picture>
```
