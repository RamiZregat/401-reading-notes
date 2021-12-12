# Context API

## Review, Research, and Discussion

1. Describe use cases for `useMemo() `and `useReducer()`

   - `useReducer()` is useful when you need to use complex state logic, when you have multiple sub values, or when the next state depends on the previous state.

   - Use `useMemo()` runs during rendering, and it will only recompute the memoized value when one of its dependents has changed. This is an optimized way to avoid calculations every re-render.

2. Why do custom hooks need the use prefix?

   - It needs the prefix so that looking at it, you can immediately tell that it is a hook. Without this, it looks just like a regular function.

3. What do custom hooks usually do?

   - They give functionality that can be used across multiple components, and they are better than functions because they can access state and component lifecycle.

4. Using any list of custom hooks, research and name one that you think will be useful in your applications

   - `useClippy` : A hook for copying data to the clipboard and retrieving/pasting it using Ctrl-C/Command-C and Ctrl-V/Command-V.

ex)

```
import useClippy from "use-clippy"
function Component() {
    const [ clipboard, setClipboard ] = useClipy()
    return (
        <div>
            <div>Clipboard</div>
            <div>{clipboard}</div>
            <button onClick={() => setClipboard("nnamdi")}>Set Clipboard</button>
        </div>
    )
}
```

5. Describe how a hook that fetches API data might work

   - An API fetching hook would take in a url and any info necessary for the request and return the results of the API call. It could use a callback to update the state with the returned results.

## Terms

- reducer :

  > is a function that determines changes to an application's state. It uses the action it receives to determine this change.
---

## Preparation Materials

Using the React "Context API" we can create an manage state in a more "global" fashion, making state that matters to your entire application easily available to ... your entire application.

### Context API

`Context` is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult. If you only want to avoid passing some props through many levels, component composition is often a simpler solution than context.

### When to Use Context

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred