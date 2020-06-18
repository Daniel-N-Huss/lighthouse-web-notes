# Class Based Components

Recall constructing classes and substantiating new versions of a class,
classes can hold methods and data (rectangle example, that also includes a method for calculating its own area)

Inherit from other classes --> 
```js 
class Square extends Rectangle {
  constructor(size) {
    super()
  }
}
```

Classes have a sort of internal state. Unlike functional programming where we need to declare the functions (which dump everything from memory when they wrap up)


Functional React Components have unlimited states. 

Class-based React Components must bundle state into one object.

We set our state within the constructor.
To access it in our render we call this.state...
Usually we destructure it in our render part of the class-component. 

When we create things in the scope of a function we will be creating that function in memory every time we render the button.
If we create it as a method outside of the render part of our component we avoid this crummy behaviour. 


2018 Introduced Class Methods, which bind methods via an arrow function as part of the class methods declaration.


### Lifecycle Methods:
Things we inherit from extending a React class component.

Lifecycle is the life of a component, from when it is rendered and mounted, through to when it is unmounted. 

* Constructor
* Render
* componentDidMount
  * The first run
* componentDidUpdate
  * When rerenders happen - won't call when FIRST rendered, but will call on subsequent rerenders. 
* componentWillUnmount
  * Cleanup tasks here