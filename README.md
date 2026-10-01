# Git workshop exercise
UCSC Rocket Team 2026/27 Git onboarding Workshop

## Workshop Exercise

This exercise provides a simple task that will introduce you to collaborative work through GitHub here at Rocket Team. 

Steps to this exercise:
1. Assign yourself to the "Missing Data" Issue
2. Create your own branch to make your code changes in.
3. Follow the instructions on the "Missing Data" issue to make changes accordingly to the files in this repository. 
4. Commit and push your changes to your branch.
5. Once you have made the necessary changes, create a "Pull Request" and fix any merge issues that may appear.
6. Request review from @OceancattUCSC.

## SSH keys (Credit to CSE 40 HW0 Git Setup Instructions)

When using Git, the easiest way to authenticate from the command line is with [SSH keys](https://wiki.archlinux.org/title/SSH_keys).

SSH keys are a pair of keys: a private key and a public key. You can use them to prove your identity to GitHub and other services. Always keep your **private key private** and never share it with anyone. You can share your public key with services that need to authenticate you, such as GitHub.

GitHub supports SSH keys for repository access. You can also authenticate with [personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-personal-access-token-classic), but SSH keys are the recommended approach for this course.

### Check for existing keys

SSH keys are usually stored in the `~/.ssh` directory, where `~` means your [home directory](https://en.wikipedia.org/wiki/Home_directory). Check for existing keys before generating a new one:

```bash
ls -lh ~/.ssh
```

Key files usually start with `id_`. Public keys have a `.pub` suffix, while private keys have no suffix. If you already have a key you want to use, you can skip to [Add your public key to GitHub](#add-your-public-key-to-github).

### Generate an SSH key

Use `ssh-keygen` to generate a new key. The default settings are sufficient for this course. Ed25519 is a modern, secure key type:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

When prompted:

1. Press **Enter** to accept the default file location if this is your first key. If you already have a key, enter another memorable filename, such as `~/.ssh/id_github`.
2. Enter a passphrase, or press **Enter** twice to leave it empty. A passphrase provides additional protection if someone gains access to your computer.

For example:

```text
Enter file in which to save the key (/Users/your-name/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/your-name/.ssh/id_ed25519
Your public key has been saved in /Users/your-name/.ssh/id_ed25519.pub
```

The command creates two files in `~/.ssh`:

- `id_ed25519`: your private key. Never share this file.
- `id_ed25519.pub`: your public key. This is the key you can share with GitHub.

### Add your public key to GitHub

Print your public key so you can copy it:

```bash
cat ~/.ssh/id_ed25519.pub
```

The key typically starts with `ssh-ed25519` and ends with your email address. Copy the entire line, but do not copy your private key.

Then:

1. Open [GitHub SSH and GPG keys settings](https://github.com/settings/keys).
2. Click **New SSH key**.
3. Give the key a descriptive title, such as `Personal laptop`.
4. Paste the public key into the **Key** field.
5. Click **Add SSH key**.

You can now use GitHub from the terminal over SSH without entering your GitHub password for every operation.

## Git command cheat sheet

Here are some quick references for common Git commands and example usage that are useful when working with a Git repository. 

### Setting up a Git Repo

- `git init`  
  Initialize a new Git repository in the current folder.
  ```bash
  git init
  ```

- `git clone <repository-url>`  
  Copy an existing repository from a remote server to your machine.
  ```bash
  git clone https://github.com/example/project.git
  ```

### Checking status and history

- `git status`  
  Shows the current state of the repository, including modified and staged files.
  ```bash
  git status
  ```

- `git log`  
  View the commit history.
  ```bash
  git log --oneline --decorate --graph --all
  ```

- `git diff`  
  Show changes between your working tree and the last commit.
  ```bash
  git diff
  ```

- `git diff --staged`  
  Show changes that are currently staged.
  ```bash
  git diff --staged
  ```

### Working with files

- `git add <file>`  
  Stage a specific file for commit.
  ```bash
  git add README.md
  ```

- `git add .`  
  Stage all modified files in the current repository.
  ```bash
  git add .
  ```

- `git commit -m "message"`  
  Save the staged changes with a commit message.
  ```bash
  git commit -m "Add project README"
  ```

- `git restore <file>`  
  Revert a file to its last committed state.
  ```bash
  git restore README.md
  ```

- `git restore --staged <file>`  
  Unstage a file without losing its changes.
  ```bash
  git restore --staged README.md
  ```

### Branching and merging

- `git branch`  
  List all branches in the repository.
  ```bash
  git branch
  ```

- `git checkout -b <branch-name>`  
  Create and switch to a new branch.
  ```bash
  git checkout -b feature/new-page
  ```

- `git switch <branch-name>`  
  Switch to an existing branch.
  ```bash
  git switch main
  ```

- `git merge <branch-name>`  
  Merge another branch into the current branch.
  ```bash
  git merge feature/new-page
  ```

### Remote repositories

- `git remote -v`  
  Show the configured remote repositories.
  ```bash
  git remote -v
  ```

- `git pull origin <branch-name>`  
  Fetch and merge changes from a remote branch.
  ```bash
  git pull origin main
  ```

- `git push origin <branch-name>`  
  Upload local commits to a remote branch.
  ```bash
  git push origin feature/new-page
  ```

- `git remote add origin <repository-url>`  
  Link a local repository to a remote repository.
  ```bash
  git remote add origin https://github.com/example/project.git
  ```

### Useful shortcuts and workflows

- `git fetch`  
  Download remote updates without merging them.
  ```bash
  git fetch origin
  ```

- `git stash`  
  Temporarily save uncommitted changes.
  ```bash
  git stash
  ```

- `git stash pop`  
  Reapply the most recent stashed changes.
  ```bash
  git stash pop
  ```

- `git status -sb`  
  Short status format that is easier to scan.
  ```bash
  git status -sb
  ```

## Example workflow

```bash
git clone https://github.com/example/project.git
cd project
git checkout -b feature/update-readme
git add README.md
git commit -m "Update README content"
git push origin feature/update-readme
```

## Notes

- Commit often with clear, descriptive messages.
- Pull the latest changes before pushing your work.
- Use branches to keep separate work isolated.


