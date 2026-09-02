# Git workshop excercise
UCSC Rocket Team 2026/27 Git onboarding Workshop

## Workshop Excercise

This excercise provides a simple task that will introduce you to colaborative work though github here at Rocket Team. 

Steps to this excercise:
    1. Assign yourself to the "Missing Data" Issue
    2. Create your own branch to make your code changes in.
    3. Follow the instructions on the "Missing Data" issue to make changes accordingly to the files in this repository. 
    4. Commit and push your changes to your branch.
    5. Once you have made the nesscarry changes, create a "Pull Request", fix any merge issue that may appear.
    6. Request review from @OceancattUCSC.

## Git command cheat sheet

Here are some quick references for common Git commands and example usage that are useful during the when working with a Git repository. 

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
  Show the current state of the repository, including modified and staged files.
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
- Always check `git status` before committing.
- Pull the latest changes before pushing your work.
- Use branches to keep separate work isolated.


