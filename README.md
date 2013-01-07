## CSS Prefixes for jQuery's or Zepto's .css() method

Overrides the $.fn.css method of jQuery or Zepto so that prefixes are added to properties and values where necessary.

### Examples

```javascript
// will use the correct property eg. transform, -webkit-transform, -moz-transform etc..
// will check that translate3d is supported, if it isn't then it will be converted to translate(0,0)
$('#element').css('transform', 'translate3d(0,0,0)');

// will use the correct value eg. box, -webkit-box, -moz-box etc..
$('#element').css('display', 'box');

// will use the correct property eg. transition-property, -webkit-transition-property, -moz-transition-property etc..
// will use the correct value eg. transform, -webkit-transform, -moz-transform
$('#element').css('transition-property', 'transform');
```

### Gradients
If setting background-image to a gradient using the W3C spec syntax then it will be coverted to a prefixed version if necessary. Vertical, horizontal, and radial gradient are supported using the following syntax.
```javascript
// for a vertical gradient
$('#element').css('background-image', 'linear-gradient(to bottom, #efefef 0%, #d3d3d3) 100%');

// for a horizontal gradient
$('#element').css('background-image', 'linear-gradient(to right, #efefef 0%, #d3d3d3) 100%');

// for a radial gradient
$('#element').css('background-image', 'radial-gradient(ellipse at center, #efefef 0%, #d3d3d3) 100%');
$('#element').css('background-image', 'radial-gradient(circle at center, #efefef 0%, #d3d3d3) 100%');
```

### $.css.getProp
This will just return the correct property to use in CSS style syntax. For example `$.css.getProp('transition')` may return `transition`, `-webkit-transition`, `-moz-transition` etc...
