# Reading Notes

## Basic Writing & Formatting Syntax in Markdown
[GitHub Docs: Basic Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[Markdown Guide: Extended Syntax](https://www.markdownguide.org/extended-syntax/#:~:text=for%20more%20information.-,Tables,either%20end%20of%20the%20row.)

### [What is Markdown?](https://www.markdownguide.org/getting-started/)

Markdown is a lightweight markup language that can be used to add formatting elements to plaintext documents. Unlike a text editior that instantly displays the styling added to text, in Markdown you will only see the syntax of the style while editing. You can utilize the "Preview" feature to view the stylistic changes made to text elements to see how their formatting has changed.

### Why use Markdown?

- It can be used to create websites, documents, notes, books, presentations, email messages, and techinical documentation.
- It is portable; it can be opened by using virtually any application.
- It is platform independent.
- It is future proof; even if applications stop working, you will be able to utilize a text editor to read your Markdown file.
- It is everywhere! GitHub, Reddbit, etc. all support Markdown.


### Headings

Headings are generated using 1-6 `#` symbols at the beginning of the line.
The number of `#` use determines the size: 1 = Largest; 6 = Smallest

`# Largest Heading`
`## Second Largest`
`###### Smallest Heading`

# Largest Heading
## Second Largest
###### Smallest Heading

If you generate two or more headings, GitHub autogenerates a Table of Contents, accessable by clicking the 3-bulleted list icon.

### Styling Text

You can emphasis words using **bold**, *italics*, ~~strikethrough~~, <sub>subscripts</sub>, <sup>superscripts</sup>, & **bold __and__ italtics.**

| Style | Syntax | Keyboard Shortcut | Example | Output |
| ---   | ---    | ---               | ---     | ---    |
| Bold  | `** **` or `__ __` | `Ctrl` + `B` | `**Bold Text**` | **Bold Text** |
| Italic | `* *` or `_ _` | `Ctrl` + `I` | `*Italics*` | *Italics* |
|Strikethrough | `~~ ~~` | | `~~Mistake~~` | ~~Mistake~~ |
| Bold & Nested Italic | `** **` & `_ _` | | `**This is _extrememly_ important**` | **This is _extremely_ important** |
| All Bold & Italic | `*** ***` | | `***All of this is important***` | ***All of this is important*** |
| Subscript | `<sub> </sub>` | | `<sub>Subscript</sub>` | <sub>Subscript</sub> |
| Superscript | `<sup> </sup>` | | `<sup>Superscript</sup>` | <sup>Superscript</sup> |
| Code | `` ` ` `` | | `` `git status` `` | `git status` |
| Ignore Content | `<!-- Ignore This -->` | | *N/A* | Content will not display |
| Links | ` [Display](URL) ` | | `[GitHub Pages](https://pages.github.com/)` | [GitHub Pages](https://pages.github.com/) |
| Images | `![Image](URL)` | | `![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)` | ![This is an image](https://myoctocat.com/assets/images/base-octocat.svg) |
| Footnotes | `Text[^#]` | | `Reference[^1]` | Reference[^1].
[^1]: My Reference |
