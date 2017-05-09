# Redux

Redux is a tool for centralizing *state* in your application. Redux can be combined with *any* front end framework, or even with vanilla JS, HTML and CSS. A great use case for Redux is with React, providing a convenient alternative to React's one way data flow. A great place to start reading about Redux is [Redux Core Concepts](http://redux.js.org/docs/introduction/CoreConcepts.html)

## [Three Principles of Redux](http://redux.js.org/docs/introduction/ThreePrinciples.html)

  1. **Single Source of Truth**: A redux application has a single state contained within the Store. 
  2. **State is read-only**: An application reads from the state. The only way to write to the state is to dispatch an *Action*, which is interpreted by a *Reducer*
  3. **Changes are made with pure functions**

## Example Data Flow: Adding a Todo
  1. in ```index.js``` the App component is wrapped in a Provider component with the store, making the store available to app and all of its children
  2. AddTodo is connected to the store using the connect() function. This makes store available as an argument
  3. ```store.dispatch(addTodo(input.value))```
     - ```addTodo``` is imported from the actions folder at the top of the file
     - It is invoked with the contents of the form
        - This *dispatches an Action* with *type* 'ADD_TODO', an id, and a text value for this todo
     - This *type* of action is heard by the *reducers* contained in ```todos.js ``` which return a **new** state for the application
  4. Because VisibleTodoList is *connected*, it rerenders every time there is a change to the store
    - VisibleTodoList renders in turn a TodoList with the updated list of todos from the store
    
## Async Redux
  1. [Redux Promise](https://github.com/acdlite/redux-promise) is a [Redux middleware](http://redux.js.org/docs/advanced/Middleware.html) that allows one to create actions with asynchronous function calls
    - Pulser: Middleware boilerplate in store.jsx
    - Pulser: userData flow in app.jsx, actions.jsx, userReducer.jsx

## Redux and React Router
>"Redux will be the source of truth for your data and React Router will be the source of truth for your URL. In most of the cases, it is fine to have them separate unless you need to time travel and rewind actions that triggers the change URL."  
#### Redux docs

## Resources / Sources:
  0. People - Christopher, Alex, Ross, Johnny and I have all worked with Redux on our respecive thesis projects. Hit us up! Scott knows a lot about testing
  1. [Redux Docs](http://redux.js.org/docs/introduction/CoreConcepts.html) - Core Concepts
  2. [Egghead.io with Redux's author, Dan Abramov](https://egghead.io/lessons/javascript-redux-passing-the-store-down-with-provider-from-react-redux)
  3. [Redux Todo App Source Code](https://github.com/reactjs/redux/tree/master/examples/todos) - comes with *tests* baked in
  4. [React Router and Redux in the TodoList](http://redux.js.org/docs/advanced/UsageWithReactRouter.html)
  4. [Async Redux](http://redux.js.org/docs/advanced/AsyncFlow.html)
  5. [Redux-Promise](https://github.com/acdlite/redux-promise)
  6. [Pulser Source Code](https://github.com/AriLFrankel/FollowMe)
  7. [OpenSauce Source Code](https://github.com/OpenSauced/OpenSauce)
  8. [**Deep dive** into the TodoList app with Dan Abramov](https://www.youtube.com/watch?v=VJ38wSFbM3A)
