Website Optimization 101
Notes taken on 11/17/2015


Steps:
1. Begin constructing DOM by parsing HTML
2. Request CSS & JS resources
3. Parse CSS and construct CSSOM tree
4. Execute JS (Ajax, won't be executed until CSSOM tree is constructed)
5. Merge DOM and CSSOM into the Render Tree
6. Run Layout, and Paint



1. Events break-down when loading a page (in timeline)

* Send Request:
	Send out a HTML document request to server

* Receive Response:
	Receive Data

* Finish Loading:
	Loaded the HTML docuemnt

* Parse HTML:
	Parse the HTML document to a DOM tree
	(send css/js docuemtn request within this step)

* Recalculate Style:
	After merge DOM and CSSOM into the Render Tree (decide what should be displayed and what to hide/remove from render tree)

* Layout:
	Compute the layout and size of render tree elements

* Paint:
	Page get rendered on the screen


For the browser to render the page, it needs a render tree, which requires both DOM and CSSOM (therefore, CSS files must be loaded and CSSOM tree must be built before painting the page


Render Blocking:

Only certain type of features are needed 



* At best, how many round trips does the browser and server need to make to render a page?
1 (1 request and 1 get response), BUT, this is true only if the HTML file is small (<=14 KB)
More round trips to render a data.


Browser can download both js and css at the same time. Therefore, download css and js combined is counted as one minimum critical path length.




##Critical Rendering Path:
3 important metric

1. number of critical resources (files)
2. total critical KB
3. minimum critical path length (round trips need)


* Preload Scanner
Load the JS in one go
http://andydavies.me/blog/2013/10/22/how-the-browser-pre-loader-makes-pages-load-faster/


https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model#css-object-model-cssom

Render blocking CSS
https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css
