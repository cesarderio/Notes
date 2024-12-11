<img src="../assets/html.png" alt="Alt Text" width="400">

# HTML Tutorial

HTML (HyperText Markup Language) is the standard language for creating web pages. It provides the structure of a webpage, allowing you to format text, embed media, and create links.

<br>

### **Table of Contents**

- [Overview](#overview)
- [HTML Basics](#html-basics)
  - [HTML Structure](#html-structure)
  - [Common HTML Tags](#common-html-tags)
- [Formatting Text in HTML](#formatting-text-in-html)
  - [Headings](#headings)
  - [Paragraphs and Line Breaks](#paragraphs-and-line-breaks)
  - [Text Styling](#text-styling)
- [Links and Images](#links-and-images)
  - [Hyperlinks](#hyperlinks)
  - [Images](#images)
- [Lists in HTML](#lists-in-html)
  - [Ordered Lists](#ordered-lists)
  - [Unordered Lists](#unordered-lists)
- [Tables in HTML](#tables-in-html)
  - [Basic Table Structure](#basic-table-structure)
- [Forms in HTML](#forms-in-html)
  - [Input Elements](#input-elements)
  - [Form Attributes](#form-attributes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

HTML is the backbone of all websites. It is used to define the structure and layout of a webpage, ensuring that content is organized and displayed properly in web browsers.

<br>

## **HTML Basics**

### **HTML Structure**

Every HTML document has a basic structure consisting of elements enclosed in tags:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>
    <h1>Welcome to HTML</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```

- **`<!DOCTYPE html>`**: Declares the document type.
- **`<html>`**: Root element of the HTML document.
- **`<head>`**: Contains metadata and links to external resources.
- **`<body>`**: Contains the content displayed on the webpage.

<br>

### **Common HTML Tags**

- **`<h1>` to `<h6>`**: Headings.
- **`<p>`**: Paragraphs.
- **`<a>`**: Links.
- **`<img>`**: Images.
- **`<ul>` / `<ol>`**: Lists.
- **`<table>`**: Tables.

<br>

## **Formatting Text in HTML**

### **Headings**

Headings define the structure of your webpage and range from `<h1>` (largest) to `<h6>` (smallest):

```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Smaller Subheading</h3>
```

<br>

### **Paragraphs and Line Breaks**

- **Paragraphs**:

  ```html
  <p>This is a paragraph.</p>
  ```

- **Line Breaks**:

  ```html
  This is a line.<br>This is another line.
  ```

<br>

### **Text Styling**

- **Bold**: `<strong>` or `<b>`

  ```html
  <strong>Important Text</strong>
  ```

- **Italic**: `<em>` or `<i>`

  ```html
  <em>Emphasized Text</em>
  ```

- **Underline**: `<u>`

  ```html
  <u>Underlined Text</u>
  ```

<br>

## **Links and Images**

### **Hyperlinks**

Create clickable links using the `<a>` tag:

```html
<a href="https://www.example.com">Visit Example</a>
```

- **`href`**: Specifies the URL of the link.

<br>

### **Images**

Embed images using the `<img>` tag:

```html
<img src="image.jpg" alt="Description of Image">
```

- **`src`**: Path to the image file.
- **`alt`**: Alternative text for the image.

<br>

## **Lists in HTML**

### **Ordered Lists**

Use `<ol>` for numbered lists:

```html
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>
```

### **Unordered Lists**

Use `<ul>` for bullet-point lists:

```html
<ul>
    <li>Item one</li>
    <li>Item two</li>
</ul>
```

<br>

## **Tables in HTML**

### **Basic Table Structure**

Create tables using the `<table>` tag:

```html
<table>
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

- **`<tr>`**: Table row.
- **`<th>`**: Table header.
- **`<td>`**: Table data.

<br>

## **Forms in HTML**

### **Input Elements**

Forms collect user input using `<form>` and various input elements:

```html
<form action="submit.php" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">
    <input type="submit" value="Submit">
</form>
```

- **`action`**: URL to send the form data to.
- **`method`**: HTTP method (GET or POST).

<br>

### **Form Attributes**

- **`placeholder`**: Text displayed inside an input field before input.
- **`required`**: Ensures the field must be filled before submission.

<br>

## **Resources**

- [HTML Living Standard](https://html.spec.whatwg.org/)
- [Mozilla Developer Network (MDN) HTML Guide](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)

<br>

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
