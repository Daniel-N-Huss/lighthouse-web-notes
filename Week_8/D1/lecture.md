# Unit and Integration Testing

Integration: Testing components with its child component.



## Tools for Testing React:

* Jest
  * Built-in to Create React App
  * Jest has its own assertion library built in, so no need to require Chai
  Jest is a framework for running tests, where an error thrown
* Testing Library
  * Helps us test the DOM - grabbing things by ID, or checking classes (we will be building on DOM Testing Library)
  * Great for universal DOM testing
  * Also has a wrapper, React Testing Library, that handles rendering and rerendering - React Specific Things
* Jest-dom
  * Custom dom-element matchers for Jest, more tools for pulling things out of the DOM, and assert against them.
* We wont use this, but create-react-app comes with User-Event (This is a end-to-end layer, we will use Cypress later on this week)


Flags for jest tests: 

(when running npm we need to indicate flags aren't for npm by doing an extra --)

--verbose
--coverage
  > Coverage reports don't work with watchAll enabled

* We can see a coverage report from the folder that is created, and in the browser we can see the report with some styling

Coverage is just a piece of the puzzle surrounding our code confidence. 
  100% coverage is pretty much impossible to acheive. Actual target will depend on the company, the team, and the project.



We're going to add 2 helper functions (with unit tests) to our example game
  * Function for how the robot will choose  
  * creating a status component depending on gamestate. 

Add 2 new features (with integration testing)
  * Toggle cheating state by clicking robot head
  * Update results with dynamic message


Try to emulate tests that already exist in the codebase.

We can wrap our tests in a 'Describe'  to compartmentalize everything. 

beforeEach lets us set up some state fresh before every test.

Jest convention is to start tests with test. 
  Follow the team convention at work. 


Wrap our test params in variables that are more descriptive than the values themselves. 

jest method for using array.includes: 
```js
expect(choices).toContain(result);
```

As always, write good tests. 


When testing components, we need to bring in react.
We can invoke a render function from the react testing library.

query tests will not fail out, get tests will. 

Pulling test methods off of a particular container gives it the context it needs, but if we bring in those tests globally we need to give the container to the method when its called. 

We don't need to have a virtual click, we can fire an event that matches what a click would be. Event is called .click, and the let it know what you want. 