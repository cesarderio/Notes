# Vim Tutorial

Vim (Vi IMproved) is a powerful text editor widely used for programming, system administration, and general text editing. Known for its efficiency, Vim can significantly speed up your workflow once mastered.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Vim](#getting-started-with-vim)
  - [What is Vim?](#what-is-vim)
  - [Installing Vim](#installing-vim)
  - [Starting Vim](#starting-vim)
- [Vim Basics](#vim-basics)
  - [Modes in Vim](#modes-in-vim)
  - [Basic Navigation](#basic-navigation)
- [Editing Text](#editing-text)
  - [Inserting Text](#inserting-text)
  - [Deleting Text](#deleting-text)
  - [Undo and Redo](#undo-and-redo)
- [Working with Files](#working-with-files)
  - [Opening and Saving Files](#opening-and-saving-files)
  - [Exiting Vim](#exiting-vim)
- [Search and Replace](#search-and-replace)
- [Advanced Features](#advanced-features)
  - [Using Buffers](#using-buffers)
  - [Splitting Windows](#splitting-windows)
  - [Customizing Vim](#customizing-vim)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Vim is a modal text editor that allows users to efficiently create and edit text files. With its steep learning curve and extensive feature set, Vim remains a favorite among power users and developers.

<br>

## **Getting Started with Vim**

### **What is Vim?**

Vim is an advanced text editor that builds on the capabilities of the Unix `vi` editor. It is highly configurable and offers powerful features for editing code, text, and configuration files.

### **Installing Vim**

- **Linux**: Most distributions include Vim. Install it using your package manager if it’s not available:

  ```bash
  sudo apt install vim       # Debian/Ubuntu
  sudo yum install vim       # CentOS/RHEL
  sudo pacman -S vim         # Arch Linux
  ```

- **macOS**: Install using Homebrew:

  ```bash
  brew install vim
  ```

- **Windows**: Download Vim from the [official website](https://www.vim.org/download.php).

### **Starting Vim**

Open a terminal and type:

```bash
vim filename
```

Replace `filename` with the name of the file you want to edit.

<br>

## **Vim Basics**

### **Modes in Vim**

Vim operates in multiple modes, each serving a different purpose:

- **Normal Mode**: Default mode for navigation and commands.
- **Insert Mode**: For inserting and editing text.
- **Visual Mode**: For selecting text.
- **Command-Line Mode**: For saving, quitting, and other commands (accessed with `:`).

### **Basic Navigation**

- **Move the Cursor**:

  - `h`: Left
  - `j`: Down
  - `k`: Up
  - `l`: Right

- **Word Navigation**:

  - `w`: Move to the next word.
  - `b`: Move to the beginning of the previous word.

- **Line Navigation**:

  - `0`: Move to the beginning of the line.
  - `^`: Move to the first non-whitespace character.
  - `$`: Move to the end of the line.

<br>

## **Editing Text**

### **Inserting Text**

- `i`: Insert before the cursor.
- `a`: Insert after the cursor.
- `o`: Insert a new line below the current line.

### **Deleting Text**

- `x`: Delete the character under the cursor.
- `dw`: Delete from the cursor to the end of the word.
- `dd`: Delete the entire line.

### **Undo and Redo**

- `u`: Undo the last change.
- `Ctrl-r`: Redo the undone change.

<br>

## **Working with Files**

### **Opening and Saving Files**

- Open a file:

  ```bash
  vim filename
  ```

- Save changes:

  ```bash
  :w
  ```

- Save and quit:

  ```bash
  :wq
  ```

- Save as a new file:

  ```bash
  :w new_filename
  ```

### **Exiting Vim**

- Quit without saving:

  ```bash
  :q!
  ```

<br>

## **Search and Replace**

- **Search**:

  ```bash
  /search_term
  ```

  Press `n` to find the next occurrence, `N` for the previous occurrence.

- **Search and Replace**:

  ```bash
  :%s/old_text/new_text/g
  ```

  This replaces all occurrences of `old_text` with `new_text` in the file.

<br>

## **Advanced Features**

### **Using Buffers**

Buffers allow you to edit multiple files simultaneously:

- Open a new file:

  ```bash
  :e filename
  ```

- Switch between buffers:

  ```bash
  :bnext  # Next buffer
  :bprev  # Previous buffer
  ```

### **Splitting Windows**

- Split the window horizontally:

  ```bash
  :split filename
  ```

- Split the window vertically:

  ```bash
  :vsplit filename
  ```

- Navigate between splits:

  - `Ctrl-w h`: Left split
  - `Ctrl-w l`: Right split
  - `Ctrl-w j`: Lower split
  - `Ctrl-w k`: Upper split

### **Customizing Vim**

- Edit the configuration file (`~/.vimrc`):

  ```bash
  set number       " Show line numbers
  syntax on        " Enable syntax highlighting
  ```

- Install plugins using a plugin manager like [Vundle](https://github.com/VundleVim/Vundle.vim).

<br>

## **Resources**

- [Vim Official Documentation](https://www.vim.org/docs.php)
- [Vim Cheat Sheet](https://vim.rtorr.com/)
- [Open Vim Interactive Tutorial](https://www.openvim.com/)

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
