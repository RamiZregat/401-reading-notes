# useState() Hook

## Review, Research, and Discussion

1. How does React differ from vanilla JS/HTML/CSS?
   - In **vanilla** each page is a separate `HTML` page, while in **React**, there is only one `HTML` page that change its content dynamically.
2. What is the primary difference between a function component and a class component?
   - Functional components are functions rather than instance of the React.component class, as such their syntax and form is entirely different. Most if not all functionality is identical across the two designs. Also, in Class components `this` is used to set the state and define functions, but in Function components `useState` is used to define states.

---

## Terms

> Functional Components: These are React components written as functions rather than classes, and have a host of hooks available to them to enable React functionality.

> Children / Child Components: Children components are contained within a parent component.



```

<Parent>
  <Child 1>
    <GrandChild 2/>
    <GrandChild 3/>
  </Child 1>
</Parent>

```


---

## Preparation Materials

### making sense of hooks

> Everything written here is related to React conference 2018
Using Class Components can be tedious and sometimes problematic when breaking a component into more components is not possible anymore. Thus the following situations appears:

- **Huge components** that are hard to refactor and test.
- **Duplicated logic** between different components and lifecycle methods.
- **Complex patterns** like render props and higher-order components.

Hooks let us organize the logic inside a component into reusable isolated units.

Hooks apply the React philosophy (explicit data flow and composition) inside a component, rather than just between the components.

- Hooks don’t introduce unnecessary nesting into your component tree.

Since Hooks are regular JavaScript functions, you can combine built-in Hooks provided by React into your own “custom Hooks”.

Hooks are fully encapsulated — each time you call a Hook, it gets isolated local state within the currently executing component.

- Each Hook may contain some local state and side effects. You can pass data between multiple Hooks just like you normally do between functions. They can take arguments and return values because they are JavaScript functions.

- Hooks open the door for powerful interactive debugging tools.

### The State Hook

- Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

**What is a Hook?**  
 A Hook is a special function that lets you “hook into” React features (like `useState`).

**When would I use a Hook?** If you write a function component and realize you need to add some state to it,you can use a Hook inside the existing function component.

In Function component we do not use `this` keyword, but we rather use `useState` Hook to define a new state in our application.



```

import React, { useState } from 'react';
function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

```



- Calling `useState` defines a state as a variable. Ths variable can be anything (number, string, array ot even object as **Class Component** do), and It returns a pair of values: the current state and a function that updates it.

- A plus feature from previous **Classes**, that we can read our state directly as they are ony variables.



```

<p>You clicked {count} times</p>

```


- To update a state, you have to call the function related to it when you have declared it initially.


```
const [count, setCount] = useState(0);
<button onClick={() => setCount(count + 1)}>
    Click me
  </button>

```


example on two components written in both methods:

> Class Component



```

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}


```


> Function Component


```

import React, { useState } from 'react';
function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### Hooks at a Glance

- To create more than one state in a single component, you can call `useState` multiple times.

```
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```

**side effects**: data fetching, subscriptions, or manually changing the DOM from React components.

The Effect Hook, `useEffect`, adds the ability to perform side effects from a function component. It serves the same purpose as `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` in **React classes**, but unified into a single API.

Here is an example on `useEffect`:

```
import React, { useState, useEffect } from 'react';
function Example() {
  const [count, setCount] = useState(0);
  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

`useEffect` tells React to run “effect” function after flushing changes to the DOM. Effects are declared inside the component so they have access to its props and state. By default, React runs the effects after every render — including the first render.

- You can use more than a single effect in a component:

```
function FriendStatusWithCounter(props) {
  const [count, setCount] = useState(0);
  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });
  const [isOnline, setIsOnline] = useState(null);
  useEffect(() => {
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });
  function handleStatusChange(status) {
    setIsOnline(status.isOnline);
  }
```

Hooks have some rules you have to follow when implementing, which are:

- Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions.
