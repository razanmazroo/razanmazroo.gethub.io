# Udacity FEND Project 4: Website Optimization

## Summary:

This project required improving the performance of loading and rendering an existing portfolio site. The speed of the site was measured using Chrome dev tools to identify performance bottlenecks, and then optimizations were applied to address those bottlenecks and janks.

## Steps to launch:

1. Clone the repo to your local machine **razanmazroo.github.io**
2. Launch a local http server to test. A simple way to do this on a Unix based OS is to open a terminal window, navigate to the directory of the project, and run a python command: python -m SimpleHTTPServer 8080
3. In the same directory, run the command: ./ngrok http 8080 to access a secure public URL to the site.
4. Copy the public URL given by nrok from the terminal window and paste it into your browser to view the site.
5. To test index.html, open the website from https://razanmazroo.github.io/, then use Google PageSpeed Insights to check the Google PageSeed score of it.
6. to test Pizza.html, Capture a timeline session while scrolling down the page to check the framerate of this page.

### Optimizations of index.html
1. Inline CSS
2. Adding media **print** to print.css
3. Profile image encoding
4. Image compression and minification
5. Using **Async** with java script files and adding them to the end of html file
6. Comments were not added in order to increase the performance of the page

### Optimizations of views/js/main.js for pizza.html

1. Modfied the changePizzaSizes function to select randomPizzaContainer elements by class name (rather than querySelectorAll) and add them to a pizzaElements array.
2. Delete the function determineDx. It is not necessary to call it, since we will change the pizza size inside the changePizzaSizes function.
3. Use of getElementByClassName instead of querySelectorAll as it is more efficient.
3. Modified the updatePositions function to select the mover elements by class name.
4. The document.body.scrollTop is a constant number, so we don't want to create the varible each time inside the for loop, we move it outside
5. phase will only print 5 different numbers. So we create an array where we put the 5 numbers (0, 1, 2, 3, 4)  we also put the phase variable outside the  loop
6. In order to calculate the exact number of pizzas, we first calculate the screen height,  then  divide it by s, to know the number of rows, and then round it to an integer. Finally multiply the rows bt cols. And in the for loop, we loop only for numberPizza times.


### Optimizations of views/css/style.css

1. Adding **backface-visibility: hidden;** to the .mover class, to move each animated pizza to its own composite layer.

## Resources referenced:

* [Udacity office hours for P4: ](https://github.com/udacity/fend-office-hours/tree/master/Web%20Optimization/Effective%20Optimizations%20for%2060%20FPS)
* [Google PageSpeed Insights rules:](https://developers.google.com/speed/docs/insights/rules) 
* [Udacity forums for P4:](https://discussions.udacity.com/c/nd001-2015-05-06/project-4)
* [Optimizing Google Web Fonts blog post:](www.hongkiat.com/blog/optimize-google-webfonts/)
* [MDN docs on getElementsByClassName:](https://developer.mozilla.org/en)US/docb/API/Document/getElementsByClassName)