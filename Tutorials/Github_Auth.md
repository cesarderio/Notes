# GitHub Authentication Methods Tutorial

## Using a Personal Access Token

### Creating a Personal Access Token on GitHub

1. **Navigate to GitHub Account Settings**
   - Access your GitHub settings.

2. **Developer Settings**
   - Click on "Developer settings" and then "Personal access tokens".

3. **Generate New Token**
   - Generate a new token ensuring you select the necessary permissions (at least `repo` for private repositories).

4. **Copy and Secure Your Token**
   - Copy the token and keep it in a safe place. It won't be shown again.

### Using Your Token

- When you push to GitHub and are prompted for your username and password, use your GitHub username and the personal access token as the password.

## Using SSH (Alternative Method)

### Step 1: Generate an SSH Key

1. **Open Terminal**
   - Start your terminal application.

2. **Generate SSH Key**
   - Run `ssh-keygen` and follow the prompts.
   - Save the key to the default location (`~/.ssh/id_rsa`).
   - Optionally, add a passphrase for security.

### Step 2: Add Your SSH Key to the SSH-Agent

1. **Start SSH-Agent**
   - Run `eval "$(ssh-agent -s)"`.

2. **Add SSH Key**
   - Add your SSH key to the agent with `ssh-add ~/.ssh/id_rsa`.

### Step 3: Add the SSH Key to Your GitHub Account

1. **Copy SSH Key**
   - Use `cat ~/.ssh/id_rsa.pub | pbcopy` on macOS or `xclip -selection clipboard < ~/.ssh/id_rsa.pub` on Linux to copy your public key.

2. **Add Key to GitHub**
   - Go to GitHub Settings -> SSH and GPG keys -> New SSH key.
   - Paste your key and save.

### Step 4: Switch to SSH on Your Repository

1. **Change Repository's Remote URL**
   - Use `git remote set-url origin git@github.com:username/repository.git`, replacing `username` and `repository.git` appropriately.

## Setting Up Credential Helper

### Configuring Git to Use Credential Helper

1. **Enable Credential Helper**
   - Run `git config --global credential.helper cache`.

### Extending Cache Timeout

1. **Set Custom Timeout**
   - For a longer timeout, use `git config --global credential.helper 'cache --timeout=3600'`.

### Using Credential Helper

- Credentials will be stored in memory for the specified duration after you enter them.

### For Permanent Storage

1. **Store Credentials Permanently**
   - Use `git config --global credential.helper store` for indefinite storage.
   - Note: This is less secure and not recommended on shared machines.
