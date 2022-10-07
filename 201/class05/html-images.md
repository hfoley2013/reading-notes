# HTML Media

## Readings

* [HTML Media](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding)
* [Using Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
* [Common Image Types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
* [Choosing Image Formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#choosing_an_image_format)

## Notes

### Basic Syntax

* `<img src="source.jpg" alt="description">`
  * NOTE: Can use a URL as `src` as well
* `alt` attribute
  * **Alternative Text** to display when the image doesn't load in the browser
    * Alt text is useful for:
      * SEO
      * Visually impaired using screen readers
      * User has turned off images to reduce data transfer volume and distractions
* `title` attribute
  * Shows information to the user `on.hover`
    * Also useful in SEO

``` html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth"
  width="400"
  height="341"
  title="A T-Rex on display in the Manchester University Museum" />
```

### `<figure>` Tag

* Semantic container for charts, images, or other figures used on a site
* `<figcaption>` can also be used to generate a caption similar to `title` attributes

### Image File Types and Formatting

| **Abbreviation** |	**File format** |	**MIME type** |	**File extension(s)** |	**Summary** |
| --- | --- | --- | --- | --- |
| APNG |	Animated Portable Network Graphics	| image/apng	| .apng	| Good choice for lossless animation sequences (GIF is less performant). AVIF and WebP have better performance but less broad browser support Supported: Chrome, Edge, Firefox, Opera, Safari. |
| AVIF	| AV1 Image File Format |	image/avif	| .avif	| Good choice for both images and animated images due to high performance and royalty free image format. It offers much better compression than PNG or JPEG with support for higher color depths, animated frames, transparency, etc. Note that when using AVIF, you should include fallbacks to formats with better browser support (i.e. using the `<picture>` element).Supported: Chrome, Opera, Firefox (still images only: animated images not implemented). |
| GIF |	Graphics Interchange Format	| image/gif	| .gif | Good choice for simple images and animations. Prefer PNG for lossless and indexed still images, and consider WebP, AVIF or APNG for animation sequences.Supported: Chrome, Edge, Firefox, IE, Opera, Safari. |
| JPEG	| Joint Photographic Expert Group image	| image/jpeg	| .jpg, .jpeg, .jfif, .pjpeg, .pjp	| Good choice for lossy compression of still images (currently the most popular). Prefer PNG when more precise reproduction of the image is required, or WebP/AVIF if both better reproduction and higher compression are required. Support: Chrome, Edge, Firefox, IE, Opera, Safari. |
| PNG	| Portable Network Graphics	| image/png	| .png	|PNG is preferred over JPEG for more precise reproduction of source images, or when transparency is needed. WebP/AVIF provide even better compression and reproduction, but browser support is more limited.Support: Chrome, Edge, Firefox, IE, Opera, Safari. |
| SVG	| Scalable Vector Graphics	| image/svg+xml	.svg	| Vector image format; ideal for user interface elements, icons, diagrams, etc., that must be drawn accurately at different sizes.Support: Chrome, Edge, Firefox, IE, Opera, Safari. |
| WebP | Web Picture format | image/webp	| .webp	| Excellent choice for both images and animated images. WebP offers much better compression than PNG or JPEG with support for higher color depths, animated frames, transparency etc. AVIF offers slightly better compression, but is not quite as well-supported in browsers and does not support progressive rendering. Support: Chrome, Edge, Firefox, Opera, Safari |

### Choosing File Types

| **Type of Image** | **File Type** | **Why** |
| --- | --- | --- |
| Photographs | JPEC or WebP | Photos do well will lossy compression. These formats maximize quality and minimize download time |
| Icons | SVG, Lossless WebP, or PNG | Because of small image size, lossless compression is better. SVG in particular scales well across various resolutions and sizes (perfect for responsive deign) |
| Screenshots | Lossless WebP or PNG | Text in your screenshot could be fuzzy if the file format is of a lossy type |
