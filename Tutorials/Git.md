# Basic Git Commands

Learn the fundamentals of Git, a powerful version control system used for tracking changes, collaborating with others, and managing code repositories effectively.

<!-- --- -->
<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Initialization Commands](#initialization-commands)
  - [Staging and Committing](#staging-and-committing)
  - [Branching and Merging](#branching-and-merging)
  - [Viewing Changes and Logs](#viewing-changes-and-logs)
  - [Remote Repository Commands](#remote-repository-commands)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Author](#author)


<br>

## **Overview**

Git is an open-source version control system designed to handle everything from small to very large projects with speed and efficiency. It is essential for collaborative software development and personal project management.


<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand basic Git commands and their use cases.
- Be able to initialize, clone, commit, branch, and merge repositories.
- Learn how to work with remote repositories using Git.


<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have Git installed on your computer. [Download Git here](https://git-scm.com/downloads).
- Basic familiarity with the command line.
- A GitHub or similar account for remote repository management (optional but recommended).


<br>

## **Steps**

### **Initialization Commands**

| Command               | Description                                                                                   | Example                                       |
|-----------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------|
| `git init`            | Initializes a new Git repository in the current directory.                                    | `git init`                                    |
| `git clone [url]`     | Clones an existing Git repository from the specified URL.                                     | `git clone https://github.com/user/repo.git`  |



### **Staging and Committing**

| Command                     | Description                                                                                       | Example                                         |
|-----------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------|
| `git add [file or dir]`     | Adds files or changes to the staging area. Use `git add .` to stage everything.                  | `git add file.txt`                             |
| `git commit -m "[message]"` | Records changes with a commit message describing the updates.                                    | `git commit -m "Fixed bug in data processing"`|
| `git status`                | Displays the state of the working directory and staging area.                                    | `git status`                                   |



### **Branching and Merging**

| Command                    | Description                                                                                         | Example               |
|----------------------------|-----------------------------------------------------------------------------------------------------|-----------------------|
| `git branch`               | Lists all branches or creates a new branch when a branch name is specified.                        | `git branch feature`  |
| `git checkout [branch]`    | Switches to the specified branch and updates the working directory.                                | `git checkout main`   |
| `git merge [branch]`       | Merges the specified branch into the current branch.                                               | `git merge feature`   |



### **Viewing Changes and Logs**

| Command          | Description                                              | Example        |
|-------------------|----------------------------------------------------------|----------------|
| `git log`        | Shows the commit history.                                | `git log`      |
| `git diff`       | Displays file differences not yet staged.                | `git diff`     |



### **Remote Repository Commands**

| Command                      | Description                                                                                    | Example                           |
|------------------------------|------------------------------------------------------------------------------------------------|-----------------------------------|
| `git push [remote] [branch]` | Pushes local changes to a remote repository.                                                  | `git push origin main`            |
| `git pull`                   | Fetches and merges changes from a remote repository.                                          | `git pull`                        |
| `git reset [file]`           | Removes a file from the staging area without altering its contents in the working directory.   | `git reset file.txt`              |
| `git revert [commit]`        | Creates a new commit that undoes the changes introduced in a specific commit.                 | `git revert a1b2c3d`              |


<br>

## **Examples**

Here’s an example of a common workflow:

1. Initialize a repository:

   ```bash
   git init
   ```

2. Add files to staging:

   ```bash
   git add .
   ```

3. Commit changes:

   ```bash
   git commit -m "Initial commit"
   ```

4. Push changes to a remote repository:

   ```bash
   git push origin main
   ```


<br>

## **Notes**

- **Pro Tip**: Use descriptive commit messages to maintain an understandable history.
- **Warning**: Be cautious with `git reset` and `git revert`, as they can alter the repository state significantly.
- Use `git status` often to stay aware of changes in your working directory.


<br>

## **Resources**

- [Official Git Documentation](https://git-scm.com/doc)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [GitHub Tutorials](https://docs.github.com/en/get-started)


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



<!-- ## Basic Git Commands

Git is a widely-used version control system that allows multiple people to work on the same codebase. It helps in tracking changes, collaborating with others, and reverting to previous states if necessary. Here are some fundamental Git commands:

- **`git init`**: Initializes a new Git repository. This command creates a new `.git` directory in your project, turning the current directory into a Git repository.

- **`git clone [url]`**: Creates a copy of an existing Git repository. The URL is the location of the Git repository you want to clone. E.g., `git clone https://github.com/user/repo.git`.

- **`git add [file or directory]`**: Adds files or changes in a directory to the staging area. It tells Git that you want to include updates to these files in the next commit. To add everything, use `git add .`.

- **`git commit -m "[commit message]"`**: Records or snapshots the file permanently in the version history along with a message describing the change. E.g., `git commit -m "Fixed bug in data processing"`.

- **`git status`**: Displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.

- **`git push [remote-name] [branch-name]`**: Pushes the changes in your local repository up to the remote repository you specify. E.g., `git push origin master`.

- **`git pull`**: Fetches and merges changes from the remote server to your working directory.

- **`git branch`**: Lists all the branches in your repo. Adding a branch name, like `git branch [branch-name]`, creates a new branch.

- **`git checkout [branch-name]`**: Switches to the specified branch and updates the working directory.

- **`git merge [branch]`**: Merges the specified branch’s history into the current branch.

- **`git log`**: Shows the commit logs.

- **`git diff`**: Shows the file differences not yet staged.

- **`git reset [file]`**: Unstages the file, but it preserves the file contents.

- **`git revert [commit]`**: Generates a new commit that undoes all of the changes introduced in `[commit]`, then applies it to the current branch. -->
