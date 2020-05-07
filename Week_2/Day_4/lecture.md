Recap:

Callbacks --> Sync, Async

# Promises 

**A brief intro**

Order food --> get receipt with order number --> wait for your food that is promised to come --> exchange recipt for food, contract complete. 

  Now, you might not get everything you want - your original promise is rejected.

Promises are Javascript Objects

3  States of promise. 

1. Pending - initial state: an observation of a future state
2. Resolved - the future state is real -- to resolve we have to wait, then figure out what to do with the resolved state.     JS - '.then' is the method.
3. Rejected - the future state is not real - bad things happen, not the expected result.

**Promises are JS objects** that are used to handle async flow. Avoid that callback hell. 

Promises help us get to a ladder state of code, rather than a waterfall. 
  Consider the profile project. 

  Hafiz solution uses readline-promise. Many libraries recreated their functionality around promises when they were released. 

  Promise-chains with .then
  .then() <-- this is passed the resolved value returned from the last promise in the chain. 

  Do chains always function in order? - not really. You can define your promises ahead of time, then call them


returning a function is..wild.

.then has *two* callbacks. One for the resolved promise, and one for the rejected promise. 

## Handling promise errors: 

Handle errors by branch

Catch block at the end to catch them all --- POKEMON


## Parallel promises:

### Promise.all()
Can ask for multiple promises:
p1
p2
p3

we can use a NEW promise with Promise.all (giving it an array of the promise variables, making it wait for ALL the promises to finish) .then(callback) 

Parallel is faster than promise chaining. 

One caveat - if one promise fails, everything fails in the Promise.all

We can catch an error at the end of promise.all.

Pass an array to promise all. Object no good because it needs to be iterable. 

This is a wrapper promise. One promise.

### Promise.race()

Similar idea to .all(), but will only return the first fulfilled promise. 

## Using promises
new promises takes two things, a function

1. A function
  * the 'what to do when things resolve properly'
2. Another function
  * the 'what to do when things are rejected' function


const futureIsBright = new Promise((resolve, reject) => {
  resolve('all good');
  reject('No bueno!')
});

  new establishes a class, don't worry about classes for now

futureIsBright.then(resolvedValue => {

})

futureisBright.catch(rejectedValue => {

});