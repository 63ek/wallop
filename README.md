# Wallop Slider

Wallop Slider is a minimal 3kb zero dependency slider.

> **Important note**<br> 
> Version 1 of Wallop Slider is not compatible with version 2+.<br>
> If you are still v1, please note that I am no longer supporting it. Documentation, etc has been moved to [this branch](https://github.com/WallopSlider/WallopSlider.js/tree/v1).


## Benefits
- Mobile first
- Progressive enhancement
- Transitions/Animations are all in CSS
- Minimal JavaScript
- Flexible & Scalable
- Custom events and API available
- 3KB minified
- Dependency free


## Install
With npm

```
npm install wallop-slider
```

With bower

```
npm install wallop-slider
```

With git

```
git clone git@github.com:WallopSlider/WallopSlider.js.git
```



## Usage
Once you have downloaded Wallop Slider, the first thing you need to do is include the CSS and the JavaScript.

### CSS
```html 
<head>
  <link rel="stylesheet" href="path/to/wallop-slider.css">
</head>
```

### JavaScript
```html
<script src="path/to/WallopSlider.js"></script>
<script>
  var slider = document.querySelector('.WallopSlider');
  new WallopSlider(slider);
</script>
```

### HTML
```html
<div class="WallopSlider">
  <ul class="WallopSlider-list">
    <li class="WallopSlider-item WallopSlider-item--current"><img src="imgs/1.jpg"></li>
    <li class="WallopSlider-item"><img src="imgs/2.jpg"></li>
    <li class="WallopSlider-item"><img src="imgs/3.jpg"></li>
    <li class="WallopSlider-item"><img src="imgs/4.jpg"></li>
    <li class="WallopSlider-item"><img src="imgs/5.jpg"></li>
  </ul>
  <button class="WallopSlider-btn WallopSlider-btn--previous" disabled="disabled">Previous</button>
  <button class="WallopSlider-btn WallopSlider-btn--next">Next</button>
</div>
</div>
```

## Adding animations
Wallop Sider has no animations by default, so if you want to animate the slides, you need to extend the default `.WallopSlider` class with an animation modifier and include the respective CSS into your HTML.<br>

I have created a few basic animations which is ready for you to use out-of-the-box, you will find them in the `/css` directory.

### Including animation CSS
```html
<head>
  <link rel="stylesheet" href="path/to/wallop-slider.css">
  <link rel="stylesheet" href="path/to/wallop-slider-animation.css">
</head>
```

### Extending with modifier
```html
<div class="WallopSlider WallopSlider--slide">
...
</div>
```

### Available animations
Here's a list of the available animation modifiers ready for you to use
- `WallopSlider--slide`
- `WallopSlider--fade`
- `WallopSlider--scale`
- `WallopSlider--rotate`
- `WallopSlider--fold`
- `WallopSlider--vertical-slide`

## Options
Here's a list of options you can pass to Wallop Slider
- `btnPreviousClass: 'WallopSlider-btn--previous'`
- `btnNextClass: 'WallopSlider-btn--next'`
- `itemClass: 'WallopSlider-item'`
- `currentItemClass: 'WallopSlider-item--current'`
- `showPreviousClass: 'WallopSlider-item--show-previous'`
- `showNextClass: 'WallopSlider-item--show-next'`
- `hidePreviousClass: 'WallopSlider-item--hide-previous'`
- `hideNextClass: 'WallopSlider-item--hide-next'`
- `carousel: false`

## API
Wallop Slider offers a basic API for you to use, so you can control it from your own buttons or gestures.

### goTo
This allows you to go to a specific slide index
```js
var slider = document.querySelector('.WallopSlider');
var WallopSlider = new WallopSlider(slider);

// Go to 2nd slide
WallopSlider.goTo(2);
```

### next
This allows you to go to the next slide
```js
var slider = document.querySelector('.WallopSlider');
var WallopSlider = new WallopSlider(slider);

// Go to next slide
WallopSlider.next();
```

### previous
This allows you to go to the previous slide
```js
var slider = document.querySelector('.WallopSlider');
var WallopSlider = new WallopSlider(slider);

// Go to previous slide
WallopSlider.previous();
```
