<img src="../assets/github-logo.png" alt="Alt Text" width="400">

# GitHub Authentication Methods

Learn how to authenticate to GitHub using different methods such as Personal Access Tokens and SSH keys for secure and efficient interactions with your GitHub repositories.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Using a Personal Access Token](#using-a-personal-access-token)
  - [Using SSH (Alternative Method)](#using-ssh-alternative-method)
  - [Setting Up Credential Helper](#setting-up-credential-helper)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

GitHub offers several authentication methods to ensure secure and seamless interactions with repositories. This tutorial covers using **Personal Access Tokens (PATs)** and **SSH keys**, both of which are recommended over the traditional username and password method, especially for private repositories and automation.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand how to create and use **Personal Access Tokens** for GitHub authentication.
- Learn how to generate and set up **SSH keys** for GitHub authentication.
- Know how to configure Git to use a **credential helper** for easier authentication.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a GitHub account.
- Git installed on your system.
- Familiarity with the command line.

<br>

## **Steps**

### **Using a Personal Access Token**

#### **Creating a Personal Access Token on GitHub**

1. **Navigate to GitHub Account Settings**
   - Open your GitHub account settings.

2. **Developer Settings**
   - Click on "Developer settings" and then "Personal access tokens."

3. **Generate New Token**
   - Click on "Generate new token" and select the necessary permissions (at least `repo` for private repositories).

4. **Copy and Secure Your Token**
   - Copy the generated token and store it in a secure location. Note: It won’t be shown again after this step.

#### **Using Your Token**

- When prompted for a username and password while pushing to GitHub, use your **GitHub username** as the username and the **Personal Access Token** as the password.

<br>

### **Using SSH (Alternative Method)**

#### **Step 1: Generate an SSH Key**

1. **Open Terminal**
   - Launch your terminal application.

2. **Generate SSH Key**
   - Run `ssh-keygen` and follow the prompts.
   - Save the SSH key to the default location (`~/.ssh/id_rsa`).
   - Optionally, set a passphrase for added security.

#### **Step 2: Add Your SSH Key to the SSH-Agent**

1. **Start SSH-Agent**
   - Run `eval "$(ssh-agent -s)"` to start the SSH agent.

2. **Add SSH Key**
   - Add your SSH private key to the agent by running: `ssh-add ~/.ssh/id_rsa`.

#### **Step 3: Add the SSH Key to Your GitHub Account**

1. **Copy SSH Key**
   - On macOS, run `cat ~/.ssh/id_rsa.pub | pbcopy` to copy the key to your clipboard. On Linux, use `xclip -selection clipboard < ~/.ssh/id_rsa.pub`.

2. **Add Key to GitHub**
   - Navigate to GitHub Settings → SSH and GPG keys → New SSH key.
   - Paste the SSH key and save.

#### **Step 4: Switch to SSH on Your Repository**

1. **Change Repository’s Remote URL**
   - Update your repository's remote URL to use SSH with the following command:

     ```bash
     git remote set-url origin git@github.com:username/repository.git
     ```

   Replace `username` and `repository` with your own details.

<br>

### **Setting Up Credential Helper**

#### **Configuring Git to Use Credential Helper**

1. **Enable Credential Helper**
   - Run the following command to enable Git’s credential helper:

     ```bash
     git config --global credential.helper cache
     ```

#### **Extending Cache Timeout**

1. **Set Custom Timeout**
   - To increase the timeout duration (default is 15 minutes), use:

     ```bash
     git config --global credential.helper 'cache --timeout=3600'
     ```

   This sets the timeout to one hour.

#### **Using Credential Helper**

- Credentials will be stored temporarily in memory for the duration of the cache timeout, making future pushes and pulls smoother without needing to re-enter them.

#### **For Permanent Storage**

1. **Store Credentials Permanently**
   - If you'd prefer to store credentials indefinitely (not recommended for shared machines), use:

     ```bash
     git config --global credential.helper store
     ```

   This stores credentials in a plaintext file on your system.

<br>

## **Examples**

Here’s a common use case for setting up GitHub authentication:

1. **Create a Personal Access Token** as described in the tutorial.
2. **Clone a Repository** using the token for authentication:

   ```bash
   git clone https://github.com/username/repository.git
   ```

3. **Push Changes** to GitHub using the token as the password:

   ```bash
   git push origin main
   ```

<br>

## **Notes**

- **Pro Tip**: SSH keys are more secure than using a Personal Access Token in some cases, especially when automating tasks.
- **Warning**: Using the credential store method for permanent storage on shared machines may expose your credentials.

<br>

## **Resources**

- [GitHub Personal Access Tokens](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token)
- [GitHub SSH Key Setup](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
- [Git Credential Helpers](https://git-scm.com/docs/git-credential)

<br>

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.
- Commit your changes:

  ```bash
  git commit -am 'Added some awesome features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the tutorial.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This tutorial is provided as-is without any warranties. Users are advised to review and understand the content before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
