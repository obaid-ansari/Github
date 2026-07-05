# 🧑‍💻 GitHub Commands

Here are some useful Git and GitHub commands for managing your workflow — including configuring Git, pushing changes, and merging branches.

---

## ⚙️ Checking and Configuring
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global --list        # Verify configuration
```

## ⚙️ File Status

### U - Untracked
### A - Staged
### M - Modified

## 🚀 Push Code to GitHub
```bash
# Initialize a new Git repository
git init

# Add all files to staging
git add .

# Commit your changes with a message
git commit -m "Initial commit"

# Connect your local repository to GitHub
git remote add origin https://github.com/your-username/your-repo-name.git

# Push your code to the main branch
git push -u origin main
```
## 🔧 Useful Git Commands
```bash
git status         # Check the current status of your repository
git status -s
git log            # View commit history
git log --oneline  # View concise commit history
git log --oneline --graph
git branch         # List all branches
git checkout       # Switch branches
git remote -v      # Show remote URLs

# Change or update the remote origin URL
git remote set-url origin https://github.com/your-username/your-repo-name.git
```
## 🌿 Create and Switch Branches
```bash
# Create a new branch
git branch feature-branch-name

# Switch to the new branch
git checkout feature-branch-name

# Create and switch in one command
git checkout -b feature-branch-name
```
## 🗑️ Delete Branches
```bash
# Delete a local branch
git branch -d feature-branch-name

# Force delete (if not merged)
git branch -D feature-branch-name

# Delete a remote branch
git push origin --delete feature-branch-name
```

## 🔁 Merge Branches
```bash
# Switch to the branch you want to merge into (usually main)
git checkout main

# Merge the feature branch into main
git merge feature-branch-name

# Push the updated main branch to GitHub
git push origin main
```

## 🌐 Clone & Undo Changes
```bash
git clone <repo_url>          # Clone a repository from GitHub

git restore --staged .        # Unstage all files (keep changes)
git restore .                 # Discard all local changes

git log --oneline             # Check commit history
git reset --soft HEAD~1       # Undo last commit (keep changes staged)
```
