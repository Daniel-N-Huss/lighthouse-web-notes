# Component Based UI's With React:


* Review functions

When you want to change a parent variable you need to pass a function into the child that has closure over the parent variable.

This is a MEGA important concept for react.

Key Takeaways:

- Data can be created internally or passed in as an argument
- Internally generated data can be called STATE (loosely)
- External data are called PROPS
- The state of a parent function can be props to a child function
  - Props are what can be fetched from the passed in data (like object keys)
- To allow a child component to modify a parent's state, the parent has to authorize the child to change it's state by passing in a function props that the child can call.

## Why React? 

- It's more about performance - React looks at the differences between two states and only re-renders what has changed rather than rerendering the whole dom (ala - tweeter)


## Rules of JSX

- Gotta close tags
- No HTML comments
- camelCase for most DOM attributes
- Children must close before Parent component
- JS logic goes in {}
- JSX expression limits us to returning a single node (everything has to be wrapped into one parent layer, no returning two things)
- Use PascalCase for React Components



## Props and State Intro:

- Components 'always' get passed an arg which is an object. By convention its called Props. (Advanced topic beyond bootcamp would be passing multiple params)
- Use destructuring! 


Hafiz Suggetions for Workflow: Use a component, THEN create it. 

Hooks (magic) 
  - A special hook is called useState:
    ```js
    const stateArr = useState('today')
    ```

    useState lets us update the state; it's an array that contains the current state, and also a function to set the state. 

    ```js
    const [day, setDay] = useState('today')
    ```

    Make dynamic:
    When you set a state the whole component refreshes. So, things like setTimeout gets called over and over because of the refresh. 



## Tweeter Refactor

### Intro to Storybook:

Storybook lets us build react components in isolation.



Filestructure for React dev: keep things that are changing together in a folder. 

ie: 
src > components > sub component > button/textbox/etc


For tweeter, we've broken it down into a nav bar, a profile aside, a tweet form, and a tweet display case.


Importing our components into a .stories file
components can be written in .jsx files
