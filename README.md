JS-Virtual-Pointer
==================

Emulate a human's mouse-movements using this JavaScript-based virtual pointer; the correct events will be executed in JavaScript, as if a real human was interacting on the page in a desktop browser

Usage
==================

virtualpointer.move_mouse_to_element(element, length_of_mouse_movement);

virtualpointer.click_element(element);

virtualpointer.move_to_element_and_click(element, length_of_mouse_movement);

virtualpointer.run_serialized_events(array_of_events);

array_of_events must be a serialized JSON array of events, with the following properties for each event:
- type: type of event (e.g. mousemove, mousedown, etc.)
- pageX: pageX value for the mouse event
- pageY: pageY value for the mouse event
- screenX: screenX value for the mouse event
- screenY: screenY value for the mouse event
- timestamp: timestamp of event; this will be used to calculate the time between one event and the next, so no need for the timestamps to start from zero
- element: DOM element on which to fire mouse event (this is optional; if the element is not specified, event will be fired on document.body instead)

Example
==================
open up example.html and open up the JavaScript console in your web-browser; you should have a log of events that have been fired programmatically.... you can then run any of the commands above


Dependencies
==================
None; uses native JavaScript

Potential Issues
==================
You can't run this inside a headless browser that depends on the jsdom.js library, such as Zombie.js, because jsdom.js doesn't have any notion of page layout (or dimensions of elements on the page) and does not implement getBoundingClientRect, etc.

