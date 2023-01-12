# orpy.wiki
Python Wiki for ORIE majors @ Cornell

Everything you need to know about Python for ORIE at Cornell, including `pandas`, OR-Tools, GurobiPy, and more!

## TODO

 - [x] Find a good way to have syntax highlighting work in pure HTML (using pygments with default style incorporated into `style.css`)
 - [x] create a favicon that works
 - [x] make the sidebar into a hamburger menu on mobile (instead did something with css that made mobile usable)
 - [ ] Courses: finish courses besides ENGRI 1101 (me: 2700, 3120, 3150, 3300, 3310, 3500, 3510, 4330, 4350, 4390, 4580, 4630, 4741, 4820, 4990); remove all course links not present
 - [ ] Concepts: do all examples
 - [ ] Tools: finish tool pages (anaconda, colab, jupyter); write up general advice for events/ilps

## Editing this wiki

This wiki is written in pure HTML/CSS. That makes it harder to edit, but makes it infinitely more customizable and limits annoying complications with external packages (which would probably work with Markdown instead).

Code supplied to this wiki should be formatted using pygments. There is already css in the `style.css` file which corresponds to the default pygments theme, so all you need to do before pasting the code directly onto a page is run the following command (in a directory on your own system, and not in the repo itself!):

```
pygmentize -f html /path/to/file.py
```

This will print a HTML-highlighted version of `file.py` out in your terminal. If you'd prefer not to copy and paste from there you may want to instead run:

```
pygmentize -f html /path/to/file.py > out.html
```

This will create a new file `out.html` in the current directory which contains the HTML-highlighted output, which you can then copy and paste from. **Be careful** that you don't already have a file named `out.html` in your current directory, as this command will wipe it!


