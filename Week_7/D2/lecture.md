# Immutable Update Patterns


Some recap of create-react-app, and initial setup


Andy (and apparantly Hafiz), give specifically jsx files the .jsx filetype, more as a sign to other devs rather than out of necessity. 


As always, making things dynamic are the key.

React doesn't recognize variable reassingment, we specifically have to use state for React to update and know to change.


**State** : Data tjat lives in, and is specific to, a component. 


Props get passed as an object with key value pairs. 

We want smart parents who hold all of the state, and dumb children. The less state held in a child the more modular or reusable that component is. 


Calling multiple changes to state at the same time is hard.


We can create values that are passed in state by default, which we can access. Though that can create problems around using Event calls, because this happens async.


## Immutable Patterns

These are developer created and enforced patterns. 

Looking at pass by reference vs pass by value. Our creation of user objects example, that updating the reference updates the source. 

Spread Operators to the rescue!

Immutable - Don't mutate the original, make a copy and make changes to the copy. 

Spread the to-copy object first. 

Spread operators also make shallow copies only, meaning it doesn't recursively walk through the object and make a new copy of everything. If the value tied to a key is an array, or an object, THAT will get passed as a reference. 

We can nest our spread operators to bring that copy capability to the nested. 


When we just want to read data, we don't have to worry about enforcing this immutable patten with spread operators. IF we want to write over some that data, make sure we're creating 'copies'

### Why Immutability?
If we build this way:

* Data structures will be easier to plan, test, use
* Immutable data is side-effect free
  - We cannot change state inside our return values in react for a reason
* We will have a previous state to make comparisons to



## Doing Stuff With React

Controlled inputs require two-way binding. We need to be able to change and read the data, but the user also needs to be able to change the data.


Why does react want key props? 
  We need to be able to target specific dom elements when there are multiple child elements. 

Pushing directly to our 'toppings' is doing mutable stuff, so we need to use spread operators with setState functions.


What happens when we start setting a lot of state?
We can actually package a lot of state into a state object.

Setting state and the default state is our way to communicate with other devs about what is happening in the state. 

Start with initial values in that state object, even if it's just an empty initializer  -   { toppings: [] }

**Don't forget about async and capturing event values before moving into the callbacks for setting a new state**


Putting all of the state related to one thing should be packaged like our pizza state object containing state around crust, toppings, etc.


It's common to pull things like input fields out to their own components. 

Child components dont need to notify the parents about EVERY step along the way of changing state. Like, Pizza parent doesn't care about every keystroke. All we need to hand back up is the finished thought (on clicking the button, in this case)


Establish which components need to share state (either as state or as props), then set the state in the common ancestor of all the components that need it. 

Data goes down, actions come back up