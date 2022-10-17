# Video and Audio Content in HTML

## Reading

* [Video and Audio Content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)

## Notes

### Video Syntax

```html
<video src="video.mp4" controls>
  <p>Fallback Content<p>
</video>
```

* `src` is the same source attribute as images and links to the location of the video file
* `controls` is an attribute and gives the user the ability to control the playback of the file
* **Fallback Content** is displayed between the `<video>` tags and shows if the video isn't supported by the browser
  * You can embed `<a>` tags here to link to another site to show the appropriate video

### Video File Formats & Browser Compatibility

* Browsers support different video and audio file types
* To account for this, you can embed multiple `<source>` tags between your `<video>` tags in order of preference

```html
<video control>
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <p>Fallback Content<p>
</video>
```

### Video Features

* `width` & `height`
  * The **aspect ratio**
  * If the aspect ratio is not maintained by the sizes you set, the video will grow to fill the space horizontally, and the unfilled space will just be given a solid background color by default.
* `autoplay`
* `loop`
* `poster`
  * URL of an image that will display before the video runs
  * Made as a splash page or advert page
* `muted`
* `preload`
  * `none` = does not buffer the file
  * `auto` = buffers the media file
  * `metadata` = buffers only the metadata for the file

### Audio Files

* Use the same syntax and attributes as video, **EXCEPT** for the following:
  * `width` & `height`
  * `poster`

### Creating Subtitles

* Use **vtt** file format paired with `<track>` tag

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <track kind="subtitles" src="subtitles_es.vtt" srclang="es" label="Spanish" />
</video>
```

* `kind` options
  * Subtitles
  * Captions
  * Descriptions
* `srclang` identifies the source language being displayed
  * The use of this attribute helps users find the language that they need
