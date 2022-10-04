# HTML Text Fundamentals

## Reading

* [HTML Text Fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#the_basics_headings_and_paragraphs)

### Headings & Paragraphs

* Paragraphs are designated by the `<p>` element
* Headings are designated by the `<h1>-<h6>` elements
  * There are 6 levels of headings

### Lists

* Unordered lists are designated by the `<ul>` element
* Ordered lists are designated by the `<ol>` element
* Lists can be nested inside of each other

### Emphasis & Importance

* Emphasis can be placed on a word using `<em>`
  * This will *italicize* the word
* Strong emphasis can be placed using `<strong>`
  * This will **bold** the word
* `<i>` tags can be used to convey meaning traditionally conveyed by *italics*, such as foreign words, taxonomic designation, technical terms, etc.

``` html
<!-- scientific names -->
<p>
  The Ruby-throated Hummingbird (<i>Archilochus colubris</i>) is the most common
  hummingbird in Eastern North America.
</p>

<!-- foreign words -->
<p>
  The menu was a sea of exotic words like <i lang="uk-latn">vatrushka</i>,
  <i lang="id">nasi goreng</i> and <i lang="fr">soupe à l'oignon</i>.
</p>

<!-- a known misspelling -->
<p>Someday I'll learn how to <u class="spelling-error">spel</u> better.</p>

<!-- term being defined when used in a definition -->
<dl>
  <dt>Semantic HTML</dt>
  <dd>
    Use the elements based on their <b>semantic</b> meaning, not their
    appearance.
  </dd>
</dl>
```

* `<b>` is used to convey meaning traditionally conveyed by **bold**, such as keywords, product names, lead sentence, etc.
* `<u>` is used to convey a meaning traditionally conveyed by <u>underline</u>, such as proper name, misspelling, etc.
