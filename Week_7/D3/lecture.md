# Data Fetching and Other Side Effects

> Review of importing / exporting

## Rules for Hooks:

* Don't call Hooks in a Javascript statement:
  - Not in a condition, a for-loop, 
* Can only call hooks in React component (Or within other hooks)
* Hooks name start with 'use', this is how React can interpret and utilize them


# Pure Functions and Side Effects

* A function is pure if it produces the same output given the same input
  - I.e. addition, 
* Functions with side effects are not pure
  ```js
    let y = 0;
    const addWithSideEffect = (a, b) => {
      y = y + a + b;
      return y;
    }
  ```
    - This example shows how we have some side effects because of the global scope of y.


Any time you don't control everything in your function there are side effects. 

Giving the function everything it needs to operate makes it pure. 

Pure = we have control over it within this scope. 
Unpure / Side effect = we don't control everything. 


### Common Side-Effects:

* Console.log
* Math.random()
* setTimeout()
* Making api requests
* fs, reading files
* trying to directly access the DOM within React (React becomes the gatekeeper to the DOM, if we directly access it then its a side effect)


### Handling Side Effects in React

Hooks! 

- useEffect, a named React export

```js
  useEffect(() => {
    //side effect code goes here  
  })
```
When we use the useEffect hook, we return a function that happens on the next refresh.

useEffects is how we undo side effects with 4 configurations:

1. When you want it to run every time, 
  > Without dependency array:  
  ```js 
    useEffect(() => {})
  ```
2. When you give it a dependecy array, it will run every time the dependency changes:
  > With dependency array
  ```js 
    useEffect(() => {}, [dependency1, dependency2])
  ```
3. With an empty dependency array, it will only run once:
> empty dep array
  ```js 
    useEffect(() => {}, [])
  ```
4. Returning a cleanup function that is called before the next effect is set up, when we want something to happen after the effect.
  ```js
    useEffect(() => {
      return function cleanup()
    })
  ```
  > Particularly useful to clean up effects that might cause memory leaks, like setInterval

## API effects

React needs an external library to make api requests.

**Axios** is a popular library for React, and this purpose.

We have to set some state to capture the api data when it returns