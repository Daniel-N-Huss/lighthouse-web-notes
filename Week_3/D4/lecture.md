# Security, Real World HTTP Servers


Security - we're not security experts, but we will use lots of tools to mitigate the security problems

Process is the running Node app. 'Process' is just node. 
  env is a special object around the environment. 
  When we deploy we will start looking to the server to tell us what port to use

We can pass css styles through our ejs head. 

Google Fonts ;)

## Lets Talk Security:

**NEVER EVER STORE PLAIN TEXT PASSWORDS**
  Bad dog.

Encryption - how to encode something

Hash / Hashing - no reverse, can never reveal the original password. 

We're using hasing for passwords, and encryption for cookies. 


## RESTful

We've not been purposeful about our endpoints.

There's an ideology around how to construct routes.

REpresentational State Transfer:
  Should serve up in a way the underlying data structures exist.


  We have some resource in memory - tweets, videos, etc. 
  We need a way to perform our BREAD's on all of those resources.

REST says 

Browse  GET   /resource           (eg. GET /users) 
Read    GET   /resource/:id       (eg. GET /users/2, GET /posts/15)
Edit    POST  /resource/:id   
Add     POST  /resource
Delete  POST  /resource/:id/delete


In a more complicated example - Posts that all have comments

Browse    GET   /posts/:id/comments
Read      GET   /posts/:id/comments/:comment_id

etc etc


### Extending to other HTTP verbs
  These are really just semantic wrappers (that do fancy stuff)

PUT       - Replace the underlying resource (Like an edit)
PATCH     - Update the resource in place
DELETE    - Delete the resource


Browse    GET       /resource
Read      GET       /resource/:id
Edit      PATCH     /resource/:id
Add       POST      /resource
Delete    DELETE    /resource/:id   <!--We don't need to specify in the route -->



### Query Params
HTML is limited to GET and POST
Method-Override is a package that lets us use verbs

Query param - ?_method=Delete

POST /resource/:id?_method=DELETE
  transforms this to
DELETE /resource/:id

Can tackle this as stretch for today.


### Custom middleware for checking user auth / credentials
  Yesssss

All middleware has access to the request and response objects that get passed in our HTML

params --> (req, res, next) => {
  //do stuff
  next();
})


## Express alternatives:

* hapi
  - Some similar api setup to Express
* Restify
  - Almost exactly the same as Express
* Koa

These all have to be able to process verbs and paths, and respond with status codes. But, the way we interact with them can be the same. REST applies to ALL of these webservers, and they all will expose the verbs in some way.