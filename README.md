

####Part 1: Optimize PageSpeed Insights score for index.html

* To run the site open the file index.html. Some animations use JavaScript so make sure JavaScript is enabled in your browser.

####Optimizing techniques used:
* inlined all CSS
* removed the call to style.css so it would not load for the index page
* optimized pizzeria.jpg
* added async to js files
* changed print call to media query

####Part 2: Optimize Frames per Second in pizza.html

* Reduced number of mover elements created from 200 to 25.
* Added the backface-visibility: hidden CSS attribute to force them into seperate composite layers. This meant that the browser wasn't required to paint the whole page each time the element moved.
* Subtracted half the window width from the basicLeft variable for use in the updatePositions function.
* Replaced querySelectorAll with getElementsByClassName which is considerably faster.
* Removed from the for loop the calculation to find scrollTop divided by 1250, and an array of values for use in the phase calculation.
* Stored the variable items.length outisde of the loop
* Replaced CSS style 'left' which triggers layout, paint and composite, with transform, which only triggers composite.
* Used requestAnimationFrame to run the updatePositions function at a steady rate.
* Added a running variable to ensure requestAnimationFrame did not run after scrolling was completed.
* Instead of calculating the size difference when resizing, I used the switch statement to return a percentage based on the size value.
* Said percentage was then used in the changePizzaSizes function as the width attribute of the pizza containers.
* Replaced querySelectorAll with getElementsByClassName which is considerably faster.