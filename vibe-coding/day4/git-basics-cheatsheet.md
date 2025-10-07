# Git Basics Cheat Sheet

Quick reference for the Git commands you'll need on Day 4.

---

## Essential Workflow

This is what you'll do most often:

```bash
# 1. Make changes to your files
# (edit in VS Code, save files)

# 2. Check what changed
git status

# 3. Add files to staging
git add .

# 4. Commit with a message
git commit -m "Describe what you changed"

# 5. Push to GitHub
git push
```

---

## First Time Setup

### Configure Git (Do this once)

```bash
# Set your name
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"

# Check configuration
git config --list
```

---

## Starting a New Project

### Option 1: Start Locally, Push to GitHub

```bash
# In your project folder
git init

# Add all files
git add .

# First commit
git commit -m "Initial commit"

# Connect to GitHub repository
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git

# Push
git branch -M main
git push -u origin main
```

### Option 2: Clone from GitHub

```bash
# Clone repository
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git

# Enter folder
cd YOUR-REPO

# Start working
```

---

## Common Commands

### Checking Status

```bash
# See what files changed
git status

# See what changed in files
git diff
```

### Adding Files

```bash
# Add all files
git add .

# Add specific file
git add filename.txt

# Add multiple files
git add file1.txt file2.txt

# Add all files of a type
git add *.js
```

### Committing Changes

```bash
# Commit with message
git commit -m "Your message here"

# Commit with longer message
git commit -m "Title" -m "Longer description"
```

### Pushing to GitHub

```bash
# Push to main branch
git push

# First time push (creates remote branch)
git push -u origin main
```

### Getting Updates

```bash
# Get latest changes from GitHub
git pull
```

---

## Understanding Git Workflow

### The Three States

```
Working Directory  →  Staging Area  →  Repository
(your files)          (git add)        (git commit)
```

1. **Working Directory:** Where you edit files
2. **Staging Area:** Files ready to commit (after `git add`)
3. **Repository:** Committed files (after `git commit`)

### Typical Day Workflow

```bash
# Morning: Get latest code
git pull

# Work on feature
# (edit files in VS Code)

# Save progress
git add .
git commit -m "Add feature X"

# Share with team
git push
```

---

## Good Commit Messages

### Good Examples

```bash
git commit -m "Add contact form validation"
git commit -m "Fix bug in todo delete function"
git commit -m "Update homepage styling"
git commit -m "Remove unused CSS files"
```

### Bad Examples

```bash
git commit -m "Update"          # Too vague
git commit -m "Fix"             # What did you fix?
git commit -m "asdfasdf"        # Not descriptive
git commit -m "Changes"         # No information
```

### Tips for Good Messages

- Start with a verb: Add, Fix, Update, Remove, Refactor
- Be specific but concise
- Explain WHAT changed, not how
- Keep it under 50 characters if possible

---

## Common Scenarios

### Scenario 1: Made Changes, Want to Save

```bash
git add .
git commit -m "Describe your changes"
git push
```

### Scenario 2: Want to See What Changed

```bash
git status                    # List changed files
git diff                      # See line-by-line changes
```

### Scenario 3: Made a Mistake in Last Commit Message

```bash
# Fix the most recent commit message
git commit --amend -m "Corrected message"
git push --force              # Be careful with this!
```

### Scenario 4: Want to Undo Changes (Before Commit)

```bash
# Undo changes to a file
git checkout filename.txt

# Undo all changes
git checkout .
```

### Scenario 5: Forgot to Add a File

```bash
# Add the forgotten file
git add forgotten-file.txt

# Amend the previous commit
git commit --amend --no-edit

# Push (might need force push)
git push --force
```

---

## Working with GitHub

### Creating a Repository on GitHub

1. Go to GitHub.com
2. Click **+** > **New repository**
3. Name your repository
4. Choose Public or Private
5. Click **Create repository**
6. Follow the instructions to push existing code

### Connecting Local Project to GitHub

```bash
# Add GitHub as remote
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git

# Verify remote is added
git remote -v

# Push to GitHub
git push -u origin main
```

---

## Troubleshooting

### Problem: "fatal: not a git repository"

**Cause:** You're not in a Git-initialized folder

**Fix:**
```bash
git init
```

### Problem: "failed to push some refs"

**Cause:** GitHub has changes you don't have locally

**Fix:**
```bash
git pull
# Resolve any conflicts if needed
git push
```

### Problem: Merge conflicts

**Cause:** Same file edited in different ways locally and on GitHub

**Fix:**
1. Open the conflicted file in VS Code
2. Look for conflict markers:
```
<<<<<<< HEAD
Your changes
=======
GitHub changes
>>>>>>> branch-name
```
3. Choose which version to keep (or combine them)
4. Remove the conflict markers
5. Save the file
6. Commit:
```bash
git add .
git commit -m "Resolve merge conflict"
git push
```

### Problem: Pushed sensitive data (API key, password)

**Fix:**
1. Immediately delete the sensitive data from code
2. Commit and push the change
3. Generate new API key/password (old one is compromised!)
4. Add sensitive file to `.gitignore`:
```bash
echo ".env" >> .gitignore
git add .gitignore
git commit -m "Add .gitignore"
git push
```

---

## .gitignore

Tells Git which files to ignore.

### Common .gitignore

Create a file named `.gitignore` in your project root:

```
# Dependencies
node_modules/

# Environment variables
.env
.env.local

# Build outputs
dist/
build/

# OS files
.DS_Store
Thumbs.db

# IDE files
.vscode/
.idea/

# Logs
*.log
```

### Usage

```bash
# Create .gitignore
touch .gitignore

# Edit in VS Code
code .gitignore

# Add to Git
git add .gitignore
git commit -m "Add .gitignore"
```

---

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git init` | Start tracking a folder with Git |
| `git status` | See what changed |
| `git add .` | Stage all changes |
| `git add file.txt` | Stage specific file |
| `git commit -m "msg"` | Save staged changes |
| `git push` | Upload to GitHub |
| `git pull` | Download from GitHub |
| `git clone <url>` | Copy repository from GitHub |
| `git log` | See commit history |
| `git diff` | See what changed |

---

## For Day 4

You'll mainly need:

```bash
# 1. Push your project to GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin YOUR-GITHUB-URL
git push -u origin main

# 2. Make updates later
git add .
git commit -m "Update X"
git push
```

**That's it! These are the only commands you need for deployment.**

---

## Help Resources

**Git Documentation:** https://git-scm.com/doc

**GitHub Guides:** https://guides.github.com/

**Interactive Tutorial:** https://learngitbranching.js.org/

**Still confused?** Ask your PIC - they're here to help!

---

## Remember

- Commit often (small commits are better)
- Write clear commit messages
- Always pull before you push (if working with others)
- Don't commit sensitive data
- When in doubt, `git status` shows you what's going on

**You don't need to memorize this - just refer back when needed!**
