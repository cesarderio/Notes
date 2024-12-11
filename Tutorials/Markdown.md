# Markdown Tutorial

Markdown is a lightweight markup language that allows you to format plain text for the web. It’s commonly used for documentation, blogging, and readme files due to its simplicity and readability.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Markdown](#getting-started-with-markdown)
  - [What is Markdown?](#what-is-markdown)
  - [How to Use Markdown](#how-to-use-markdown)
- [Basic Syntax](#basic-syntax)
  - [Headings](#headings)
  - [Paragraphs and Line Breaks](#paragraphs-and-line-breaks)
  - [Emphasis](#emphasis)
- [Lists](#lists)
  - [Ordered Lists](#ordered-lists)
  - [Unordered Lists](#unordered-lists)
- [Links and Images](#links-and-images)
  - [Adding Links](#adding-links)
  - [Adding Images](#adding-images)
- [Code and Quotes](#code-and-quotes)
  - [Inline Code](#inline-code)
  - [Code Blocks](#code-blocks)
  - [Block Quotes](#block-quotes)
- [Tables](#tables)
- [Advanced Markdown](#advanced-markdown)
  - [Task Lists](#task-lists)
  - [Footnotes](#footnotes)
  - [HTML in Markdown](#html-in-markdown)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Markdown provides a simple way to add formatting to plain text. It’s widely used for creating formatted text that’s easy to read and write without complex tools.

<br>

## **Getting Started with Markdown**

### **What is Markdown?**

Markdown is a plain text formatting syntax designed for writing content for the web. It’s often used for creating blog posts, documentation, and GitHub README files.

### **How to Use Markdown**

You can write Markdown using any text editor. Files are typically saved with a `.md` or `.markdown` extension. To preview or render Markdown, use:

- Markdown preview features in IDEs (e.g., VS Code).
- Online tools like [Dillinger](https://dillinger.io/).

<br>

## **Basic Syntax**

### **Headings**

Headings are created using `#` symbols:

```markdown
# Heading 1
## Heading 2
### Heading 3
```

Output:

# Heading 1
## Heading 2
### Heading 3

<br>

### **Paragraphs and Line Breaks**

Create paragraphs by leaving a blank line between blocks of text. Use two spaces at the end of a line for a line break.

```markdown
This is a paragraph.

This is another paragraph.
```

<br>

### **Emphasis**

- *Italic*: Wrap text in `*` or `_`:

  ```markdown
  *italic text*
  _italic text_
  ```

- **Bold**: Wrap text in `**` or `__`:

  ```markdown
  **bold text**
  __bold text__
  ```

- ***Bold and Italic***: Combine symbols:

  ```markdown
  ***bold and italic***
  ```

<br>

## **Lists**

### **Ordered Lists**

Use numbers followed by periods:

```markdown
1. First item
2. Second item
3. Third item
```

Output:

1. First item
2. Second item
3. Third item

### **Unordered Lists**

Use `*`, `-`, or `+`:

```markdown
- Item one
- Item two
- Item three
```

Output:

- Item one
- Item two
- Item three

<br>

## **Links and Images**

### **Adding Links**

Format links with `[text](URL)`:

```markdown
[Markdown Guide](https://www.markdownguide.org)
```

Output:

[Markdown Guide](https://www.markdownguide.org)

### **Adding Images**

Use `![alt text](image URL)`:

```markdown
![Markdown Logo](https://www.markdownguide.org/assets/images/tux.png)
```

Output:

![Markdown Logo](https://www.markdownguide.org/assets/images/tux.png)

<br>

## **Code and Quotes**

### **Inline Code**

Wrap code in backticks:

```markdown
Use `code` for inline code.
```

Output:

Use `code` for inline code.

### **Code Blocks**

Use triple backticks for multi-line code:

```markdown
```
function greet() {
    console.log("Hello, Markdown!");
}
```
```

Output:

```javascript
function greet() {
    console.log("Hello, Markdown!");
}
```

### **Block Quotes**

Start a line with `>`:

```markdown
> This is a block quote.
```

Output:

> This is a block quote.

<br>

## **Tables**

Use pipes (`|`) and dashes (`-`) to create tables:

```markdown
| Header 1 | Header 2 |
|----------|----------|
| Row 1    | Data     |
| Row 2    | Data     |
```

Output:

| Header 1 | Header 2 |
|----------|----------|
| Row 1    | Data     |
| Row 2    | Data     |

<br>

## **Advanced Markdown**

### **Task Lists**

Use `- [ ]` for unchecked and `- [x]` for checked items:

```markdown
- [x] Completed task
- [ ] Incomplete task
```

Output:

- [x] Completed task
- [ ] Incomplete task

### **Footnotes**

Add footnotes with `[^1]`:

```markdown
This is a sentence with a footnote.[^1]

[^1]: This is the footnote.
```

### **HTML in Markdown**

Include HTML for advanced formatting:

```markdown
<div style="color: red;">This is red text.</div>
```

Output:

<div style="color: red;">This is red text.</div>

<br>

## **Resources**

- [Markdown Guide](https://www.markdownguide.org)
- [Dillinger Online Markdown Editor](https://dillinger.io)
- [CommonMark Specification](https://commonmark.org/)

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
