# Ajax & jQuery


Ajax came from Microsoft. Outlook was a desktop client, and they wanted to mirror the 'always on' functionality with the web app. 

Established norms at the time meant the client had to make constant requests to the server checking for new emails. 

AJAX (Asynchronous Javascript and XML)

We're going to use async to make a request, without the user noticing, and update our page with XML data that gets returned.

XML (eXtensible Markup Language):
kinda like HTML, but has custom tags. 

XML is still a valid data transfer format, though JSON is more popular now. 


These requests for data are called:

**XMLHttpRequest (XHR) Object**

In practice you set an object, set up a listener, and then do something 



## Using AJAX

Build a listener for our form submission,
  prevent browser from submitting (override the default form behaviour)
  Then retrieve data from the form
  Then decide what to do with it (template, etc)



**jQuery serialize** -  


## Hacky

We were trusting data from the user.
We can protect from 'code injection' by not letting the browser interpret input as html, but as text instead. 
We need a sort of sanitizer function that stores the data in memory, within a container div, stored as a text string.

```js
document.createTextNode(string)
```

We can create nodes in different data types. createTextNode


## Refactor

When modularizing public code (client), we have to use:

```html 
<script src=""></script>
```
