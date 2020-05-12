# HTTP Servers


Review: 
* HTTP's have requests
  * Path - URL
  * Methods
    * GET / POST /
  * HTTP is Request / Response based cycle - it cannot respond without a request
  * The url + method === endpoint
* Responses have:
  * Status codes - 200/300/400/500
  * Body
  * Headers
* HTTP is stateless
  * The server responds to your request and then forgets about you.


## HTTP Server demo:

Get requests, responding with If else's at first;
Refactored to be a routing object.
Callbacks as part of this object table.

## Express Demo:

npm install 
app.listen


route handlers with app.get()

app.get('path', (request, response) =>{
  response.send('Hi from Express!);
});

We can refactor to have a seperate 'route handling' file. We can export an object of functions, that start point


ejs - library for page creation (Embedded JavaScript Templating) - this exists for alot of languages
  intialize ejs with app.set('view engine', 'ejs');

    ejs templates get built in a views folder.
    ejs mostly looks like html, but you can write JavaScript within it, with <% (alligator tag)
      calling the javascript logic comes with a <%= alligator tag, the '=' will display this on our page


response.render()

### express middlewares

app.use(request, response, next);
  request response make sense: **next** is the thing that 'passes the batton' that goes to the next function. Next hands exection to the next inline function. 

  app.get is also a middleware. But this is how we pass along information through our requests --> This is how we start keeping track of things like a logged in user, or other things. Carry over cart data? Timing how long a request takes with a Date.now(); 

  This is how we can manage and manipulate requests without responding and letting them disappear.

Store things, rather than pass along through next functions. 


# Recap:

The HTTP model and how to build applications. 
HTTP - request, response cycle.
Request object, with a url and method (called endpoints)

Response has a header and body

Creating server and opening it for listening on a port. (Binding a tcp port to a server)

Dynamic page templating --> using dynamic strings, or using libraries to do html/js in one place. 

app.get, give it a route and a function to call when the route is matched. 
Next functions can be used to call the next function in the chain (middlewares);

Storing users on a request object, and pass along with the next functions. 


Express gives us functionality --> Http servers do routing, rendering (handling requests), and listen on a port.
  Express gives us excellent routing capabilities without using some sort of routing object. 

Encapsulating route handlers in their own module.