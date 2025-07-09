# ORPY wiki
Python Wiki for ORIE majors @ Cornell

Everything you need to know about Python for ORIE at Cornell, including `pandas`, OR-Tools, GurobiPy, and more!

## TODO

 - [x] Find a good way to include Jupyter Notebooks in HTML (built a better version of `nbconvert`, see below)
 - [x] Create a good favicon 
 - [x] Make website look better/be usable on mobile
 - [x] Courses: finish all courses listed (more can still be added via pull requests!)
 - [ ] Tools: write up general advice for events/ilps
 - [ ] Concepts: do all examples

## Editing this wiki

This wiki is written in pure HTML/CSS. That makes it harder to edit, but makes it infinitely more customizable and limits annoying complications with external packages.

In general, to make another page, just copy a preexisting page, rename it, and edit that. This removes any work w.r.t. formatting stuff like the sidebar and header.

### Code examples

Code examples on this wiki are supplied with Jupyter Notebook files (`.ipynb` files). 

The workflow for creating a code example is as follows.

If creating a new page:

1. Copy another page in the same directory to serve as the starting template
2. Rename that file to a reasonable abbreviation that does not conflict with anything else in the directory
3. Edit that file to remove the unneeded content

If the page template from which you're starting **does not already have the KaTeX CSS and JS blurb in the header, make sure you add it:

```html
  <!-- KaTeX JS and CSS -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.11.1/katex.min.js"></script>
  <script>document.addEventListener("DOMContentLoaded", function () {
   var mathElements = document.getElementsByClassName("math");
   var macros = [];
   for (var i = 0; i < mathElements.length; i++) {
    var texText = mathElements[i].firstChild;
    if (mathElements[i].tagName == "SPAN") {
     katex.render(texText.data, mathElements[i], {
      displayMode: mathElements[i].classList.contains('display'),
      throwOnError: false,
      macros: macros,
      fleqn: false
     });
  }}});
  </script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.11.1/katex.min.css" />
```
 
Then:

1. Create a new Jupyter Notebook in that directory, with the same name as the HTML file. For example, if the HTML file for the new wiki page is has the filename `filename.html`, the Jupyter Notebook file should have the filename `filename.ipynb`.
   - Alternatively, if the example is already in the form of a Jupyter Notebook, simply copy the notebook file into the directory and rename it so that it follows the above naming scheme
2. Write up the example in that notebook file
3. **Run the `nbconv.py` script linked here:** [nbconv.py script gist](https://gist.github.com/benrosenberg/66b02e9842b6082101d97e5cec344e05) 
   - When running the script, choose a value for `out_filename` that **does not conflict** with other files in the directory, as they will be overwritten if there is a name conflict. A surefire choice is `out.html`
   - Make sure the `standalone` parameter is off; that is, **do not** include a `-s` or `--standalone` flag when running (e.g.) `python nbconv.py filename.ipynb out.html`
4. Copy the contents of the script output file into the wiki page, where the other content was deleted. (For examples of correctly formatted wiki pages, click the "Edit this page on GitHub" link in the footer of any page with a code example on it.)
5. Delete the script output file


