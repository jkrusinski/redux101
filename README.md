# Redux101

> *"Redux is a predictable state container for JavaScript apps."* \- [Redux Documentation](http://redux.js.org/)

### What is State?

Before we can figure out what the above definition tells us, we first need to understand another important concept—state. When we talk about state in an application, we are talking about all of the variables (or more specifically locations in memory) that can change in value over *time*. A stateful application is designed to remember preceding events or user interactions and behave respectively. While this may seem like a simple concept, you may know that managing state is a source of frustration for many developers. This is because changing state is inherently an asynchronous process, which as you know is a difficult concept to represent in code. On top of having to visualize how your application changes over time, many different parts of your code may depend upon or even manipulate the same piece of state. Separating or even repeating this logic across your code provides an abundance of opportunity for bugs to appear as the project develops.

### What is Redux?

By now you might be thinking to yourself, why don't we design our application so that all of the logic concerning state is organized in one central location? Since the same pieces of state are depended upon by many different parts of our application, it makes sense to organize our application in this way. Redux is a design pattern to help you achieve just that.

Redux is not a framework, rather a lightweight implementation of Flux, a one-way data flow architecture. The Redux container itself is not provided for you, rather it is something you build yourself by adhering to the Redux guidelines. In fact, the Redux library is just a collection of helper functions that you could easily implement yourself with enough understanding of it.

Finally, Redux is not related with any specific front-end framework. Many people believe that React and Redux are intrinsically bound, but in fact you can use Redux with almost any front-end framework. That being said, React works especially well with Redux since it allows you to describe your application components as a function of state. Because of that complementary nature, I will be using React as the front-end framework for the examples in this tutorial.

### Why Use Redux?

Setting up your application to implement Redux can be time consuming in the beginning and requires a lot of boilerplate code. This barrier to start coding your application causes many developers first starting out with Redux to quickly dismiss it. Many programmers also find Redux overly complicated, and in a way it is by design. The tradeoffs that Redux provides, in my opinion, far outweigh the barriers that are in place when setting up your application with Redux. Some notable advantages Redux can provide for you include ([source](https://www.smashingmagazine.com/2016/06/an-introduction-to-redux/#benefits-of-redux)):

- __Predictability Of Outcome:__ There is always one source of truth, the store, with no confusion about how to sync the current state with actions and other parts of the application.
- __Maintainability:__ Having a predictable outcome and strict structure makes the code easier to maintain.
- __Organization:__ Redux is stricter about how code should be organized, which makes code more consistent and easier for a team to work with.
- __Server Rendering:__ This is very useful, especially for the initial render, making for a better user experience or search engine optimization. Just pass the store created on the server to the client side.
- __Developer Tools:__ Developers can track everything going on in the app in real time, from actions to state changes. It can even let you rewind actions made to your UI to make debugging a breeze.
- __Ease of Testing:__ The first rule of writing testable code is to write small functions that do only one thing and that are independent. Redux's code is mostly functions that are just that: small, pure, and isolate.
