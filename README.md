"orientationchange" Event Polyfill
==================================

This polyfill allows you to use "window.orientation" and to bind to the "orientationchange" event.  It has
no dependencies on any libraries, but has support for using jQuery to bind to the "orientationchange" event.

Because IE8 does not allow you to use attachEvent / fireEvent for custom events, you have to set the
window.onorientationchange function:

	function handler() {
		if(window.orientation == 0 || window.orientation == 180) {
			// Do something useful in portrait mode
		} else {
			// Do something useful in landscape mode
		}
	}

	if(window.addEventListener) {
 		window.addEventListener("orientationchange", handler, false);
 	} else {
 		window.onorientationchange = handler;
	}

If you use jQuery:

	$(window).on('orientationchange', function() {
		if(window.orientation == 0 || window.orientation == 180) {
			// Do something useful in portrait mode
		} else {
			// Do something useful in landscape mode
		}
	});

