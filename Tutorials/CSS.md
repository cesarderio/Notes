<img src="../assets/css3.png" alt="Alt Text" width="400">


# CSS Tutorial

CSS (Cascading Style Sheets) is a stylesheet language used to control the presentation of HTML elements. It enables you to add styles like colors, fonts, layouts, and animations to your web pages.

<br>

### **Table of Contents**

- [Overview](#overview)
- [CSS Basics](#css-basics)
  - [What is CSS?](#what-is-css)
  - [How to Include CSS](#how-to-include-css)
  - [CSS Syntax](#css-syntax)
- [Selectors and Properties](#selectors-and-properties)
  - [Types of Selectors](#types-of-selectors)
  - [Common Properties](#common-properties)
- [Working with Colors](#working-with-colors)
  - [Color Types](#color-types)
  - [Background Colors](#background-colors)
- [Text and Font Styling](#text-and-font-styling)
  - [Text Properties](#text-properties)
  - [Font Properties](#font-properties)
- [Box Model](#box-model)
  - [Understanding the Box Model](#understanding-the-box-model)
  - [Padding, Margin, and Border](#padding-margin-and-border)
- [CSS Layouts](#css-layouts)
  - [Flexbox](#flexbox)
  - [Grid](#grid)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

CSS is used to style and format the visual appearance of HTML documents. It enhances the user experience by making web pages more visually appealing and easier to navigate.

<br>

## **CSS Basics**

### **What is CSS?**

CSS is a stylesheet language that separates content (HTML) from presentation. It allows you to apply styles like colors, fonts, and layouts to HTML elements.

### **How to Include CSS**

CSS can be added to HTML documents in three ways:

1. **Inline CSS**:

   ```html
   <p style="color: red;">This is a paragraph.</p>
   ```

2. **Internal CSS** (in `<style>` tags):

   ```html
   <style>
       p {
           color: red;
       }
   </style>
   ```

3. **External CSS** (in a separate file):

   ```html
   <link rel="stylesheet" href="styles.css">
   ```

### **CSS Syntax**

CSS is written using rules consisting of selectors and declarations:

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
    font-size: 24px;
}
```

<br>

## **Selectors and Properties**

### **Types of Selectors**

- **Element Selector**: Targets specific HTML elements.

  ```css
  p {
      color: green;
  }
  ```

- **Class Selector**: Targets elements with a specific class.

  ```css
  .example {
      font-style: italic;
  }
  ```

- **ID Selector**: Targets an element with a specific ID.

  ```css
  #unique {
      text-align: center;
  }
  ```

### **Common Properties**

- **Color**: Sets text color.
- **Background-color**: Sets background color.
- **Font-size**: Controls text size.
- **Margin**: Controls space outside elements.
- **Padding**: Controls space inside elements.

<br>

## **Working with Colors**

### **Color Types**

- **Named Colors**:

  ```css
  color: red;
  ```

- **Hexadecimal Colors**:

  ```css
  color: #ff0000;
  ```

- **RGB Colors**:

  ```css
  color: rgb(255, 0, 0);
  ```

### **Background Colors**

- Apply background colors to elements:

  ```css
  body {
      background-color: #f0f0f0;
  }
  ```

<br>

## **Text and Font Styling**

### **Text Properties**

- **Text Alignment**:

  ```css
  text-align: center;
  ```

- **Text Decoration**:

  ```css
  text-decoration: underline;
  ```

### **Font Properties**

- **Font Family**:

  ```css
  font-family: Arial, sans-serif;
  ```

- **Font Weight**:

  ```css
  font-weight: bold;
  ```

<br>

## **Box Model**

### **Understanding the Box Model**

The box model consists of:

1. **Content**: The actual content of the box.
2. **Padding**: Space between the content and the border.
3. **Border**: The edge around the padding.
4. **Margin**: Space outside the border.

### **Padding, Margin, and Border**

Example:

```css
div {
    margin: 10px;
    padding: 15px;
    border: 2px solid black;
}
```

<br>

## **CSS Layouts**

### **Flexbox**

Flexbox is used for responsive layouts:

```css
display: flex;
justify-content: center;
align-items: center;
```

### **Grid**

CSS Grid is a powerful layout system:

```css
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 10px;
```

<br>

## **Resources**

- [MDN CSS Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/)
- [CSS-Tricks](https://css-tricks.com/)

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
