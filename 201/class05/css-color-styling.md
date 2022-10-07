# CSS: Color & Styling Text Elements

## Readings

* [Using Color in CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Applying_color)
* [Styling HTML Text Elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

## Notes

### Things that Have Color

* At the element level, everything in HTML can have color added to it
* There are *two* types of color:
  1. Foreground color `color`
  2. Background color `background-color`

#### Text

* `color`: the color of the lines making up the text, including any text decorations
* `background-color`: text background
* `text-shadow`: applies shadow effect
* `text-decoration-color`: changes default text decoration color to color specified
* `text-emphasis-color`: changes color of emphasis symbols
* `caret-color`: changes the color of the text cursor

#### Boxes

* `background-color`: color of elements without foreground content
* `column-rule-color`: color of lines separating columns
* `outline-color`: color used when drawing an outline around the outside of the element

#### Borders

* `border-color`: changes border color
  * Can apply `-top/-bottom/-left/-right` attributes as well to target specific lines
* `border-block-start-color` & `border-block-start-color`: changes the color of the border than the element starts with
  * For elements rendered left-to-right, will change the color of the left and right border, respectively

### Using Color Wisely

* Choose a **base color**
  * This will be the color that *defines* the site
  * Should have something to do with the topic of the site or your brand
* Selecting the Palette
  * Using online tools, you can get a range of colors that go well with your base color and accent it well
    * [MDN Color Picker](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool)
    * [Paletton](https://paletton.com/)
    * [Adobe Color Wheet](https://color.adobe.com/create/color-wheel)
  * Keep in mind, you will also need some neutral colors like white, black, and grey for the palette

## Fonts

### Font Shorthand

* Fonts can be shorthanded in the following order:
  1. `font-style`
  2. `font-variant`
  3. `font-weight`
  4. `font-stretch`
  5. `font-size`
  6. `line-height`
  7. `font-family`

  ``` css
  font: italic normal bold normal 3em/1.5 Helvetica, Arial, sans-serif;
  ```
