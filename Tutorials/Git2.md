# Basic Git Commands

Git is a widely-used version control system that helps track changes, collaborate with others, and revert to previous states. Below are fundamental Git commands and their uses.

### Table of Contents

- [Initialization Commands](#initialization-commands)
- [Staging and Committing](#staging-and-committing)
- [Branching and Merging](#branching-and-merging)
- [Viewing Changes and Logs](#viewing-changes-and-logs)
- [Remote Repository Commands](#remote-repository-commands)

---

## Initialization Commands

| Command               | Description                                                                                   | Example                                       |
|-----------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------|
| `git init`            | Initializes a new Git repository in the current directory.                                    | `git init`                                    |
| `git clone [url]`     | Clones an existing Git repository from the specified URL.                                     | `git clone https://github.com/user/repo.git`  |

---

## Staging and Committing

| Command                     | Description                                                                                       | Example                                         |
|-----------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------|
| `git add [file or dir]`     | Adds files or changes to the staging area. Use `git add .` to stage everything.                  | `git add file.txt`                             |
| `git commit -m "[message]"` | Records changes with a commit message describing the updates.                                    | `git commit -m "Fixed bug in data processing"`|
| `git status`                | Displays the state of the working directory and staging area.                                    | `git status`                                   |

---

## Branching and Merging

| Command                    | Description                                                                                         | Example               |
|----------------------------|-----------------------------------------------------------------------------------------------------|-----------------------|
| `git branch`               | Lists all branches or creates a new branch when a branch name is specified.                        | `git branch feature`  |
| `git checkout [branch]`    | Switches to the specified branch and updates the working directory.                                | `git checkout main`   |
| `git merge [branch]`       | Merges the specified branch into the current branch.                                               | `git merge feature`   |

---

## Viewing Changes and Logs

| Command          | Description                                              | Example        |
|-------------------|----------------------------------------------------------|----------------|
| `git log`        | Shows the commit history.                                | `git log`      |
| `git diff`       | Displays file differences not yet staged.                | `git diff`     |

---

## Remote Repository Commands

| Command                      | Description                                                                                    | Example                           |
|------------------------------|------------------------------------------------------------------------------------------------|-----------------------------------|
| `git push [remote] [branch]` | Pushes local changes to a remote repository.                                                  | `git push origin main`            |
| `git pull`                   | Fetches and merges changes from a remote repository.                                          | `git pull`                        |
| `git reset [file]`           | Removes a file from the staging area without altering its contents in the working directory.   | `git reset file.txt`              |
| `git revert [commit]`        | Creates a new commit that undoes the changes introduced in a specific commit.                 | `git revert a1b2c3d`              |

---

## Notes

> **Pro Tip**: Always use meaningful commit messages to make your Git history more understandable.
>
> **Warning**: Be cautious with `git reset` and `git revert` as they can significantly alter your repository state.

---
