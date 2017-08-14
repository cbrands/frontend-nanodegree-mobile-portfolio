# Website Performance Optimization portfolio project

## Getting started

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights!

# Part 1: Optimize PageSpeed Insights score for index.html
## Optimization steps
The original score on pagespeed was 28 for mobile and 30 for desktop.
* Added async attribute to google analytics javascript tag to unblock page rendering
* Added media print attribute to the link for print stylesheet.
* Created a thumb sized image for the pizzeria
* Compressed all images
* Loading google webfont asynchroneously helpt significantly.
* Minimized css using[cssminifier](https://cssminifier.com/) and placed the resulting css inline in index.html.
* After some testing I noticed that the speed gain came from the inline css and not from minifiyng css. So for readability I replaced the minified inline css with the full css but kept it inline

final score 93 for mobile and 94 for desktop


# Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

## Optimization steps
* Replaced querySelectorAll with getElementsByClassName
* Replaced querySelector's with getElementById
* Placed the calculation of newWidth outside of the loop
* placed every call to the dom outside loops
* Calculated the number of pizzas to loop over. 
* Using the requestAnimationFrame method to get the animation in a single reflow paint cycle
* As the styling limits the pizzeria image to a with of 720 I replaced that image with a version of that with