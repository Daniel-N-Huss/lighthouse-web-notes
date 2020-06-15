# Tying it together, DB's and JS


We use a package to handle this.

Node-postgres


Connection string - anytime we connect to a resource, the thing we feed into the package in order to connect.


```js
client.connect();
```

When we ask for rows back from sql thorugh node postgres, we always get our data back wrapped in an array

## Security and SQL Injections

SQL injection is still the #1 hack that exists on the web. 

Piggybacking SQL Queries where they shouldn't be. Our example we passed a read and id#


We can use prepared statement syntax, which pass two seperate arguments. We can pass the query and then it looks to the next parameters to fill in the $ syntax.
Second param is an array holding our values to pass with the SQL query


Switch statement doesn't scope, so we need to set variables at the full switch scope and adjust them per switch trigger


## Web Delivery


As always, production code is modular


db.js --> JUST for establishing a database connection

Our queries will be wrapped in JS functions, with a function name that starts with a verb -->  getVillains



## Secrets

We don't want to share our database credentials.
We **NEVER** want to send those credentials onto Github, this is an EMERGENCY. 

IF YOU DO DELETE YOUR REPO, and change your DB passwords.

We can use a package to pass variables into our command line

**dotenv** loads a file (.env) that can hold our environment variable keys for accessing db. 
Those environment variables only load on runtime.

**.gitignore** our *.env* file
We name these variables in our .envs which we can then call inside db client JS file. 

### To share with other devs

We do push a .env example file to our repo that holds the environment variable KEYS, NOT THE VALUES, and the other devs have to fill those in themselves