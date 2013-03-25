# Code School's jQuery courses

## Course #1: jQuery Flight
* you usually add key handlers (e.g. keydown, keyup, keypress) on the whole document (and not on a specific HTML element), like so:

```
$(document).ready(function() {
  // Handler for .ready() called.
});
```

which is equivalent to:
```
$(function() {
 // Handler for .ready() called.
});
```

You can also use the delegate method:

```
$("#tabs div").delegate("#flights a", "click", selectFlight);
```

* CSS selector ">" means "directly under"


## Course #2: Captain's log
* `jQuery()` ensures it's namespaced
* use `live()` to hook handlers which are not yet present on the page (e.g. which will come with Ajax)
* `bind()`
* `$(element).css({'background-color': '#2C1F11', 'opacity':'0.5'}).animate({ height: '30', opacity: '1'});`
* `fadeIn()`
* `fadeOut()`
* `slideUp()`
* `slideDown()`
* `$(element).stop()` to stop any animation 

```
$(element).queue(function(next){
  // animation 1
  // animation 2
  next();
})
```

```
$(element).slideSown(function(){
  // this happens after the slide down
});
```

if you want to trigger an event on an object, you must first bind the event handler to that object:
```
$('#flight-navigation a').click(function(event) {
  event.preventDefault();
  $(this).trigger('flightChanged');
});

$('#flight-navigation a').bind('flightChanged', function() {
  $(this).toggleClass('on');
});
```
