# Express Day 2:

Building a website from scratch, and considering what we need:


## Coffee App:

  - Buy coffee
  - Shop for coffee
  - Shopping cart
  - Order history

How does our thing extend later on? Keeping in mind the growth pattern, so we don't have to redesign 


### Data:

- Storage for coffee
- Give things different ids as a way to always have a unique identifier.
  Relying on name only to differentiate isn't a good practice.
- In our example, our data structure is a regular object.

One way we might be encouraged to store our data is in an object, and set the key of the object to be the id.

We're bringing in an array for this example. 
  Method for using arrays - ```Array.find(coffee => coffee.id === desiredID)```- this is a way we can scan through for unique id's
  Wrap this in a function.
  This function allows us to not need to know the data structure, or HOW the function is working, we can make changes to the function without breaking the code. 


Checking you work via different pathways to see it works.  

Creating functions to change the data can bo good for control, or stopping users from changing data they shouldn't have access too.

Instead of a specific updater function, create a function that takes in 3 params, coffee id - the value to change - the value.

Writing new functions? Start with how to hardcode it as JS.

Using filter as the heart of a delete coffee function. IF id is NOT the id passed, you stay in the array.


### BREAD 

  Browse - Read - Edit - Add - Delete

    Kinda like CRUD: Create - Read - Update - Delete

Browse speaks to the way we route a bit - show me one index : it's a read with a tighter scope. 

BREAD is a list of actions, BREAD is a verb. 


## Resources:

Resources are the nouns of our apps.
  - **Coffee**
  - Users
  - Orders
  - Shopping Cart
  - Dashboard
  - Recommendations

### REST
(REST) -> REpresentational State Transfer
  
  **Better definition** 
  A routing plan fo doing BREAD stuff to resources.

Wraping a server around BREAD functions. (Building an express server around the core functions, via route handlers, and then representing them in EJS (or other tools)).

## Routes

Routes are a combo of the path and the HTTP method:

*URL* --> coffeeapp.com/coffees/3/edit
*Path* --> /coffees/3/edit

Routes: 
```
GET /coffes/3/edit
POST /coffees/3/edit
```

GET --> No server state changes (usually: clients aren't asking for a change, but we might update a view count or something internally)

POST --> Please change the state of the server (and it's data)

This is convention, so we CAN do other things, but we shouldnt. 


### Restful routing

Browse - GET `/coffees`
Read - GET `/coffees/:id`
Edit - POST `/coffees/:id`
Add - POST `/coffees`
Delete - POST `/coffees/:id/delete`  <-- we're adding this in to differentiate it from the Edit request. We can just add on things to help our own routing -->

HTTP methods are just.. strings . So you COULD make it up, but your extra software (like express) probably wont know what to do with it. 



## Object destructuring: 

const { name, origin } = coffee 

--> Now coffee contains these variables
Can also help us remember what data we're working with, without flipping over to where that data is located. 


# BREAD Servers:

**Data access --> Render Plan --> Routes that make it work**

Watch your data types - when dealing with HTML most everything is a string, but if you're relying on numbers that can wreak havoc on your routing & value grabbing. 

## HTML Elements:

### Forms
This is how we make post requests. 
Form provides data to server about what change we want. 
Delete is a post request, so we can implement that. 

Properties of form:
* Action
* Method

Forms describe where the request is supposed to go - Form is the bundle.

  Buttons get wrapped in here. Button type defaults to submit. 

### Input
  Reading inputs from user. 

 **You can make get requests with inputs for routing!**


### Label

Toss a note beside your input- `for=` ties it to the id of whatever you put here


## Express
Places data can be hiding in a few spots

req.params --> come in response headers
req.body --> built into POST requests, or things that ask for changes to server
req.query

Express doesn't have the default ability to parse body - Express.urlEncoded( { extended: true });

We had the case of being concerned about passing in an undefined - we can handle this in our helper functions by just returning if nothing is passed.

By keeping our data removed via the functions people can't just hack our page and add in buttons and try to change the other data because we didn't set up a route to get that sorted. 