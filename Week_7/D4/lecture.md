# Custom Hooks

* Lets you extract logic into reusable functions
* Custom hooks are just JS functions that uses hooks

> Reminder of the Rules of Hooks:

* Hooks must be top-level, not nested in things like if statements
* Must be within a react component
* Hooks start with 'use'
* Different calls to a hook do not share state. Still have to prop-drill

## Some Code Examples 

### Title.jsx

Setting the title of the document, easy peasy - though directly accessing it via document.title is a side effect. 

All hooks are part of React, so we need to import react whenever we use it.


We can choose to pass params or return from our hooks.


Wraping state updates into act() function.

Layer your hooks, use one inside another to create cool combos.


