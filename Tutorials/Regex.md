![Regex](../assets/regex.png)

# Regex Tutorial

Regular expressions (Regex) are powerful tools for pattern matching and text processing. They are widely used in programming, text editing, and data validation.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Regex](#getting-started-with-regex)
  - [What is Regex?](#what-is-regex)
  - [Common Use Cases](#common-use-cases)
- [Basic Syntax](#basic-syntax)
  - [Characters and Literals](#characters-and-literals)
  - [Metacharacters](#metacharacters)
- [Quantifiers](#quantifiers)
  - [Greedy Quantifiers](#greedy-quantifiers)
  - [Lazy Quantifiers](#lazy-quantifiers)
- [Groups and Capturing](#groups-and-capturing)
  - [Using Parentheses](#using-parentheses)
  - [Named Groups](#named-groups)
- [Assertions and Lookarounds](#assertions-and-lookarounds)
  - [Anchors](#anchors)
  - [Lookahead and Lookbehind](#lookahead-and-lookbehind)
- [Advanced Regex](#advanced-regex)
  - [Flags](#flags)
  - [Escape Sequences](#escape-sequences)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Regular expressions provide a concise way to describe patterns in strings. They are supported by most programming languages and text editors, making them an essential tool for developers and data analysts.

<br>

## **Getting Started with Regex**

### **What is Regex?**

Regex is a sequence of characters that define a search pattern. It can be used to match, search, replace, or split strings based on specified patterns.

### **Common Use Cases**

- Validating email addresses.
- Searching for specific text in large datasets.
- Replacing or extracting text.

<br>

## **Basic Syntax**

### **Characters and Literals**

- Match exact characters by typing them directly:

  ```regex
  hello
  ```

  Matches: "hello" in "hello world."

- Match any single character with a dot (`.`):

  ```regex
  h.llo
  ```

  Matches: "hello", "hallo".

### **Metacharacters**

- **`\d`**: Matches any digit (0-9).
- **`\w`**: Matches any word character (letters, digits, underscores).
- **`\s`**: Matches any whitespace (spaces, tabs, newlines).
- **`.`**: Matches any character except a newline.

Examples:

```regex
\d{3}
```

Matches: "123" in "abc123xyz".

```regex
\w+
```

Matches: "hello" in "hello world".

<br>

## **Quantifiers**

### **Greedy Quantifiers**

- **`*`**: Matches 0 or more occurrences.
- **`+`**: Matches 1 or more occurrences.
- **`?`**: Matches 0 or 1 occurrence.
- **`{n,m}`**: Matches between `n` and `m` occurrences.

Examples:

```regex
h.*o
```

Matches: "hello" in "hello world".

```regex
\d{2,4}
```

Matches: "123" in "12345".

### **Lazy Quantifiers**

Lazy quantifiers match as few characters as possible:

- **`*?`**: Matches 0 or more (lazy).
- **`+?`**: Matches 1 or more (lazy).
- **`{n,m}?`**: Matches between `n` and `m` (lazy).

<br>

## **Groups and Capturing**

### **Using Parentheses**

Use parentheses to group patterns:

```regex
(a|b)c
```
Matches: "ac" or "bc".

### **Named Groups**

Assign names to groups for easier referencing:

```regex
(?<name>\w+)
```
Matches: "john" in "john123" with the group name "name".

<br>

## **Assertions and Lookarounds**

### **Anchors**

- **`^`**: Matches the start of a string.
- **`$`**: Matches the end of a string.

Examples:

```regex
^hello
```
Matches: "hello" at the start of the string.

```regex
world$
```
Matches: "world" at the end of the string.

### **Lookahead and Lookbehind**

- **Positive Lookahead (`?=`)**: Ensures a pattern is followed by another pattern.

  ```regex
  \d(?=abc)
  ```
  Matches: "1" in "1abc".

- **Negative Lookahead (`?!`)**: Ensures a pattern is not followed by another pattern.

  ```regex
  \d(?!abc)
  ```

  Matches: "1" in "1xyz".

- **Positive Lookbehind (`?<=`)**: Ensures a pattern is preceded by another pattern.

  ```regex
  (?<=abc)\d
  ```

  Matches: "1" in "abc1".

- **Negative Lookbehind (`?<!`)**: Ensures a pattern is not preceded by another pattern.

  ```regex
  (?<!abc)\d
  ```

  Matches: "1" in "xyz1".

<br>

## **Advanced Regex**

### **Flags**

Flags modify the behavior of a regex pattern:

- **`i`**: Case-insensitive matching.
- **`g`**: Global matching.
- **`m`**: Multiline matching.

Example:

```regex
hello
```

With the `i` flag, matches "hello" and "Hello".

### **Escape Sequences**

Escape metacharacters with a backslash (`\`):

```regex
\.
```

Matches: "." as a literal dot.

<br>

## **Resources**

- [Regex101 Online Tester](https://regex101.com)
- [Regular-Expressions.info](https://www.regular-expressions.info)
- [Regex Cheat Sheet](https://www.rexegg.com/regex-quickstart.html)

## **Contribution**

Your contributions can improve this guide:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b improve-mysql-guide
  ```

- Make your updates.

- Commit your changes:

  ```bash
  git commit -am 'Enhanced MySQL tutorial'
  ```

- Push to the branch:

  ```bash
  git push origin improve-mysql-guide
  ```

- Create a Pull Request targeting the Notes directory.

<br>

## **Date of Latest Revision**

- 12/10/2024

<br>

## **License**

- This guide is provided as-is without warranties. Use it responsibly and ensure you comply with legal and ethical guidelines.

- This project is licensed under the MIT License. See the LICENSE file for details.
