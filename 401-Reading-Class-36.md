# Application State with Redux

## Review, Research, and Discussion

1. What are the advantages of storing tokens in “Cookies” vs “Local Storage”

   - The advantage is Cookies are mainly for reading server-side, whereas local storage can only be read by the client-side. Plus, cookie can be made to persist for an arbitrary length of time

2. Explain 3rd party cookies.

   - Third-party cookies are cookies that are set by a website other than the one you are currently on. For example, you can have a "Like" button on your website which will store a cookie on a visitor's computer, that cookie can later be accessed by Facebook to identify visitors and see which websites they visited. Such a cookie is considered to be a 3rd party cookie.

3. How do pixel tags work?
   - Pixel tags (also called clear GIFs, web beacons, or pixels) are small blocks of code on a webpage that allow websites to do things like read and place cookies. The resulting connection can include information such as the person’s IP address, the time the person viewed the pixel and the type of browser being used.

---

## Terms

- cookies

  > cookies are small files which are located on a user’s computer. They are designed to hold a generous amount of data specific to a client and website, and they can accessed either by the web server or the client computer.

- authorization

  > Authorization in the `web` is related to what a user is allowed to have, do, access, edit, delete, etc.

- access control

  > The term is related to web authorization. One type is `Role-based access control`, where authorization is based on the role the user has. There are other types like, `Mandatory access control, Discretionary access control, Attribute-based access control`

- conditional rendering

  > To render an element on the browser at the satisfaction of a condition, like the existing of a certain state or its value.
---

## Preparation Materials

### Fundamentals of Redux Course from Dan Abramov


- `Redux` is a predictable state container for `JavaScript` apps.

- `State management` is absolutely critical in providing users with a well-crafted experience with minimal bugs.

- `Redux` helps organizing `React` code, to make it easier to read and functions.

#### Redux Advantages:

- Predictable:

  > Redux helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test.

- Centralized:

  > Centralizing your application's state and logic enables powerful capabilities like undo/redo, state persistence, and much more.

- Debuggable:

  > The Redux DevTools make it easy to trace when, where, why, and how your application's state changed. Redux's architecture lets you log changes, use "time-travel debugging", and even send complete error reports to a server.

- Flexible:

  > Redux works with any UI layer, and has a large ecosystem of addons to fit your needs.
