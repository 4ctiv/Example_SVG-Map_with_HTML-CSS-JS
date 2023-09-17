# Example for "Interactive SVG-Map" using HTML, CSS, JS (Vanilla)
> The following will desrivbe how to interactively communicate and transfere data using SVG maps and html + CSS + JS
> using only a few external libraries.
>
> In Contrast to other tiutorials this also shows how to transfere data between the SVG and website as the
> internal js code from the svg does not interact with the website's js natively.  

### SVG Structure
> Inside the ```<g></g>``` all SVG structures e.g. rectangles (`<rect id="", onclick="", onmouseover="", onmouseout=""></rect>`) are defined
> - Note: `onclick="", onmouseover="", onmouseout=""` should have functions from the internal js code between the quotes
> - Note2: `id` parameter is by default the SVG element id, 'evt' is by default the SVG elent invoked event
> Internal JS code of the SVG is defined inside the `<script type="text/ecmascript"> JS CODE HERE </script>`
> - The defined code does only work within the SVG and cann not directly interact with the embedding website itself
>   - The root for the internal js code is the `<svg></svg>` NOT the embedding website's root 
> External JS code can be imporeted relative to the procject root using `<script xlink:href="PATH_TO_JS/NAME.js" />`
> - Note: To embed external code, `xmlns:xlink="http://www.w3.org/1999/xlink"` is required inside the `<svg ADD_HERE>`

### Website Structure (HTML/CSS/JS)
#### HTML
> It is recommended to import the SVG as an object, but some browsers do not support this, alternatives for `object` are
> in comments below (in the index.html example: `embed` & `img` tags)
#### CSS

#### JS
##### Hand down data from HTML 
> Modify Dummy variables (e.g. hidden text) inside of the SVG itself
> - Inside Website JS: `document.getElementByID('svg-example').getElementByID('DUMMY_NAME').innerHTML = "DATA";`
> - Inside SVG JS: ``data = document.getElementByID('DUMMY_NAME').innerHTML;``

##### Push data from SVG
> Website JS gets data from (dummy) variables inside the SVG by simply using
> - Inside SVG JS: `document.getElementByID('DUMMY_NAME').innerHTML = "DATA";`
> - Inside Website JS: `let data = document.getElementByID('svg-example').getElementByID('DUMMY_NAME').innerHTML;`
