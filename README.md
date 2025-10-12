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
