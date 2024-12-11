# PowerShell Tutorial

PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework. This guide will provide you with the fundamentals of PowerShell to help you get started.

<br>

### **Table of Contents**

- [Overview](#overview)
- [PowerShell Basics](#powershell-basics)
  - [What is PowerShell?](#what-is-powershell)
  - [How to Install PowerShell](#how-to-install-powershell)
  - [Opening PowerShell](#opening-powershell)
- [Basic Commands](#basic-commands)
  - [Getting Help](#getting-help)
  - [Common Cmdlets](#common-cmdlets)
- [Working with Files and Directories](#working-with-files-and-directories)
  - [Navigating Directories](#navigating-directories)
  - [File Operations](#file-operations)
- [Using Variables and Data Types](#using-variables-and-data-types)
- [Creating and Running Scripts](#creating-and-running-scripts)
  - [Writing a Script](#writing-a-script)
  - [Running a Script](#running-a-script)
- [Advanced Topics](#advanced-topics)
  - [Pipelines](#pipelines)
  - [Working with Objects](#working-with-objects)
  - [Error Handling](#error-handling)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

PowerShell is a powerful tool for task automation and configuration management. It is used widely by system administrators, developers, and IT professionals to manage systems and automate tasks efficiently.

<br>

## **PowerShell Basics**

### **What is PowerShell?**

PowerShell is a task automation framework consisting of a command-line shell and a scripting language built on .NET. It provides tools to manage computers, applications, and network configurations.

### **How to Install PowerShell**

- **Windows**: PowerShell is pre-installed on most Windows systems. For the latest version, download it from the [official PowerShell GitHub page](https://github.com/PowerShell/PowerShell).
- **Linux**: Install PowerShell using your package manager:

  ```bash
  sudo apt install -y powershell # Debian/Ubuntu
  sudo dnf install -y powershell # Fedora
  ```

- **macOS**: Install PowerShell using Homebrew:

  ```bash
  brew install --cask powershell
  ```

### **Opening PowerShell**

- **Windows**: Search for "PowerShell" in the Start Menu or use `Win + X` and select "Windows PowerShell."
- **Linux/macOS**: Open a terminal and type `pwsh`.

<br>

## **Basic Commands**

### **Getting Help**

Use the `Get-Help` cmdlet to learn about commands and their usage:

```powershell
Get-Help Get-Command
```

Update help files to get the latest documentation:

```powershell
Update-Help
```

### **Common Cmdlets**

- List all available cmdlets:

  ```powershell
  Get-Command
  ```

- Get details about a specific cmdlet:

  ```powershell
  Get-Help <cmdlet-name>
  ```

- Examples of commonly used cmdlets:

  ```powershell
  Get-Process    # List running processes
  Get-Service    # List services
  Get-EventLog   # View system logs
  ```

<br>

## **Working with Files and Directories**

### **Navigating Directories**

- **Change Directory**:

  ```powershell
  Set-Location <path>
  ```

- **List Files and Folders**:

  ```powershell
  Get-ChildItem
  ```

- **Get Current Directory**:

  ```powershell
  Get-Location
  ```

### **File Operations**

- **Create a File**:

  ```powershell
  New-Item -Path <filename> -ItemType File
  ```

- **Copy a File**:

  ```powershell
  Copy-Item -Path <source> -Destination <destination>
  ```

- **Delete a File**:

  ```powershell
  Remove-Item -Path <filename>
  ```

<br>

## **Using Variables and Data Types**

- **Creating Variables**:

  ```powershell
  $myVariable = "Hello, PowerShell!"
  ```

- **View Variable Value**:

  ```powershell
  Write-Output $myVariable
  ```

- **Common Data Types**:

  ```powershell
  [int]$number = 10
  [string]$text = "Sample Text"
  [array]$list = @(1, 2, 3)
  ```

<br>

## **Creating and Running Scripts**

### **Writing a Script**

1. Open a text editor (e.g., Notepad or VS Code).
2. Write your PowerShell commands.
3. Save the file with a `.ps1` extension.

Example script (`example.ps1`):

```powershell
Write-Output "Hello, PowerShell!"
```

### **Running a Script**

Run the script in PowerShell:

```powershell
./example.ps1
```

Ensure script execution is enabled:

```powershell
Set-ExecutionPolicy RemoteSigned
```

<br>

## **Advanced Topics**

### **Pipelines**

Pass output from one command as input to another:

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

### **Working with Objects**

PowerShell uses objects instead of plain text. Access properties and methods:

```powershell
$service = Get-Service -Name "Spooler"
$service.Status
```

### **Error Handling**

Use `try`, `catch`, and `finally` blocks to handle errors:

```powershell
try {
    Get-Item -Path "C:\nonexistentfile"
} catch {
    Write-Output "An error occurred: $_"
} finally {
    Write-Output "Cleanup actions."
}
```

<br>

## **Resources**

- [PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/)
- [PowerShell GitHub Repository](https://github.com/PowerShell/PowerShell)
- [SS64 PowerShell Reference](https://ss64.com/ps/)

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

