# Github Commands
Here are some useful Git and GitHub commands for managing your workflow, including pushing changes and merging code.
### Checking and Configuring
```
git config --global user.name "name"
git config --global user.email "email"
git config --global --list
```

### Push Code to GitHub
```
# Initialize a Git repository
git init

# Add all files to staging
git add .

# Commit your changes with a message
git commit -m "Initial commit"

# Connect your local repository to GitHub
git remote add origin https://github.com/your-username/your-repo-name.git

# Push your code to the main branch
git push origin main

```
### Useful Git Commands
```
git status        # Check the current status of your repository
git log           # View commit history
git branch        # List all branches
git checkout      # Switch branches
git merge         # Merge branches
# Reset/Change the Remote Origin URL
git remote set-url origin git@github.com:yourusername/your-repo.git
```

### Create and Switch Branches
```
# Create a new branch
git branch feature-branch-name

# Switch to the new branch
git checkout feature-branch-name

# Create and switch in one command
git checkout -b feature-branch-name
```

### Delete Branches
```
# Delete a local branch
git branch -d feature-branch-name

# Force delete (if branch not merged)
git branch -D feature-branch-name

# Delete a remote branch
git push origin --delete feature-branch-name
```

### Merge Branches
```
# Switch to the branch you want to merge into (usually main)
git checkout main

# Merge the feature branch into main
git merge feature-branch-name

# After merging you have to push
git push origin main
```
