# Component Based UI

## Review, Research, and Discussion

1. Name 5 Javascript UI Frameworks (other than React)

   - Angular  
   - Webix 
   - Vue 
   - Sencha
   - Syncfusion



2. What’s the difference between a framework and a library?

- Both frameworks and libraries are code written by someone
- Both libraries and frameworks are reusable code written by someone else.
- The ain deference is the level of freedom a developer has when structuring their code. When using a library, you control the data flow in the app. While a framework controls how data flow in the app, but you control what data, order, inputs and etc.


## Terms


> Rendering: according to `Wikipedia` **Rendering** or image **synthesis** is the process of generating a photorealistic or non-photorealistic image from a 2D or 3D model by means of a computer program. However, in `Web`. It is taking `html` tags and defining them, then defining `css` rules and applying them to the `DOM` tree and after that displaying three in the browser window in the right order.

> Templates: A website template is a predesigned resource that shows the structure for the comprehensive layout and display features of any website. It is provided by various suppliers to help make Web design a lot easier for designers.

> State: There are three types of state that are important in web application. `Application State` (also known as `Program State`) represents the totality of everything necessary to keep your application running. `Resource State` refers to the state of the resources being stored on the server. And Last but not least, `Session State` which keeps track of user interaction during a browser session.


## Preparation Materials

### introducing JSX

`JSX` is syntax extension to JavaScript and produces `React` “elements”.

- `JSX` is used to create both markups and logics with one kinda language.

- ex)

```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

- In the example above `name`, which is inside the curly brackets can be any valid `JS` expression. It can be a function, object, mathematical operation...etc.

- `JSX` expressions become regular JavaScript function calls and evaluate to JavaScript objects. That means it can be used in many methods, like `if` statements, `for` loops, assigned in variables ...etc.

- You can set attributes by using either quotes or curly braces, but nit both at the same time.

```
const element = <div tabIndex="0"></div>;
const element = <img src={user.avatarUrl}></img>;
```

- By default, React DOM escapes any values embedded in JSX before rendering them. Thus it ensures that you can never inject anything that’s not explicitly written in your application. Everything is converted to a string before being rendered. This helps prevent XSS (cross-site-scripting) attacks.

### rendering elements

- Elements are the smallest building blocks of React apps.

- Unlike browser DOM elements, React elements are plain objects, and are cheap to create. React DOM takes care of updating the DOM to match the React elements.

- Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.

- To update the rendered element in react, you have to add a new element.

- React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.