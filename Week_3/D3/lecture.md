# Cookies and User Authentication!

**Cookies**: 
Helps to address the statelessness of HTTP servers with *session persistence*

Used for servers to recognize when they've seen clients before. 

Solving statelessness without cookies? 

* User requests 'my profile'
* Server couldn't find info about you- asks user to login & redirect to login page
* User submits login info
* Sever checks requet body and finds credentials submitted in database
* Now knows who you are, redirect to your profile page. 
* User goes to my/profile - server forgets who you are. Asks you to login. 

We can use clever redirects, including user information from query params - `my/profile/?user_id=2` to pass info along the route.
  Problems:
  - Security
  - Sharability
  - Navigating away from the website means we lose our query params
    Meaning we have to update all our views to recognize the params after autheniticated
    New tabs mean no more authentication
  
## Example: Language Switcher

Front page asks 'Do you prefer english or french?' 

Click on one option, it sets your preference and redirects you to the homepage, which renders the homepage in the correct language.

Redirect links to something like '/lang/en' or '/lang/fr' which set a cookie.
Can use if statements for proper redirects - watch out for sending multiple times if you only use if statement --> must use else or some sort of return to stop the routing from sending both responses.

Our solution has a problem - if a new user is sent a link, it will ask them the 'what language' question because they have no cookie, and then the request for the original page shared.

For things like language prefs, putting in the url can be very preferable. 


## Example 2: User Authentication:

OMG OUR TRESURE PAGE IS ACCESSIBLE BY EVERYONE 

`cookiemonster gif`

Currently our login is making get requests, instead of post requests.

For user auth:

1. Extract submitted credentials via req.body (need a body parser, either our own or a middleware)
2. First: Check if we know the username - second, check the password matches what is in our database.
  * if yes, set authentication cookie
  * Else if, password doesn't match (Error - Reset password, or enter again)
  * Else, some error (i.e. user not found, register instead)
3. On success, redirect somewhere (home in this case)


Digression --> Morgan as a tool (in express) for logging to console. When you make requests it automatically logs those requests to server console 

TemplateVars are stored as `locals`  --> `locals.username` or whatever you've passed in. Hafiz likes locals, but ejs can do it without that locals. tag
As long as this is an object it doesn't matter what you call it when you pass to templates. 


# Recap:

Cookies are ways to deal with HTTP statelessness, but not the ONLY way, nor right in every circumstance (like language preferences, or shareability issues)

Don't just check that a cookie exists for user auth. Gotta DOUBLE check that the user is real and exists in the database / that the cookie represents something real. 

Get 'Morgan' library for HTTP.

Cookies aren't secure. More like hiding things from the url, but still in plain text. 

Cookie parser and body parser, what they do. We could use custom code.

When you want to send a cookie it's singular!!! When you want to fetch a cookie, its plural!