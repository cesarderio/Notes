# Setting Up SSH Key for GitHub on Ubuntu

In this guide, you'll learn how to generate an SSH key and add it to your GitHub account for secure authentication.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Generate an SSH Key](#generate-an-ssh-key)
  - [Add SSH Key to SSH Agent](#add-ssh-key-to-ssh-agent)
  - [Copy the SSH Public Key](#copy-the-ssh-public-key)
  - [Add SSH Key to Your GitHub Account](#add-ssh-key-to-your-github-account)
  - [Test the SSH Connection](#test-the-ssh-connection)
  - [Clone a GitHub Repository](#clone-a-github-repository)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

This tutorial walks you through setting up an SSH key on Ubuntu and connecting it to your GitHub account. Using SSH keys enhances security and eliminates the need to enter your password for each interaction with GitHub.

<br>

## **Objectives**

- Understand the process of generating and adding an SSH key to GitHub.
- Learn how to configure SSH for secure interactions with GitHub repositories.
- Test the connection to ensure proper setup.

<br>

## **Prerequisites**

- An Ubuntu system with terminal access.
- A GitHub account.
- Basic understanding of terminal commands.

<br>

## **Steps**

### **Generate an SSH Key**

1. Open your terminal and run the following command:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   Replace `"your_email@example.com"` with your GitHub-associated email address.

2. Press Enter to accept the default file location (`/home/your_username/.ssh/id_rsa`) or specify a custom one.

3. Optionally, set a passphrase for added security or leave it empty for convenience.

<br>

### **Add SSH Key to SSH Agent**

1. Start the SSH agent by running:

   ```bash
   eval "$(ssh-agent -s)"
   ```

2. Add your SSH key to the agent:

   ```bash
   ssh-add ~/.ssh/id_rsa
   ```

<br>

### **Copy the SSH Public Key**

1. Copy the contents of your SSH public key to the clipboard:

   ```bash
   xclip -sel clip < ~/.ssh/id_rsa.pub
   ```

   If `xclip` is not installed, you can manually copy the key using:

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

<br>

### **Add SSH Key to Your GitHub Account**

1. Log in to your GitHub account.

2. Click on your profile picture in the top right corner and select **Settings**.

3. In the left sidebar, click on **SSH and GPG keys**.

4. Click the **New SSH key** button.

5. Give your key a title (e.g., "Ubuntu SSH Key") and paste the public key copied in Step 3 into the "Key" field.

6. Click the **Add SSH key** button.

<br>

### **Test the SSH Connection**

To verify that your SSH key is properly configured, run the following command:

```bash
ssh -T git@github.com
```

You should see a message indicating successful authentication, such as:

```text
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

<br>

### **Clone a GitHub Repository**

Now you can clone a GitHub repository using SSH:

```bash
git clone git@github.com:username/repo.git
```

Replace `username` with your GitHub username and `repo` with the name of the repository you want to clone.

<br>

## **Examples**

- Example command to list all configured SSH keys:

  ```bash
  ls -al ~/.ssh
  ```

- Example of resetting a passphrase for an existing key:

  ```bash
  ssh-keygen -p -f ~/.ssh/id_rsa
  ```

<br>

## **Notes**

- Ensure your SSH agent is running whenever you interact with GitHub repositories.
- If you encounter issues, verify the public key on your GitHub account matches the key on your system.

<br>

## **Resources**

- [GitHub SSH Key Documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- [Ubuntu SSH Key Management](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)

<br>

## **Contribution**

Contributions to this guide are welcome! Submit issues or pull requests on the repository hosting this tutorial to suggest improvements or additional tips.

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
