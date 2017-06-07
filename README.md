# Floating Carousel jQuery plugin

Current version: 3.0

The Floating Carousel plugin creates a carousel which is clean and intuitive without the need for controls. The carousel is navigated by relative movement of the cursor (or the user's finger in the case of touch devices). Moving the cursor further to the left of the carousel element causes the content to scroll faster to the right and vice versa. The carousel can be implemented in a vertical alignment which works in the same fashion, but with up/down movements.

## Usage

To apply the carousel to a `UL` or `LI`, you need to wrap the list in a parent element to call the carousel on:

```html
<div id="carousel">
	<ul class="clearfix">
		<li>Carousel Item One</li>
		<li>Carousel Item Two</li>
		<li>Carousel Item Three</li>
	</ul>
</div>
<script type="text/javascript">
  $('#carousel').floatingCarousel();
</script>
```
...Or you can use `DIV` elements:

```html
<div id="carousel">
  <div>Carousel Item One</div>
  <div>Carousel Item Two</div>
  <div>Carousel Item Three</div>
</div>
<script type="text/javascript">
  $('#carousel').floatingCarousel();
</script>
```
See the demo file for more detailed examples of usage.

## Options

### autoScroll
Boolean - If set to 'true' the carousel will scroll automatically at set speed in a set direction when the mouse cursor is not over it.
Default : `false`

### autoScrollDirection
String telling the carousel which direction to scroll if `autoScroll` is on. Can be 'left' or 'right,' for the horizontal carousel, or 'up' or 'down' for the vertical carousel.
Default : `'left'/'down'`

### autoScrollSpeed
Integer representing the approximate time, in milliseconds, it takes for each pixel to scroll from one end of the carousel element to the other while the carousel is autoscrolling. A setting of 10000 (the default) means that one pixel will scroll from one end of the carousel element to the other in 10 seconds, thus the higher the number, the slower the speed. Obviously the speed will vary according to the width of the carousel element, so some experimentation may be required.

Default: `10000`

### looped
Boolean - If set to 'false' the content will stop scrolling when its edge reaches the edge of the container, otherwise it will loop infinitely.

Default: `true`

### scrollerAlignment
String - Set to 'vertical' to create a vertically aligned carousel, which scrolls up and down according to the vertical position of the mouse cursor over it.

Default: `'horizontal'`

### scrollerOffset
Integer representing the percentage the carousel content should be offset when the scroller first loads. A value of '0' will align the left-most element of the carousel content to the left of the container, a value of '100' will align the right-most element to the right.

Default: `0`

### scrollSpeed
String representing the relative speed at which the content will scroll when the user mouses over it. Can be 'slow', 'medium' or 'fast'.

Default: `'medium'`

### beforeCreateFunction
A function to call before the carousel is initiated.

Default: `NULL`

### afterCreateFunction
A function to call after the carousel has finished initiating.

Default: `NULL`

### enableTouchEvents
If set to `true` the carousel will respond to touch events, with similar behaviour to the way in which it responds to mouseover events.

Default: `true`

## Exposed functions

Use these by storing the carousel instance in an object:

```js
var myCarousel = $('#my-carousel-container').floatingCarousel();
		
$('#my-carousel-button').click(function() {
	myCarousel.Pause();
});
```

### destroy()
Removes the Floating Carousel functionality and returns the carousel element to its previous state.

### update(options)
Updates the carousel

Argument: `options` - The options to pass into the updated carousel instance

### pause()
Stops the carousel from scrolling until the `play()` function is activated (will also stop autoscrolling).

### play()
Re-enables the scrolling action on the carousel after the `pause()` function has been activated (also re-starts autoscrolling if it is set to `true`).
