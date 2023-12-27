# Setting Up SSH Key for GitHub on Ubuntu

In this guide, you'll learn how to generate an SSH key and add it to your GitHub account for secure authentication.

## Step 1: Generate an SSH Key

Open your terminal and follow these steps:

1. Generate a new SSH key pair by running the following command:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   Replace `"your_email@example.com"` with your GitHub-associated email address.

2. Press Enter to accept the default file location (`/home/your_username/.ssh/id_rsa`) or provide a custom one if desired.

3. Optionally, set a passphrase for added security or leave it empty for convenience.

## Step 2: Add SSH Key to SSH Agent

1. Start the SSH agent by running:
   ```bash
   eval "$(ssh-agent -s)"
   ```

2. Add your SSH key to the agent:
   ```bash
   ssh-add ~/.ssh/id_rsa
   ```

## Step 3: Copy the SSH Public Key

1. Copy the contents of your SSH public key to the clipboard using:
   ```bash
   xclip -sel clip < ~/.ssh/id_rsa.pub
   ```

## Step 4: Add SSH Key to Your GitHub Account

1. Log in to your GitHub account.

2. Click on your profile picture in the top right corner and select "Settings."

3. In the left sidebar, click on "SSH and GPG keys."

4. Click the "New SSH key" button.

5. Give your key a title (e.g., "Ubuntu SSH Key") and paste the public key you copied in Step 3 into the "Key" field.

6. Click the "Add SSH key" button.

## Step 5: Test the SSH Connection

To ensure that your SSH key is properly configured, run the following command in your terminal:

```bash
ssh -T git@github.com
```

You should see a message indicating that you've successfully authenticated.

## Step 6: Clone a GitHub Repository

Now you can clone a GitHub repository using SSH:

```bash
git clone git@github.com:username/repo.git
```

Replace `username` with your GitHub username and `repo` with the name of the repository you want to clone.

You have successfully set up an SSH key for GitHub on your Ubuntu system.

Happy coding!
