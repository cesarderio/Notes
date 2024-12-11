<!-- <img src="../assets/react.png" alt="React" width="400"> -->

# Basic React Tutorial

Learn the fundamentals of React, a popular JavaScript library for building interactive user interfaces and single-page applications.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Getting Started](#getting-started)
  - [Creating Components](#creating-components)
  - [Using Props and State](#using-props-and-state)
  - [Handling Events](#handling-events)
  - [Conditional Rendering](#conditional-rendering)
  - [Lists and Keys](#lists-and-keys)
  - [Working with Forms](#working-with-forms)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

React is a JavaScript library developed by Facebook for building reusable, component-based user interfaces. It makes creating interactive UIs efficient and declarative.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the basic concepts of React, including components, props, and state.
- Be able to build a simple React application.
- Learn how to handle events, render conditionally, and manage forms in React.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a basic understanding of JavaScript, HTML, and CSS.
- Have Node.js and npm (or yarn) installed. [Download here](https://nodejs.org/).
- Install a code editor like Visual Studio Code.

<br>

## **Steps**

### **Getting Started**

| Command/Syntax                   | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `npx create-react-app my-app`    | Creates a new React application.                    | `npx create-react-app my-app`              |
| `cd my-app`                      | Navigates to the app directory.                     | `cd my-app`                                |
| `npm start`                      | Starts the development server.                      | `npm start`                                |
| `npm install [package-name]`     | Installs a new npm package (e.g., a React library).  | `npm install react-router-dom`             |

### **Creating Components**

| Syntax                           | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| Functional Component             | Defines a React component as a function.           | `function Hello() { return <h1>Hello</h1>; }` |
| JSX                              | JavaScript XML, a syntax extension for defining UI. | `<div>Hello, React!</div>`                |
| Component Composition            | Combines multiple components in a parent.          | `<Header /><Main /><Footer />`            |

### **Using Props and State**

| Concept                          | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `props`                          | Passes data to child components.                   | `<Greeting name="John" />`                |
| `useState`                       | Adds local state to a functional component.         | `const [count, setCount] = useState(0);`  |

### **Handling Events**

| Syntax                           | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `onClick`                        | Handles click events.                              | `<button onClick={handleClick}>Click Me</button>` |
| Event handler                    | Defines a function to handle an event.             | `function handleClick() { alert("Clicked"); }` |

### **Conditional Rendering**

| Syntax                           | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `if` statement                   | Renders based on conditions.                       | `{isLoggedIn ? <Logout /> : <Login />}`   |
| `&&` operator                    | Renders only if the condition is true.             | `{isAdmin && <AdminPanel />}`            |

### **Lists and Keys**

| Syntax                           | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `.map()`                         | Iterates over an array to render components.        | `{items.map(item => <li>{item}</li>)}`    |
| `key` prop                       | Adds a unique identifier to each list item.         | `<li key={item.id}>{item.name}</li>`      |

### **Working with Forms**

| Syntax                           | Description                                         | Example                                    |
|----------------------------------|-----------------------------------------------------|--------------------------------------------|
| `onChange` event                 | Captures input changes.                            | `<input onChange={handleChange} />`       |
| Controlled component             | Links input value to state.                        | `<input value={name} onChange={setName} />`|

<br>

## **Examples**

Here’s an example of a simple React counter app:

```jsx
import React, { useState } from 'react';

function Counter() {
    const [count, setCount] = useState(0);

    const increment = () => setCount(count + 1);
    const decrement = () => setCount(count - 1);

    return (
        <div>
            <h1>Count: {count}</h1>
            <button onClick={increment}>Increment</button>
            <button onClick={decrement}>Decrement</button>
        </div>
    );
}

export default Counter;
```

To run this:

1. Save it as `Counter.js` in the `src` folder of your React app.
2. Import and use it in `App.js`:

   ```jsx
   import Counter from './Counter';

   function App() {
       return (
           <div>
               <Counter />
           </div>
       );
   }

   export default App;
   ```

3. Start your app:

   ```bash
   npm start
   ```

<br>

## **Notes**

- Use JSX to write cleaner and more readable React code.
- Break components into smaller, reusable pieces for better maintainability.
- Use `React Developer Tools` in your browser for debugging React components.

<br>

## **Resources**

- [Official React Documentation](https://reactjs.org/docs/getting-started.html)
- [React Cheat Sheet](https://reactcheatsheet.com/)
- [React GitHub Repository](https://github.com/facebook/react)

<br>

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b add-react-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -m "Added React tutorial"
  ```

- Push to the branch:

  ```bash
  git push origin add-react-tutorial
  ```

- Create a Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues or suggest enhancements.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/09/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
