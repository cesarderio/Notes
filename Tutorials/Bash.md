<img src="../assets/bash.png" alt="Bash Script" width="400">

# Basic Bash Scripting

Learn the fundamentals of Bash scripting, a powerful tool for automating tasks, managing system processes, and writing reusable scripts to improve productivity.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Getting Started](#getting-started)
  - [Variables and Parameters](#variables-and-parameters)
  - [Conditionals and Loops](#conditionals-and-loops)
  - [Functions](#functions)
  - [File and Directory Operations](#file-and-directory-operations)
  - [Error Handling](#error-handling)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Bash (Bourne Again Shell) is a Unix shell and command language used as the default login shell for most Linux distributions. It enables you to automate repetitive tasks, manage system operations, and write efficient scripts.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the basics of Bash scripting.
- Be able to write and execute simple Bash scripts.
- Learn key concepts such as variables, conditionals, loops, and functions.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a Linux or Unix-based system with Bash installed (default on most systems).
- Basic familiarity with the command line.
- A text editor like Vim, Nano, or VS Code.

<br>

## **Steps**

### **Getting Started**

| Command                 | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `bash`                  | Starts an interactive Bash shell session.              | `bash`                           |
| `chmod +x [file.sh]`    | Makes a script executable.                              | `chmod +x script.sh`             |
| `./[file.sh]`           | Executes a script in the current directory.             | `./script.sh`                    |
| `#!/bin/bash`           | Specifies the interpreter for the script (shebang).     | Place it at the start of a script.|

### **Variables and Parameters**

| Syntax                  | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `variable=value`        | Assigns a value to a variable (no spaces allowed).      | `name="John"`                    |
| `$variable`             | Accesses the value of a variable.                       | `echo $name`                     |
| `$1, $2, ...`           | Accesses positional parameters (script arguments).      | `echo $1`                        |

### **Conditionals and Loops**

| Syntax                  | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `if [ condition ]; then`| Executes code if condition is true.                     | `if [ -f file.txt ]; then`       |
| `for var in list; do`   | Iterates over a list.                                   | `for i in 1 2 3; do echo $i; done`|
| `while [ condition ]; do`| Loops while a condition is true.                       | `while [ $i -lt 5 ]; do ((i++)); done`|

### **Functions**

| Syntax                  | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `function_name () {}`   | Defines a reusable function.                             | `greet() { echo "Hello, $1"; }`  |
| `function_name`         | Calls a defined function.                                | `greet "World"`                  |

### **File and Directory Operations**

| Command                 | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `touch file.txt`        | Creates a new file.                                      | `touch myfile.txt`               |
| `rm file.txt`           | Deletes a file.                                          | `rm oldfile.txt`                 |
| `mkdir folder`          | Creates a new directory.                                 | `mkdir myfolder`                 |

### **Error Handling**

| Command                 | Description                                             | Example                           |
|-------------------------|---------------------------------------------------------|-----------------------------------|
| `set -e`                | Exits script on the first error.                         | Add `set -e` at the top.         |
| `||`                    | Executes the next command if the previous one fails.    | `command || echo "Failed"`       |

<br>

## **Examples**

Here’s an example of a simple script:

```bash
#!/bin/bash

# Script to greet a user
echo "Enter your name:"
read name
echo "Hello, $name! Welcome to Bash scripting."
```

To run this script:
1. Save it as `greet.sh`.
2. Make it executable:

   ```bash
   chmod +x greet.sh
   ```

3. Execute the script:

   ```bash
   ./greet.sh
   ```

<br>

## **Notes**

- Use `#` to add comments and improve script readability.
- Test scripts on a non-production system to avoid accidental damage.
- Use `set -x` to enable debugging mode and trace execution.

<br>

## **Resources**

- [Official Bash Documentation](https://www.gnu.org/software/bash/manual/bash.html)
- [Bash Scripting Cheat Sheet](https://devhints.io/bash)
- [Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/)

<br>

## **Contribution**

Your contributions can make these scripts even better:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.

- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/09/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
