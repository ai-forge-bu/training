# GitHub Setup Guide

Step-by-step guide to create a GitHub account and set up Git on your computer.

---

## Part 1: Create GitHub Account

### Step 1: Sign Up
1. Go to https://github.com
2. Click **Sign up** in the top right
3. Enter your email address
4. Create a password (make it strong!)
5. Choose a username (this will be public)
6. Complete the verification puzzle
7. Click **Create account**

### Step 2: Verify Email
1. Check your email inbox
2. Find the verification email from GitHub
3. Click the verification link
4. You'll be redirected to GitHub

### Step 3: Choose Free Plan
1. Select the **Free** plan (it's perfect for this training)
2. Click **Continue**
3. Skip the survey if you want (or fill it out)
4. You now have a GitHub account

---

## Part 2: Install Git

### For Windows

**Step 1: Download Git**
1. Go to https://git-scm.com/download/win
2. Download will start automatically
3. Run the installer

**Step 2: Install Git**
1. Click **Next** through most screens (defaults are fine)
2. **Important screens:**
   - Default editor: Choose "Use Visual Studio Code as Git's default editor"
   - Adjusting PATH: Select "Git from the command line and also from 3rd-party software"
   - Line endings: Select "Checkout Windows-style, commit Unix-style"
3. Click **Install**
4. Click **Finish**

**Step 3: Verify Installation**
1. Open Command Prompt or PowerShell
2. Type: `git --version`
3. You should see something like: `git version 2.x.x`

### For macOS

**Option 1: Using Homebrew (Recommended)**
1. Open Terminal
2. Run: `brew install git`
3. Wait for installation to complete

**Option 2: Download Installer**
1. Go to https://git-scm.com/download/mac
2. Download the installer
3. Open the downloaded file
4. Follow the installation wizard

**Verify Installation**
1. Open Terminal
2. Type: `git --version`
3. You should see: `git version 2.x.x`

---

## Part 3: Configure Git

After installing Git, you need to tell it who you are.

### Set Your Name and Email

**Open Terminal/Command Prompt and run:**

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Important:**
- Use your real name (or the name you want on commits)
- Use the same email you used for GitHub

**Verify Configuration:**
```bash
git config --global user.name
git config --global user.email
```

---

## Part 4: Connect Git to GitHub

You need to authenticate so Git can push to GitHub.

### Windows & macOS (Modern Method)

When you try to push to GitHub for the first time, Git will prompt you to authenticate:

1. You'll see a browser window open
2. Log in to GitHub
3. Click "Authorize"
4. You're connected

**This happens automatically during your first push - no setup needed.**

### Alternative: Personal Access Token (If Browser Auth Doesn't Work)

**Step 1: Create Token**
1. Go to GitHub.com and log in
2. Click your profile picture (top right)
3. Go to **Settings**
4. Scroll down to **Developer settings** (bottom left)
5. Click **Personal access tokens** > **Tokens (classic)**
6. Click **Generate new token** > **Generate new token (classic)**
7. Give it a note: "Training Token"
8. Select expiration: 90 days
9. Check these scopes:
   - [x] repo (all repo permissions)
10. Click **Generate token**
11. **COPY THE TOKEN NOW** (you won't see it again!)

**Step 2: Use Token as Password**
- When Git asks for password, paste your token
- Git will remember it for future pushes

---

## Part 5: Test Your Setup

### Create a Test Repository

**On GitHub:**
1. Go to https://github.com
2. Click the **+** icon (top right)
3. Select **New repository**
4. Repository name: `test-repo`
5. Keep it **Public**
6. Check **Add a README file**
7. Click **Create repository**

**On Your Computer:**

1. Open Terminal/Command Prompt
2. Navigate to a test folder:
   ```bash
   cd Desktop
   ```

3. Clone your repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/test-repo
   ```
   (Replace YOUR-USERNAME with your actual GitHub username)

4. Enter the folder:
   ```bash
   cd test-repo
   ```

5. Create a test file:
   ```bash
   echo "Hello GitHub" > test.txt
   ```

6. Add the file:
   ```bash
   git add test.txt
   ```

7. Commit the file:
   ```bash
   git commit -m "Add test file"
   ```

8. Push to GitHub:
   ```bash
   git push
   ```

9. Go to your repository on GitHub and refresh - you should see `test.txt`

**If you see the file on GitHub, you're all set up!**

---

## Common Issues & Solutions

### Issue: "git is not recognized" (Windows)
**Solution:**
- Reinstall Git and make sure "Add to PATH" is checked
- Restart your terminal/command prompt after installation

### Issue: "git: command not found" (macOS)
**Solution:**
- Install Xcode command line tools: `xcode-select --install`
- Or install via Homebrew: `brew install git`

### Issue: Authentication failed
**Solution:**
1. Make sure you're using the correct GitHub username
2. If using token, make sure you copied it correctly
3. Try creating a new personal access token

### Issue: Permission denied
**Solution:**
- Check you're logged into the correct GitHub account
- Make sure the repository exists and you have access to it
- Verify your GitHub email is verified

---

## Git Basics Cheat Sheet

You'll need these commands on Day 4:

```bash
# Clone a repository
git clone <repository-url>

# Check status
git status

# Add files to staging
git add .                    # Add all files
git add filename.txt         # Add specific file

# Commit changes
git commit -m "Your message"

# Push to GitHub
git push

# Pull latest changes
git pull
```

---

## Tips

1. **Commit messages should be clear**
   - Good: "Add contact form validation"
   - Bad: "Update", "Fix", "Changes"

2. **Commit often**
   - Small, frequent commits are better than huge ones
   - Makes it easier to track changes

3. **Always pull before you push**
   - Especially if working with others
   - Prevents conflicts

4. **Don't commit sensitive data**
   - No API keys
   - No passwords
   - No personal information

---

## Ready for Day 4

By the end of this guide, you should have:
- [x] GitHub account created
- [x] Git installed on your computer
- [x] Git configured with your name and email
- [x] Successfully pushed a test file to GitHub

**If you have all of these, you're ready for deployment on Day 4!**

If you're stuck on any step, refer to the troubleshooting section or ask your PIC for help.
