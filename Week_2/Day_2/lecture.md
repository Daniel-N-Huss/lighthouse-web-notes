# Intro to Asynchronus Programming:

**Review**
  Callback Functions:

  function sampleFunction(x) {  // <-- can be hoisted
    console.log(x);
  }

  const sampleFunction = function (x) {
    console.log(x);
  }

  const sampleFunction = (x) => {
    console.log(x);
  }

  const sampleFunction = x => { // <-- if we only have one parameter we can drop braces
    console.log(x)
  }
  const sampleFunction = x => console.log(x)  //<-- one statement we can drop curly braces.


  const add = (a, b) => {
    return a + b
  }

  const add = (a, b) => a + b   // <-- return is implied


  [1,2,3].map(() => {   <--- inline callback

  })

Recall first-class / higher order functions.
  Either recieves a parameter, or returns a function. Returning functions isn't terribly common, but does happen on occasion.

    i.e. - calling a listener, and that calls a function that unlistens when you hear what you need

Callbacks can be used either Synchronously or Asynchronously. .map, .filter, are sync. Callback is just passing around usable functionality around. 
  But can also be a way to hand around a function asynchronously. 

## Benchmarks:

Synchronous programming - 1 thing at a time, in order.

Jan 1 1970 - now.getTime() : take a time before function, and after - subtract start from after and see how long it takes to run


## Asynchronous:

setTimeout(() => {
  // after the time passed, this callback will be called.
}, 3000)


Asynchronous behaviour will make Node stay alive until it has finished all the asyncs.


Javascript: Is a language. Can work in node, or in a browser.
Node: Runtime environment JS runs in. Node is kinda like a browser.

Javascript sets the rules through its language, but HOW that is implemented is up to the runtime environment. 

To run JS, Node parses the code to understand, store variables in mem, and execute. 

Synchronus JS - *singlethreaded*, one process at a time. 

Node does Asynchronus time called an **Event Que**. setTimeout() schedules a behaviour on the event que.

The restaurant analogy -- waiters take requests (via javascript / server), and the kitchen is the event loop and worker threads.


Helps us gracefully handle errors without crashing the whole setup. 

### Blocking / Non-Blocking <-Always Remember This Differentiation->:

  The while (true) infinite loop example - blocks the whole thread forever. (Sync code)

  Async code is non-blocking, multiple things can be working.


Interval() is non-blocking, so we can get things from the surrounding areas while the interval is still looping.

Inside interval, depending on what is happening outside (scope) -- if something changes outside it can be rough to manage, or data can be wrong.

Asynchs and loops are *weird*


## Higher Order Function:

How to extract values back to the main thread when they happen async? 

Beware Callback Hell (for when we use callbacks to handle async functions); 

## Working with the Filesystem

Wherever node is running is the relative space for where it accesses the files. Whether that's on our own pc, a server, etc. 


Reading from your system is an asynchronus event. 

const fs = require('fs');

Some methods:

data = fs.readFileSync // The synchronous file reading. 

__dirname is the current directory callable in node. 

fs.readFile --- the async version, with a callback given (err, data) ==> {

})

## User inputs and outputs

stdin = standard in abbrv
stdout

Encoding - types of characters to expect. 

Listener - a process that waits for something to happen, until you tell it to stop. 