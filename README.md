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
* Loading google webfont asynchroneously helpt significantly. Pagespeed still saw it as a performance hog so finally google webfont was eliminated altogether.
* Minimized css using[cssminifier](https://cssminifier.com/) and placed the resulting css inline in index.html.

final score 93 for mobile and 94 for desktop


# Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

## Optimization steps
* Replaced querySelectorAll with getElementsByClassName
* Placed the calculation of newWidth outside of the loop
* Calculated the number of pizzas to loop over 200 was way to much 
