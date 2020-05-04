# Test Driven Development w/ Mocha and Chai

Checkbox for markdown: [x]

Behaviour Driven Dev:
  Does the app behave correctly, from the user perspective?

More to come: Component Driven, others.

All of them are about giving thought to code, **before** we write it.
We declare file names, function names, ideas of what we will be getting out of the file (data types, etc), and even have an idea of how the function will work. Preemptively considering what the sad paths are, what can go wrong. Maybe build a list of 'I've been bitten by, lets test for n. '




Keep that test code out of production code. 

API - Application Programming Interface.  Interacting with someone elses code. (Functions are a layor of abstraction that we can build on top of);

[Node](nodejs.org)

Conventions 
* Requires come in on top of the file so other devs know what's happening
* Exports usually are at the bottom of the code
  * Though you can also export the function anonymously
  * Exporting multiple functions, globals? Export as a function. 
    * When we Require them we then must call them as keys from the object. 
    * Can declare these as object keys either with function declaration, OR combined as an object declaration at the bottom. But, stay consistent.  
Wrapper functions - Node will wrap every module in a function including params around exports, require, __filename & __dirname.

  *Require* comes from a parameter to this wrapper function
    First, will look to Node for packages, then to node_modules, then throw errors if cant find.

  *Module* another part of the wrapper function
      module.exports === exports

      Exports is a function, holding the value of the function to be exported.



## Test files

In a seperate folder
Require the function to be tested into this test code.


In our own code we use relative pointer paths. 
Invoking modules by name. 

**Unit Tests** test the smallest, indivisible component of code. 

Pure functions will always return the same value from a given input. 

### Packages, Branding, Mocha

A note on branding: Javascript licenced the name Java from Oracle. 
Languages and tools succede or fail based on naming, marketing conventions, etc. 

When finding new libraries. LOOK AT THE DOCS. 

#### NPM - 
Manages all these packages (no name, but considered to be the 'Node PAckage Manager'). Ships with node. Others include yarn, etc.

Development Dependencies - Something our project relies on during development. 

Global installs are usually a bad idea - can build bad habits around getting versioning correct with a set-and-forget mindset of global install. 
  not including a --save-dev, or listing it as a dependecy in the project, is **mandatory** for teamwork. 

**NPM init** sets up these dependencies as part of the package.json

### Mocha

--save-dev is a Dev dependency. A dependecy for development ONLY - needed in test code, vs what our production code will need. 

We don't want to save our dependencies to our git. 
**.gitignore** 
  node_modules

Package lock files help us determine the exact versioning of each dependency. NEVER edit package lock directly. 

When not globally installed we have to find mocha in the node_modules. 

Mocha only gets mad if tests fail.

Set up the test script in package.json with the filepath. 

2 new functions : 
1. describe(); //descibe what you're testing - 'sayHello function tests', and a callback function. (vvvv the it's are called back)
2. it(); //This is a test - it ('string describing what it should do')
    'should return x when given x', () => {
      assert.goes.here
    });

Mocha cannot look inside your it functions. All it can do is look for errors thrown. Relies on an assertion to throw an error for it to check. Binary! If all code executes, pass! If something doesn't pass, test fail. Up to us to write good tests. 

### Chai

Brings in new assertions, beyond what comes with node. Node gives fairly simple assertions. 

Chai lets us juice that up to a few different paths. Should, Expect, and Assert phrasing (which let us re-langugage our syntax to help with things like Behaviour Driven Development). 

Chai gives us... so heckin many assertion tests. 


Sidenote ---- When making functions: Create container, fill container. (Make all your brackets first, dummy). 

Test the happy path, and test off the happy path. 