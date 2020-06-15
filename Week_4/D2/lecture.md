# Client Side JS & jQuery


JS is the same, mostly. We have no access to node from client side. 

Instead, we have

## The Window:

The entire tab, everything that's happening in the tap. 
  values such as users window size, (one of the most popular things for us to do)
  Location
  host names, etc.

  We can do javascript through the console, and mess with a lot of things. This replaces our Process access. 

## Navigator: 

The Browser the client is using. 
So much access can happen here. 

```navigator``` has SO many accessibilities, and this is our API to them.

Value to users comes from comparing data to data (your location, and the location of your Skip driver)


## console.dir();

Interactive list of the properties of an object like with our document (the webpage itself)

Lead into the DOM


# The DOM:
Another API

A tree data structure that turns your HTML into an object.

When the DOM is fully loaded we get an event called "Document Loaded" (on.documentloaded?)

HTML no longer exists in the browser once it's loaded, now it's the DOM. 


`document` is our api

We can write queries for the DOM:

```javascript
document.get

document.getElementById('main-list');
```

We can retrieve DOM nodes! Store them in variables, in memory, and interact with them. 

If we want to add stuff, we can!

We want to create new elements, which we can store in variable. 
Then we can create text nodes, and append the text node to our new element,
then we can append a child to a parent in the DOM. 

**This is all called Client-Side rendering**


`Clients have access to all our CSS, HTML, JS. Security-minded: we keep secrets on the server side, never store credentials or important info on client-side & be wary of what you share`


## Events: 

Things like our 
```js
app.get('/login', (req, res) => {});
```
^ Event

EventListeners let us take over with code when something happens, and respond with a callback function. Gets passed an event object

When listening, we get specifics around what the event is / does.

EVERYTHING in the browser is an event, so we have *crazy* amounts of control around what we can see. 

We can also programattically click on stuff, or take control of stuff (testing? user experience?)

## Bringing in Javascript:
Script tags! We can do inline scripting with JS, but we modularize them and bring the min.
```html
<script src="script.js">
```

src is the path to our file. 


Watch for temporal issues - did the item get created in the DOM before the script ran?

# JQuery:

CDN - Content Delivery Network
  - A webserver that exists to serve up static files (like jQuery)

  Integrity = hashing, to make sure the contents of the file match what the user downloaded.

Bring jQuery in before other stuff.

jQuery === $
```js
//invoking 
jQuery() 
//or 
$()
```

Grabbing elements in jQuery
```js
$('#mail-list')

```

Prepend jQuery variables with a '$';

add event listener jQuery:
```js
$h1.on('click', (event) => {
  console.log(event);
})
```

Calling when the doc is ready with 
```js
$(document).ready()
```

Suggestion: Keep using both - move scripts to bottom of the function, and also use the document.ready to do **Defensive Coding** - making sure you've done all you can do to make things to work. 

Creating with jQuery, use angle brackets 
```js
$('<li>').text(value)
```
When manipulating the dom there *must* be an anchor point


ORDER:

1. Grab button
2. Attach listener to button, and fire callback on event
3. Get the value back from the form
4. Create a new DOM node with the value
5. Grab existing node
6. Append new node


