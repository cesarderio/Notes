<img src="../assets/javascript.png" alt="JavaScript" width="400">

# Basic JavaScript Tutorial

Learn the fundamentals of JavaScript, the versatile programming language that powers interactivity and functionality on the web.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Getting Started](#getting-started)
  - [Variables and Data Types](#variables-and-data-types)
  - [Conditionals and Loops](#conditionals-and-loops)
  - [Functions](#functions)
  - [DOM Manipulation](#dom-manipulation)
  - [Debugging and Error Handling](#debugging-and-error-handling)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

JavaScript is a high-level programming language commonly used to create dynamic web pages, develop interactive applications, and control web page content. It’s an essential tool for modern front-end and back-end development.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand JavaScript basics, including variables, loops, and functions.
- Be able to write JavaScript code to interact with web pages.
- Learn debugging techniques to troubleshoot JavaScript errors.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a basic understanding of HTML and CSS.
- Use a web browser with a developer console (e.g., Chrome, Firefox).
- Optionally install a code editor like Visual Studio Code.

<br>

## **Steps**

### **Getting Started**

| Command/Syntax           | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| `<script>` tag           | Embeds JavaScript in HTML.                         | `<script src="script.js"></script>`           |
| `console.log()`          | Outputs messages to the browser’s developer console.| `console.log("Hello, World!");`              |
| `alert()`                | Displays a browser alert dialog.                   | `alert("Welcome!");`                          |

### **Variables and Data Types**

| Syntax                   | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| `let`                    | Declares a block-scoped variable.                  | `let name = "John";`                          |
| `const`                  | Declares a constant variable.                      | `const pi = 3.14;`                            |
| `var`                    | Declares a function-scoped variable (legacy).      | `var age = 25;`                               |
| Data types               | Common types: String, Number, Boolean, Object, Array.| `let isActive = true;`                       |

### **Conditionals and Loops**

| Syntax                   | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| `if (condition)`         | Executes a block if the condition is true.         | `if (x > 0) { console.log("Positive"); }`     |
| `for` loop               | Iterates over a block of code a fixed number of times.| `for (let i = 0; i < 5; i++) { console.log(i); }`|
| `while` loop             | Iterates as long as the condition is true.         | `while (x > 0) { x--; }`                      |

### **Functions**

| Syntax                   | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| Function declaration     | Defines a reusable function.                       | `function greet(name) { return "Hello " + name; }`|
| Function expression      | Stores a function in a variable.                   | `const add = function(a, b) { return a + b; };`|
| Arrow functions          | Concise syntax for functions.                      | `const subtract = (a, b) => a - b;`           |

### **DOM Manipulation**

| Command/Syntax           | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| `document.getElementById()`| Selects an element by its ID.                    | `document.getElementById("myDiv")`            |
| `document.querySelector()`| Selects the first matching element.               | `document.querySelector(".myClass")`          |
| `.innerHTML`             | Sets or gets the HTML content of an element.       | `document.getElementById("myDiv").innerHTML = "Hello!";`|
| `.addEventListener()`    | Attaches an event handler to an element.           | `button.addEventListener("click", () => alert("Clicked!"));`|

### **Debugging and Error Handling**

| Command/Syntax           | Description                                        | Example                                       |
|--------------------------|----------------------------------------------------|-----------------------------------------------|
| `try { ... } catch (e)`  | Handles runtime errors in a code block.            | `try { console.log(x); } catch (e) { console.error(e); }`|
| `console.error()`        | Outputs error messages to the console.             | `console.error("This is an error!");`         |
| Browser DevTools         | Built-in tools for debugging JavaScript.           | Use F12 in most browsers.                     |

<br>

## **Examples**

Here’s an example of JavaScript interacting with the DOM:

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Example</title>
</head>
<body>
    <h1 id="header">Welcome!</h1>
    <button id="changeText">Change Text</button>

    <script>
        const button = document.getElementById("changeText");
        button.addEventListener("click", () => {
            document.getElementById("header").innerHTML = "Text Changed!";
        });
    </script>
</body>
</html>
```

To test this:

1. Save the code in a `.html` file.
2. Open the file in a browser.
3. Click the button to change the header text.

<br>

## **Notes**

- Always use `const` or `let` instead of `var` for variable declarations.
- Use browser developer tools to debug your JavaScript code efficiently.
- Modularize your code by organizing functions and reusable logic.

<br>

## **Resources**

- [JavaScript Documentation (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [JavaScript Cheat Sheet](https://htmlcheatsheet.com/js/)
- [Eloquent JavaScript (Book)](https://eloquentjavascript.net/)

<br>

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b add-javascript-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -m "Added JavaScript tutorial"
  ```

- Push to the branch:

  ```bash
  git push origin add-javascript-tutorial
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
