<img src="../assets/github-logo.png" alt="Alt Text" width="400">

# GitHub Comprehensive Tutorial

GitHub is a platform that hosts software development and version control using Git. It provides a web-based graphical interface and offers all the distributed version control and source code management functionality of Git, plus its features.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Setting Up a GitHub Account](#setting-up-a-github-account)
- [Creating and Managing Repositories](#creating-and-managing-repositories)
  - [Creating a New Repository](#creating-a-new-repository)
  - [Cloning a Repository](#cloning-a-repository)
  - [Making Changes and Committing](#making-changes-and-committing)
- [Working with Branches](#working-with-branches)
  - [Create a New Branch](#create-a-new-branch)
  - [Merge Branches](#merge-branches)
- [Working with GitHub Organizations and Teams](#working-with-github-organizations-and-teams)
  - [Creating an Organization](#creating-an-organization)
  - [Managing Teams within Organizations](#managing-teams-within-organizations)
- [Collaborating on Projects](#collaborating-on-projects)
  - [Forking a Repository](#forking-a-repository)
  - [Submitting Pull Requests](#submitting-pull-requests)
  - [Reviewing Pull Requests](#reviewing-pull-requests)
- [Additional Features](#additional-features)
- [Conclusion](#conclusion)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

GitHub is an essential platform for hosting and managing Git repositories. It provides powerful version control features and simplifies collaboration on software projects, making it a staple for developers worldwide.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Know how to set up a GitHub account.
- Be able to create and manage repositories.
- Understand how to work with branches and make changes.
- Learn to collaborate with others on GitHub.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a GitHub account.
- Be familiar with Git and basic command-line operations.
- Have Git installed on your local machine.

<br>

## **Setting Up a GitHub Account**

1. **Sign Up**:
   - Visit [GitHub](https://github.com/) and sign up for a new account.
   - Enter a username, email address, and password.

2. **Verify Email**:
   - Check your email for a verification link from GitHub and verify your account.

3. **Configure Account Settings**:
   - Set up your profile by adding a profile picture, bio, and other personal information.

<br>

## **Creating and Managing Repositories**

### **Creating a New Repository**

1. **Navigate to the Repository Tab**:
   - Click on the "+" icon in the top right corner and select "New repository".

2. **Set Up the Repository**:
   - Enter a repository name, description, and choose between a public or private repository.
   - Initialize the repository with a README, .gitignore file, and choose a license if needed.

### **Cloning a Repository**

1. **Clone via Command Line**:
   - Find the "Clone or download" button in the repository.
   - Copy the URL provided.
   - Use the command `git clone [URL]` in your terminal or command prompt, where `[URL]` is the link you copied.

### **Making Changes and Committing**

1. **Edit Files**:
   - Make changes to the files in your local repository.

2. **Commit Changes**:
   - Stage the changes with `git add .`
   - Commit the changes with `git commit -m "Commit message"`

3. **Push Changes to GitHub**:
   - Push your changes using `git push origin master` (for the master branch).

<br>

## **Working with Branches**

### **Create a New Branch**

1. Use `git branch [branch-name]` to create a new branch.
2. Switch to your new branch with `git checkout [branch-name]`.

### **Merge Branches**

1. After making changes in your branch, merge it to the main branch using `git merge [branch-name]`.

<br>

## **Working with GitHub Organizations and Teams**

### **Creating an Organization**

1. **Set Up**:
   - On your GitHub dashboard, click on your profile picture and select "Your organizations" > "New organization".
   - Choose a plan and fill in the organization's name and billing email.

### **Managing Teams within Organizations**

1. **Create Teams**:
   - In the organization's dashboard, go to "Teams" and create a new team.
   - Add members and set permissions for the repositories they can access.

<br>

## **Collaborating on Projects**

### **Forking a Repository**

1. Click the "Fork" button in the repository to create a copy under your GitHub account.

### **Submitting Pull Requests**

1. After making changes in your fork, click on "Pull Request" in the original repository to submit your changes for review.

### **Reviewing Pull Requests**

1. Repository maintainers can review, comment, and merge pull requests.

<br>

## **Additional Features**

- **GitHub Actions**: Automate, customize, and execute software development workflows.
- **GitHub Pages**: Host your static websites directly from a GitHub repository.

<br>

## **Conclusion**

GitHub is a powerful tool for version control and collaboration in software development. By understanding its core functionalities, such as repositories, branches, organizations, and collaboration tools, you can effectively manage and contribute to software projects.

For more detailed information, visit the [GitHub Docs](https://docs.github.com/en).

<br>

## **Examples**

Here’s a common workflow for using GitHub:

1. **Create a New Repository:**

   ```bash
   git init
   ```

2. **Clone a Repository:**

   ```bash
   git clone https://github.com/username/repository.git
   ```

3. **Make Changes:**

   ```bash
   git add .
   git commit -m "Updated the README"
   git push origin master
   ```

<br>

## **Notes**

- **Tip**: Use `git status` frequently to keep track of your changes.
- **Warning**: Be cautious when merging branches, as conflicts may arise.

<br>

## **Resources**

- [Official GitHub Documentation](https://docs.github.com/en)
- [GitHub Learning Lab](https://lab.github.com/)
- [GitHub Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

<br>

## **Contribution**

We welcome contributions to improve this tutorial:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b improve-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -am 'Improved tutorial content'
  ```

- Push your changes:

  ```bash
  git push origin improve-tutorial
  ```

- Submit a Pull Request.

Your contributions will be highly appreciated!

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This tutorial is provided as-is without any warranties. Users are advised to review and understand the content before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
