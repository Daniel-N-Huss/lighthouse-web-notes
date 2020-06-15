# Responsive Design

A combination of approaches:

* Be elastic - Wikipedia
* Layout shifting - Compass

## View Port and Units

**This should be a default tag!** --> Allows for nice scaling, get comfortable using this. Without it, mobile sites have 
an awful side-scrolling thing

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```


### Units:

Absolute Values:
- Pixels
- Cm
- MM

Relative Units:

- vm:  1% viewport width
- vh:  1% of veiwport height
- rem: Font size of root element - depends on the ```<html>``` tag's font size
- em:  Font size of parent - always relative to parent size, can scale decently depending on the parent. Can be troublesome if we change a font size on an element, and that has a cascading effect downwards in the tree
- Others


We can set min width or height to restrict elastic shrinking, along with setting a max width or height to stop unwanted stretching. 


## Intro to Media Query 

Lets us selectively apply styling based on the devices viewport, or other specified criteria.

TONS of functions,
but also Logical operators 

and, or, not, only


Breakpoints for different styles. 

CSS Breakpoints guides exist all over google, but our content should be driving our breakpoints.

How does it look? When it looks wrong, then start adjusting


## SASS
Syntactically Awesome Style Sheet

CSS Preprocessor (google this), syntax that compiles down to CSS. 

Node Sass coming today.