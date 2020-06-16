# React in the Real World

This lecture is for our information, in case we want to use React in our finals. 

### Routing:

Single page apps and routing? Transitions.

* Conditional Rendering - show part of the ui based on conditions. 
  * useVisualMode hook played this role

The way we've routed with Scheduler isn't how we really do this in the real world of production development. 

React-Router is a tool we can use for React routing. 

#### React Router: 

```js
import { BrowserRouter as Router, Link, Route, Switch } from "react-router-dom"
```

Router will wrap everything that needs to be routed to. 
We will use the Link method from react router, 


>Get Emmet and learn that scaffolding!

Now we wrap our different views in a Route tag
```js
<Route path="/routeHere"></Route>
```

We can pass an exact tag to make sure we only head to the EXACT match for our url.
But instead of doing individual exact tags we can bring in the Switch from the react routing library


```js
<Switch> 
  <Route></Route>
  <Route></Route>
  <Route></Route>
</Switch>
```
The switch will match the first route and return that one, so ordering is important. 

Generic routes at the end, more exact routes at the top. 

Dynamic pathing works similar to express: 
```js
<Switch>
  <Route path="/products/:id">
    <Product />
  </Route>
  <Route path>
    <h3>Choose your Product</h3>
  </Route>
</Switch>
```

Leaving the path blank will make sure it gets grabbed. 

We can map through an array of data and create links for each\

More Hooks!:

> useRouteMatch

URL is the actual url to go to.
Path can be dynamic.


### Styled Components

Helps us bundle our css, only rendering the critical css for what is on the screen. 


Has a weird syntax. We create our styled components in a variable:

```js
const Header = styled.header`
  background-color: tomato;
`;

const Styled = () => {
  return(
    <Header>
    <h1>Styled Component</h1>
    </Header>
  )
}
```

We can style based on props with this library. 


### Component Libraries

* Why build our own if other developers have done a great job?
  * Can get more consistent design
  * Hafiz approves this message. 

Popular ones:

1. Ant Design
2. Material-UI
3. React Bootstrap

### useRef

Before React, html attributes could be passed objects that refer to the html element. 

useRef comes with react, 
has one key --> current:


useRef lets us bind to a particular html element, even through rerenders, and helps us to get through stale state issues

> Read through more of the react hooks via react api docs.