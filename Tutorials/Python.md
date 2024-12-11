![Python](../assets/python.png)

# Python Basics Tutorial for Beginners

Python is a high-level, interpreted, and general-purpose programming language. It's known for its readability and efficiency, making it a popular choice for beginners and experts alike. This tutorial covers the basics of Python, including installation, syntax, data types, control structures, and functions.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Python](#getting-started-with-python)
  - [What is Python?](#what-is-python)
  - [Installation](#installation)
  - [Running Python](#running-python)
- [Python Basics](#python-basics)
  - [Syntax and Indentation](#syntax-and-indentation)
  - [Variables and Data Types](#variables-and-data-types)
  - [Control Structures](#control-structures)
    - [If Statements](#if-statements)
    - [Loops](#loops)
  - [Functions](#functions)
  - [Lists and Dictionaries](#lists-and-dictionaries)
- [Advanced Python Concepts (Optional)](#advanced-python-concepts-optional)
- [Best Practices](#best-practices)
- [Conclusion](#conclusion)
- [Further Learning](#further-learning)
- [Contribution](#contribution)

<br>

## **Overview**

Python is a high-level, interpreted, and general-purpose programming language. It's known for its readability and efficiency, making it a popular choice for beginners and experts alike. This tutorial covers the basics of Python, including installation, syntax, data types, control structures, and functions.

<br>

## **Getting Started with Python**

### **What is Python?**

Python is a versatile language used for various applications, from web development to data science and artificial intelligence.

### **Installation**

| Platform  | Installation Method                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------|
| Windows   | Download Python from the [official Python website](https://www.python.org/downloads/) and run the installer. |
| Linux     | Python usually comes pre-installed. If not, install it using your package manager.                   |
| macOS     | Use Homebrew: `brew install python`.                                                                 |

### **Running Python**

| Method                   | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| Interactive Shell        | Type `python` or `python3` in your terminal or command prompt.             |
| Python Scripts           | Write Python code in a file with a `.py` extension and run it using `python filename.py`. |

<br>

## **Python Basics**

### **Syntax and Indentation**

- Python uses indentation to define code blocks.
- No need for semicolons at the end of statements.

<br>

### **Variables and Data Types**

- Variables are used to store data values.
- Python has various data types: strings, integers, floats, booleans, lists, tuples, sets, and dictionaries.

```python
my_string = "Hello, Python!"
my_int = 10
my_float = 20.5
my_bool = True
```

<br>

### **Control Structures**

#### **If Statements**

```python
if my_int > 5:
    print("Greater than 5")
elif my_int == 5:
    print("Equal to 5")
else:
    print("Less than 5")
```

#### **Loops**

- **For Loop**:

  ```python
  for i in range(5):
      print(i)
  ```

- **While Loop**:

  ```python
  while my_int < 15:
      print(my_int)
      my_int += 1
  ```

<br>

### **Functions**

- Functions are defined using the `def` keyword.
- Functions can have parameters and return values.

```python
def greet(name):
    return "Hello, " + name + "!"

print(greet("Alice"))
```

<br>

### **Lists and Dictionaries**

- **Lists**: Ordered and changeable collections.

  ```python
  my_list = [1, 2, 3]
  ```

- **Dictionaries**: Unordered, changeable, and indexed collections.

  ```python
  my_dict = {"name": "Alice", "age": 25}
  ```

<br>

## **Advanced Python Concepts (Optional)**

- **List Comprehensions**: Concise way to create lists.
- **Lambda Functions**: Small anonymous functions.
- **Modules and Packages**: Organizing larger Python projects.

<br>

## **Best Practices**

- **Code Readability**: Write clear and readable code.
- **Consistent Naming Conventions**: Use meaningful and consistent naming.
- **Commenting and Documentation**: Regularly comment and document your code.

<br>

## **Conclusion**

Python's simplicity and power make it ideal for a wide range of applications. Understanding its basics lays the foundation for advanced programming and specialized fields like web development and data science.

<br>

## **Further Learning**

- [Official Python Documentation](https://docs.python.org/3/)
- [Online Courses](https://www.coursera.org/, https://www.udemy.com/, https://www.codecademy.com/)

<br>

## **Contribution**

Your contributions are highly encouraged to enhance this guide:

- Fork the repository.
- Create a new branch:

    ```bash
    git checkout -b my-awesome-feature
    ```

- Make your valuable changes.
- Commit your changes:

    ```bash
    git commit -am 'Added some amazing features'
    ```

- Push to the branch:

    ```bash
    git push origin my-awesome-feature
    ```

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve this guide.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
