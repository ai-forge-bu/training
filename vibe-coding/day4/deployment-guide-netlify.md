# Netlify Deployment Guide

Step-by-step guide to deploy your project to Netlify.

---

## What is Netlify?

Netlify is a platform that hosts static websites for free. It's perfect for:
- HTML/CSS/JavaScript projects
- React, Vue, or other frontend frameworks
- Projects without a backend server

**Best for:** Simple projects, single-page applications

---

## Prerequisites

Before you start:
- [ ] Project is working locally
- [ ] All files are saved
- [ ] GitHub account created
- [ ] Git installed and configured
- [ ] Code pushed to GitHub repository

---

## Step 1: Create Netlify Account

1. Go to https://www.netlify.com/
2. Click **Sign up** in the top right
3. Choose **Sign up with GitHub**
4. Authorize Netlify to access your GitHub account
5. You're now logged into Netlify

---

## Step 2: Push Your Project to GitHub

### Create New Repository

1. Go to https://github.com
2. Click **+** (top right) > **New repository**
3. Repository name: `my-project-name` (use your actual project name)
4. Description: (optional)
5. Choose **Public**
6. Do NOT check "Add a README"
7. Click **Create repository**

### Push Your Code

**In your project folder (using Terminal/Command Prompt):**

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit"

# Connect to GitHub (replace with your actual repository URL)
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# Push
git branch -M main
git push -u origin main
```

**Verify:** Refresh your GitHub repository page - you should see your files.

---

## Step 3: Deploy to Netlify

### Connect Repository

1. In Netlify dashboard, click **Add new site** > **Import an existing project**
2. Click **Deploy with GitHub**
3. Authorize Netlify if prompted
4. Find and select your repository
5. Click on your repository name

### Configure Build Settings

**For most simple projects (HTML/CSS/JS):**
- **Branch to deploy:** main
- **Build command:** (leave empty)
- **Publish directory:** (leave empty or type `.` if it asks)

**For React/Vue/Vite projects:**
- **Build command:** `npm run build`
- **Publish directory:** `dist` (or `build` for Create React App)

**Click "Deploy site"**

---

## Step 4: Wait for Deployment

- Netlify will start building your site
- You'll see a build log
- Wait for "Site is live" message (usually under 1 minute)
- You'll get a random URL like: `https://random-name-123456.netlify.app`

---

## Step 5: Test Your Site

1. Click the generated URL
2. Test all features
3. Check that everything works as expected
4. Test on mobile (use your phone or browser dev tools)

---

## Step 6: Customize Your URL (Optional)

1. In Netlify dashboard, go to **Site settings**
2. Click **Change site name** under Site information
3. Choose a unique name: `my-cool-project`
4. Your URL becomes: `https://my-cool-project.netlify.app`
5. Click **Save**

---

## Updating Your Site

When you make changes:

```bash
# Make changes to your code
# Save all files

# Add changes
git add .

# Commit
git commit -m "Update feature X"

# Push to GitHub
git push
```

**Netlify automatically rebuilds and deploys** when you push to GitHub. No extra steps needed!

---

## Common Issues & Solutions

### Issue: Site shows 404 or "Page Not Found"

**Solution 1: Check Publish Directory**
- Go to Site settings > Build & deploy > Publish directory
- Should be empty or `.` for simple HTML projects
- Should be `dist` or `build` for framework projects

**Solution 2: Check index.html exists**
- Make sure you have an `index.html` file
- Must be in the root or publish directory

### Issue: JavaScript not working

**Check:**
- Open browser console (F12) on deployed site
- Look for errors
- Often caused by incorrect file paths

**Fix file paths:**
```html
<!-- Wrong (absolute path) -->
<script src="/js/app.js"></script>

<!-- Right (relative path) -->
<script src="./js/app.js"></script>
```

### Issue: Styles not loading

**Check CSS link:**
```html
<!-- Make sure path is correct -->
<link rel="stylesheet" href="./style.css">
```

### Issue: Build failed

**Check build log:**
- Netlify shows why it failed
- Often missing dependencies or build errors

**For npm projects:**
```bash
# Make sure these are in package.json
npm install --save-dev <missing-package>
git add package.json package-lock.json
git commit -m "Fix dependencies"
git push
```

### Issue: Environment variables needed

**For API keys:**
1. Go to Site settings > Environment variables
2. Add your variables
3. Click **Save**
4. Redeploy site

**Important:** Never commit API keys to GitHub!

---

## Netlify Features You Can Use

### Forms
Netlify can handle form submissions without a backend.

```html
<form name="contact" method="POST" data-netlify="true">
  <input type="text" name="name" required>
  <input type="email" name="email" required>
  <button type="submit">Send</button>
</form>
```

Submissions appear in: Site settings > Forms

### Functions (Advanced)
Netlify supports serverless functions if you need backend logic.

### Custom Domain (Advanced)
You can connect your own domain name (requires purchasing a domain).

---

## Deployment Checklist

Before deploying:
- [ ] All features work locally
- [ ] No errors in browser console
- [ ] All files are saved
- [ ] Code is committed and pushed to GitHub
- [ ] Removed any sensitive data (API keys, passwords)

After deploying:
- [ ] Site loads correctly
- [ ] All features work on deployed site
- [ ] Tested on mobile
- [ ] No console errors on deployed site
- [ ] Shared URL with team/trainer

---

## Getting Help

**Netlify Docs:** https://docs.netlify.com/

**Common questions:**
- Build errors: Check the deploy log in Netlify
- Site not updating: Clear browser cache (Ctrl/Cmd + Shift + R)
- 404 errors: Check your publish directory setting

**Still stuck?** Ask your PIC with:
- Link to your GitHub repository
- Link to deployed Netlify site
- Screenshot of error
- What you've tried

---

## Success

If you can:
- See your site at the Netlify URL
- All features work correctly
- Tested on mobile

**Congratulations! Your app is live on the internet!**

Share your URL with friends, team, or anyone who needs it. Your project is now deployed and accessible worldwide.
