**Housekeeping**

Rate of study increasing - more emphasis on self study on topics you want more info on. Expectation is shifting, less of the resources provided and now we're to do more of our own digging and learning. (But with mentor/instructor support)

# Styling - CSS

Writing maintainable CSS is hard. Ask for code reviews. We might be surprised at how little we actually need. 

**USE CHROME DEV TOOLS** - My new CSS BFF

` Google later - CSS Grid `


## Project this week Tweeter: 

Single Page App, focus on front-end: we're given a server api to work with. 

## HTML Review:

* Context around content - HTML gives us the structure

Semantic Tags :

    Look out for div soup - while we CAN do everything with the basic tags (because more complex ones are semantic only), using those semantics are sooooo important for: 

  * accessibility 
  * clarity 
  * developer readability 
  * SEO / Indexing (content heirarchy matters)

Examples of semantic tags, check out MDN for more:
section
summary



## CSS Defined:

Cascading Style Sheet:

* Top down
* Inheritance (nested styling adopts properties from parent)
* 

Default Styles, and inspecting them:

* User agent style sheet: the default styling around a page


**reset.css** 
 - and why (overcome defaults)

## CSS Syntax:

* Style attribute for inline styling
```html
<main style="property: value; another-property; another-value">
  some main content
</main>
  ```
  * Hard to reuse and maintain

* Selector + style block

```css
selector, selector2 {
  property: value,
  property2: value2
}
```

### Types of Selectors

**Ordering matters, the last read rule (in a list, with the same specificity) will be presented**


- Direct > Child selector: for all the tags directly related to the parent, do something. 

- General Descendent  (Not just direct descendents)

- General Sibling Selector: ~

- Direct Sibling Selector: +

- Class Selector (find a class=)

- Attribute Selector (find a type=)



id Selectors > Attribute Selectors > Class Selectors > Unit Selectors (Direct Child/General Descendent/Sibling Selectorss)


## Boxes:

Innermost layer of the box is content - surrounded by an html tag.

Next layer, padding

Above that, border

Above, Margin

We can style each of the 4 sides, (top, left, right, bottom), or all sides by not specifiying. 
Can also specify Top&Bottom/sides: 
```css
nav {
  padding: 100px 200px
} 

Can also specify Top/sides/Bottom: 
```css
nav {
  padding: 100px 200px 300px
} 

Can also specify each TRBL: 
```css
nav {
  padding: 100px 200px 300px 400px
} 
```

### 2 HTML divisions

* Block level:
  * Nothing can be places beside them (h1, div, p, would all stack because they each take the whole width)
  * most elements are block level, and there's a lot of them
* Inline:
  * Img, a, input, all just take up the size of their own content
  * Also have a lot, things like anchors, buttons, bolding, italicized, 
  * Box model changes for inline, cannot set top/bottom margins

**Nesting:**

Don't next block elements inside inline elements.

Block level can be nested in block level

Inline-block hybrid 


**Box Sizing**:

use box sizing property to make the padding/margin go WITHIN the width/height values. 


Maybe Google Float later? 

## Intro to Flexbox:

Parent boxes control how children boxes are laid out.

Margins colapse on each other (rather than stack)

Flex takes away display properties and controls them
Flex direction on parents goes by row but can be changed with  **flex-direction: column**, or reverse their layout.
Flex shrank the size to fit the content

**flex-wrap**
  Self explanitory

**flex-flow**
  Combo of direction and wrap

**justify-content**
  COOL STUFF HERE - centering, evenly distribute, space between, 
  Space around (no margin collapsing) 

  **Align-items** 


  But holy heck, please go look at more of these flexbox things. 


  # Building a page demo

  Emmet (vscode built in extension for html scaffolding) --> Google Emmet Cheat Sheet

  When styling, be consistent with specificity


Things to google:
  * 8-point Grid System
  * var() - CSS - MDN
  * 