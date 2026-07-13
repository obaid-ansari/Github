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

git reset --soft HEAD~1       # Undo last commit (keep changes staged)
```

```
```
# 📝 Git & GitHub Company Workflow Notes

## 1️⃣ Clone Company Repository

### Situation

I joined a company and received the repository link.

### Commands

```bash
git clone <repo-link>
cd <project-folder>
git branch -a
git checkout main-branch
git pull origin main-branch
```

### What each command does

* `git clone` → Downloads the project from GitHub.
* `cd` → Opens the project folder.
* `git branch -a` → Shows all local and remote branches.
* `git checkout main-branch` → Switches to the `main-branch` branch.
* `git pull origin main-branch` → Gets the latest code from `main-branch`.

---

# 2️⃣ Create a New Feature Branch

### Situation

Manager says:

> "Create a CTA button."

### Commands

```bash
git branch
```

Check that you are on the `main-branch` branch.

Then create a feature branch:

```bash
git checkout -b cta/button
```

### Meaning

* Creates a new branch.
* Switches to that branch.
* The new branch starts from the latest `main-branch`.

---

# 3️⃣ Finish Your Work

### Stage files

```bash
git add src/components/Button.vue
```

or

```bash
git add .
```

> Stage only the files you want to commit.

---

### Commit

```bash
git commit -m "feat(cta): add CTA button"
```

Meaning:
Save your changes in your local Git history.

---

### Push

```bash
git push origin cta/button
```

Meaning:
Upload your branch to GitHub.

---

### Create Pull Request

Create a PR from

```
cta/button
        ↓
main-branch
```

---

# 4️⃣ main-branch Updated (My Work Is NOT Committed)

### Situation

* Working on `cta/button`
* Someone updated `main-branch`
* My code is **not committed**

### Commands

```bash
git stash
git checkout main-branch
git pull origin main-branch
git checkout cta/button
git stash apply
git add .
git commit -m "feat(cta): add CTA button"
git push origin cta/button
```

### Why?

* `git stash` → Save temporary work.
* Pull latest main-branch.
* Return to feature branch.
* Restore work.
* Commit and push.

---

# 5️⃣ main-branch Updated (My Work Is Already Committed)

### Situation

✅ Code added

✅ Code committed

❌ Not pushed

Someone updated `main-branch`.

### Commands

```bash
git checkout main-branch
git pull origin main-branch
git checkout cta/button
git merge main-branch
git push origin cta/button
```

OR

```bash
git checkout main-branch
git pull origin main-branch
git checkout cta/button
git rebase main-branch
git push origin cta/button
```

### Important

If your work is already committed,

❌ Don't use `git stash`.

Use **Merge** or **Rebase**.

---

# 6️⃣ When Should I Use `git stash`?

### Case 1

```
Code written

❌ add
❌ commit
```

Use

```bash
git stash
```

---

### Case 2

```
Code written

✅ add
❌ commit
```

Use

```bash
git stash
```

---

### Case 3

```
Code written

✅ add
✅ commit
```

Do **NOT** use

```bash
git stash
```

Instead use

```bash
git merge main-branch
```

or

```bash
git rebase main-branch
```

---

# 📌 Quick Cheat Sheet

| Situation            | Command                                     |
| -------------------- | ------------------------------------------- |
| Clone project        | `git clone`                                 |
| Latest main-branch       | `git pull origin main-branch`                   |
| New feature branch   | `git checkout -b feature/name`              |
| Stage changes        | `git add .`                                 |
| Commit               | `git commit -m "message"`                   |
| Push                 | `git push origin branch-name`               |
| Save temporary work  | `git stash`                                 |
| Restore work         | `git stash apply`                           |
| Bring latest main-branch | `git merge main-branch` or `git rebase main-branch` |
| Raise PR             | GitHub UI                                   |

---

# ⭐ Golden Rule

```
Code NOT committed
        ↓
Use git stash

-------------------------

Code committed
        ↓
Use git merge
or
git rebase

-------------------------

Push not done?
No problem.

-------------------------

Push done?
Continue normal workflow.
```

# 7️⃣ main-branch Updated After I Already Pushed My Branch

## Situation

* ✅ Code completed
* ✅ `git add`
* ✅ `git commit`
* ✅ `git push`
* ❌ PR not created yet

Meanwhile, someone merged new code into the `main-branch` branch.

### Commands

```bash
git checkout main-branch
git pull origin main-branch

git checkout cta/button

# Option 1 (Most Common)
git merge main-branch

# OR Option 2 (If your team uses rebase)
git rebase main-branch
```

### Push Again

If you used **merge**:

```bash
git push origin cta/button
```

If you used **rebase**:

```bash
git push --force-with-lease origin cta/button
```

### Then

Create the Pull Request to the `main-branch` branch.

---

## Why?

* Get the latest changes from `main-branch`.
* Make sure your feature branch is up to date.
* Resolve any conflicts before creating the PR.
* Reduce review and merge issues.

## Remember

* ✅ Already committed → No `git stash`
* ✅ Already pushed → Just sync with `main-branch`
* ✅ Merge or Rebase, then push again
* ✅ Finally create the Pull Request
