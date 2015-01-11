![Papier Logo](https://cdnjs.cloudflare.com/ajax/libs/ionicons/1.5.2/png/512/paper-airplane.png)

# Papier -> [Demo](http://gugel.io/papier/)

> a minimal, pretty semantic, responsive CSS library

## Design Decisions

* **Responsiveness** Everything is responsive: alerts, panels, grids - everything!
* **Lightweight**: ~ 2.5kb minified and gzipped last time I checked
* **Intrusiveness**: While other frameworks force you to be very explicit about the intended styling of your elements by adding lots of classes (`<button class="btn">Click</button>`), Papier is very semantic and simply styles e.g. all buttons as Papier-buttons (no need to add additional classes, `<button>Click</button>` works just fine). This is especially handy for rapid prototyping.
* [**normalize.css**](http://necolas.github.io/normalize.css/) makes browsers render all elements more consistently and in line with modern standards. It's the foundation of papier.
* **Readability over semantic**: Papier sacrifices readability and expressiveness over semantic. In Bootstrap you would create a blue button by adding the `btn-primary` and `btn` classes. Papier takes a different approach: Instead of expecting you to know that every primary button is blue, it allows you to simply add a background to it, by adding the `bg-blue` class. While this is obviously less semantic, it is much easier to understand, since who knows that `btn-primary` means "make this button blue".
* **Prototyping**: Papier is perfect for rapid prototyping. This is also an area where it sacrifices readability over everything else. This means you have access to a ton of utility classes that aren't necessarily very semantic, but very handy and expressive - in short, perfect for hackathons.
* Smart defaults: When setting the background of an element via `.bg-red`, the color of links and text within it will automatically set to `#fff`.
* **No custom styles for checkboxes, radio-buttons etc.** - Users have a certain expectation how a radio button or checkbox needs to look like. Applying custom styles would ruin the assumption. Further, it's nearly impossible to make them look good on all browsers.
* Maximum possible browser support: Everything above **IE7** should work fine - nice CSS3 animations excluded.
* CSS preprocessor: Stylus - CSS still looks like CSS, but should also be mostly valid in SCSS and Less

## Utility classes

### Material design-like depth classes
```css
.depth-0
.depth-1
.depth-2
.depth-3
.depth-4
.depth-5
```

### Rounded corners
```css
.round-1
.round-2
.round-3
.round-4
.round-5
.round-10
.round
```

### Selectively setting margin and padding (responsive)
```css
.inner-seamless
.outer-seamless

.s-padding
.m-padding
.l-padding

.s-margin
.m-margin
.l-margin
```

### Setting text-align
```css
.left
.center
.right
```

### They do exactly what you expect them to do
```css
.subtle
.full-width
.uppercase
.inline-block
.hidden
.window-height
```

### Vertically centering elements
For some reason ~~2014~~ 2015 and vertically centering elements is still a pain.
```css
.vertical-center-container
.vertical-center
```

```html
<div class="full-height vertical-center-container">
    <div class="vertical-center">
        BOOM
    </div>
</div>
```

### Background colors
```css
.bg-no
.bg-subtle
.bg-white
.bg-red
.bg-pink
.bg-purple
.bg-deep-purple
.bg-indigo
.bg-blue
.bg-light-blue
.bg-cyan
.bg-teal
.bg-green
.bg-light-green
.bg-lime
.bg-yellow
.bg-amber
.bg-orange
.bg-deep-orange
.bg-brown
.bg-grey
.bg-blue-grey
.bg-black
.bg-almost-black
```

When applying a background color (e.g. `.bg-brown`) to an element, the color of links and other text within it will automatically be set to `#fff` to maintain the contrast.

If you prefer a more semantic approach, the utility classes are still useful, since you can use them in order to extend your own custom classes if needed.

### Example

```stylus
@require 'util.styl';

.danger {
  @extend .bg-red;
}
```

## Getting started

* npm: `npm i papier --save`
* bower: `bower i papier --save`
* CDN (preferred): `<link rel="stylesheet" href="https://cdn.rawgit.com/alexanderGugel/papier/master/dist/papier-1.0.0.min.css">` or `<link rel="stylesheet" href="https://cdn.rawgit.com/alexanderGugel/papier/master/dist/papier.min.css">` for the latest version

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Papier CSS</title>

<!-- FONT -->
<link rel="stylesheet" href="http://fonts.googleapis.com/css?family=Source+Sans+Pro:400,600">

<!-- ICONS -->
<link rel="stylesheet" href="http://code.ionicframework.com/ionicons/2.0.0/css/ionicons.min.css">

<!-- MAGIC -->
<link rel="stylesheet" href="{{PATH TO PAPIER}}/dist/papier.min.css">

</head>
<body class="bg-subtle">

<button class="bg-indigo"><i class="icon ion-ios-cart"></i> Icon button</button>

<div class="row">
<div class="col-2 bg-lime"><strong>col-2</strong><br> bg-lime</div>
<div class="col-3 bg-yellow"><strong>col-3</strong><br> bg-yellow</div>
<div class="col-4 bg-amber"><strong>col-4</strong><br> bg-amber</div>
<div class="col-3 bg-orange"><strong>col-3</strong><br> bg-orange</div>
</div>
</body>
</html>
```

## Customizing

Papier is built with Stylus. Customizing it is therefore very easy:

* Install Stylus: `npm i stylus -g`
* Create your stylesheet using [stylus](http://learnboost.github.io/stylus/):

`styles.styl`

```css
@require 'node_modules/papier/src/panel.styl';

.my-panel {
  @extend .panel;
}

.introduction {
  @extend .my-panel;
  width: 500px;
}
```

**Important** Make sure to to `require` instead of `import` to avoid duplicate classes in the compiled CSS.

You can also customize colors and other variables by overriding `config.styl`. E.g. Papier features a 12-column grid layout by default, but you can also set the `$columns` variable to 36 or whatever you prefer.

## Help, Bugs, Issues

File an issue if you find a bug or have a question. Feel free to send PRs! I'm also hanging out on Freenode all the time ([alexandergugel](http://webchat.freenode.net/)). You can also find me on Twitter: [@alexanderGugel](https://twitter.com/alexanderGugel).

The easiest way to support this project is to **star** it. Thanks.

### Credits

* intrusiveness inspired by [Picninc CSS](http://picnicss.com/)
* grid inspired by [Pure CSS](http://purecss.io/) and [Bootstrap](http://getbootstrap.com/)
