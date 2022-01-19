# gulp-webp-avif-html - fork gulp-webp-html-nosvg

> Gulp extension, replace html element `<img>` to `<picture>` with [`gulp-webp-avif-html`](https://github.com/TiroZit/gulp-webp-avif-html/)

## Install

```
$ npm i --save-dev gulp-webp-avif-html
```


## Usage

Use this into your `gulpfile.js`:

```js
const gulp = require('gulp')
const webpAvifHTML = require("gulp-webp-avif-html")

function html() {
    return src('source/*.html')
        .pipe(webpAvifHTML())
        .pipe(gulp.dest('dist/'))
}

exports.html = html;
```

## Example

```html
// Input
<img src="img/image.jpg" alt="image">
```
```html
// Output
<picture>
    <source srcset="img/image.avif" type="image/avif">
    <source srcset="img/image.webp" type="image/webp">
    <img src="img/image.jpg" alt="image">
</picture>
```

**Support file extensions:**  `.png, .jpg, .jpeg`

### The picture element
For now, you can still use the format in its almost complete glory with the native `<picture>` element in HTML. Why, you may ask? Well, the `<picture>` element allows progressive support. You can simply drop all image files in the order in which you want to load them. Your visitors' browsers load only one image at a time, which reduces the load on the server. Besides, you don't need a script to process multiple images.
Currently **96.5% of browsers support the** [`picture element`](https://caniuse.com/?search=picture)

✔ *Does not download more than one image at a time*

✔ *Native support for selecting the most appropriate image*

✔ *96% browser support and automatic fallback*

✔ *Getting this implemented is easy and straightforward*


<img src="https://raw.githubusercontent.com/powerrampage/Test-Avif/main/avif-result.png" alt="result" />
