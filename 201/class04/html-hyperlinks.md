# HTML Hyperlinks

## Reading

* [HTML Creating Hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)

## Notes


### Basic Syntax

* Created with `<a>` tags

``` html
<a href="https://www.url.com">The Link Text</a>
```

* Additional information can be included in a `title` attribute
  * This info gives the user useful info on what the link does and helps in SEO

```html
<a href="link.com" title="The best place to find links">Link Text</a>
```

### Linking Specific Parts of HTML Document

* You can link to a specific part of an HTML document by adding `#id_name` to the end of the document's path in the `<a>` tag

```html
<h2 id="Mailing_address">Mailing address</h2>

<p>
  Want to write us a letter? Use our
  <a href="contacts.html#Mailing_address">mailing address</a>.
</p>
```

### Link Best Practices

* Use a short, descriptive link name
* Do not use the URL in the link name
* Make links standout on the page for ease of locating
* Use `title` attributes to give the user useful info `on.hover` and help with SEO

### Email Links

* Created using `mailto: emailaddress@host.com`
* Can also add `cc`, `bcc`, `subject` and `body` info into the link as well

```html
<a
  href="mailto:rainierracingco@gmail.com?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  Send mail with cc, bcc, subject and body
</a>
```
