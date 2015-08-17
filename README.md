# wallop
### Much more than just a slider

wallop is a minimal 4kb library for showing & hiding things.

>❗️️**Important note**️<br>
> Version 1 of *WallopSlider* is not compatible with version 2+.<br>
> If you are still v1, please note that I am no longer supporting it. Documentation, etc has been moved to [this branch](https://github.com/WallopSlider/Wallop.js/tree/v1).

## About
In a nutshell, wallop takes a collection of HTML elements and Pevious & Next buttons, and adds helper HTML classes in the correct elements based on whether you want to navigate forwards or backwards.

It basically just add the right classes in the right places at the right time.

With those classes, you can do an infite [number of things](#real-life-examples), controlling what's shown or hidden with CSS.

## Benefits
- Mobile first
- Progressive enhancement
- Transitions/Animations are all in CSS
- Minimal JavaScript
- Flexible & Scalable
- Custom events and API available
- 4KB minified
- Dependency free


## Install
With npm

```
npm install wallop
```

With bower

```
npm install wallop
```

With git

```
git clone git@github.com:WallopSlider/Wallop.js.git
```



## Usage
Once you have downloaded Wallop, the first thing you need to do is include the CSS and the JavaScript.

### CSS
```html
<head>
  <link rel="stylesheet" href="path/to/wallop.css">
</head>
```

### JavaScript
```html
<script src="path/to/Wallop.min.js"></script>
<script>
  var slider = document.querySelector('.Wallop');
  new Wallop(slider);
</script>
```

### HTML
```html
<div class="Wallop">
  <div class="Wallop-item">…</div>
  <div class="Wallop-item">…</div>
  <div class="Wallop-item">…</div>
  <div class="Wallop-item">…</div>
  <div class="Wallop-item">…</div>

  <button class="Wallop-buttonPrevious">Previous</button>
  <button class="Wallop-buttonNext">Next</button>
</div>
```

>**#protip**<br>
>You can set the starting slide with a `.Wallop-item--current` class.

## Adding animations
Wallop has no animations by default, so if you want to animate the slides, you need to extend the default `.Wallop` class with an animation modifier and include the respective CSS into your HTML.<br>

I have created a few basic animations which is ready for you to use out-of-the-box, you will find them in the `/css` directory.

### Including animation CSS
```html
<head>
  <link rel="stylesheet" href="path/to/wallop.css">
  <link rel="stylesheet" href="path/to/wallop-animation.css">
</head>
```

### Extending with modifier
```html
<div class="Wallop Wallop--slide">
...
</div>
```

### Available animations
Here's a list of the available animation modifiers ready for you to use
- `Wallop--slide`
- `Wallop--fade`
- `Wallop--scale`
- `Wallop--rotate`
- `Wallop--fold`
- `Wallop--vertical-slide`

## Options
Here's a list of options you can pass to Wallop
- `buttonPreviousClass: 'Wallop-buttonPrevious'`
- `buttonNextClass: 'Wallop-buttonNext'`
- `itemClass: 'Wallop-item'`
- `currentItemClass: 'Wallop-item--current'`
- `showPreviousClass: 'Wallop-item--show-previous'`
- `showNextClass: 'Wallop-item--show-next'`
- `hidePreviousClass: 'Wallop-item--hide-previous'`
- `hideNextClass: 'Wallop-item--hide-next'`
- `carousel: true`

## API
Wallop offers a basic API for you to use, so you can control it from your own buttons or gestures.

### goTo
This allows you to go to a specific slide index.
```js
var slider = document.querySelector('.Wallop');
var Wallop = new Wallop(slider);

// Go to 2nd slide
Wallop.goTo(1);
```
>**#protip**<br>
>index starts at 0 👌

### next
This allows you to go to the next slide
```js
var slider = document.querySelector('.Wallop');
var Wallop = new Wallop(slider);

// Go to next slide
Wallop.next();
```

### previous
This allows you to go to the previous slide
```js
var slider = document.querySelector('.Wallop');
var Wallop = new Wallop(slider);

// Go to previous slide
Wallop.previous();
```

## Events
Wallop dispatches a Custom Event everytime a slide changes, and it returns a `detail` object which contains the current slide index and the element you initiated Wallop with.

### Listening to a slide change
```js
var slider = document.querySelector('.Wallop');
var Wallop = new Wallop(slider);

Wallop.on('change', function(event) {
  // event.detail.wallopEl
  // => <div class="Wallop">…</div>

  // event.detail.currentItemIndex
  // => number
});
```

## Real life examples
- **[Google](http://www.google.com/trends/worldcup)** – uses wallop as a slideshow, transitioning the background colour and animating the hero image of each item
- **[Warp](http://warp.net/news/afx-following-global-premieres-you-can-now-hear-4-tracks-from-the-ep/?o=gallery&index=0)** – uses the power of wallop's API and Custom Events to control the items via the URL and to build a custom pagination
- **[London Housing Headlines](http://london-housing.uk)** – uses wallop to display a collection of really cool headlines about London's housing crisis 👍

## Limitiations
Wallop is a very simple library which basically just adds the right classes in the right places at the right time. Those classes allows you to use CSS to create animations.

Due to its simplicity, Wallop has a few limitations. For example, it is not possible to have the slide position animation based on gesture, or it's not possible to include physics based animations based on gesture momentum.

If you want a slider which provides all these options, I highly recommend David Desandro's [Flickity](http://flickity.metafizzy.co/).

## Contributing
Plese see [CONTRIBUTING](#).

## Licensing
MIT © 2015 [Pedro Duarte](http://pedroduarte.me)
