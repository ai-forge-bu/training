# Vercel Deployment Guide

Step-by-step guide to deploy your project to Vercel.

---

## What is Vercel?

Vercel is a deployment platform for static sites and serverless functions. It's perfect for:
- HTML/CSS/JavaScript projects
- React, Next.js, Vue, or other frontend frameworks
- Projects with or without serverless backend

**Best for:** Any frontend project, especially React/Next.js

---

## Prerequisites

Before you start:
- [ ] Project is working locally
- [ ] All files are saved
- [ ] GitHub account created
- [ ] Git installed and configured
- [ ] Code pushed to GitHub repository

---

## Step 1: Create Vercel Account

1. Go to https://vercel.com/
2. Click **Sign Up**
3. Choose **Continue with GitHub**
4. Authorize Vercel to access your GitHub account
5. You're now logged into Vercel

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

## Step 3: Deploy to Vercel

### Import Project

1. In Vercel dashboard, click **Add New** > **Project**
2. Find your repository in the list
3. Click **Import** next to your repository name

### Configure Project

**For simple HTML/CSS/JS projects:**
- **Framework Preset:** Other
- **Root Directory:** ./
- **Build Command:** (leave empty)
- **Output Directory:** (leave empty)

**For React/Vite projects:**
- **Framework Preset:** Vite (auto-detected)
- **Build Command:** `npm run build`
- **Output Directory:** `dist`

**For Create React App:**
- **Framework Preset:** Create React App (auto-detected)
- **Build Command:** `npm run build`
- **Output Directory:** `build`

**Click "Deploy"**

---

## Step 4: Wait for Deployment

- Vercel will start building your site
- You'll see a build log with progress
- Wait for deployment to complete (usually under 2 minutes)
- You'll see a success screen with your URL

---

## Step 5: View Your Site

1. Click **Visit** or click the generated URL
2. Your site will open at: `https://your-project-name.vercel.app`
3. Test all features
4. Check that everything works as expected

---

## Step 6: Customize Your URL (Optional)

**Free custom subdomain:**
1. Go to your project in Vercel dashboard
2. Click **Settings** > **Domains**
3. Add a custom Vercel subdomain
4. Your URL: `https://my-cool-name.vercel.app`

**Custom domain (requires owning a domain):**
- Follow Vercel's domain setup guide
- Not needed for this training

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

**Vercel automatically rebuilds and deploys** when you push to GitHub!

---

## Common Issues & Solutions

### Issue: Build Failed

**Check the build log:**
1. Go to your project in Vercel
2. Click **Deployments**
3. Click the failed deployment
4. Read the error message

**Common causes:**
- Missing dependencies in package.json
- Build script errors
- Wrong build command

**Fix:**
```bash
# If missing dependencies
npm install <missing-package> --save
git add package.json package-lock.json
git commit -m "Fix dependencies"
git push
```

### Issue: 404 Not Found

**For simple HTML projects:**
- Make sure you have `index.html` in the root directory

**For React Router (or similar):**
1. Create `vercel.json` in your project root:
```json
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/" }
  ]
}
```
2. Commit and push

### Issue: Environment Variables Not Set

**For API keys or environment variables:**
1. Go to project Settings > Environment Variables
2. Add your variables:
   - Name: `VITE_API_KEY` (or whatever your app needs)
   - Value: your-api-key-here
3. Click **Save**
4. Redeploy: Deployments > click ... > Redeploy

**Important:** Never commit API keys to GitHub!

### Issue: Styles/JavaScript Not Loading

**Check file paths:**
```html
<!-- Wrong (absolute path may not work) -->
<script src="/js/app.js"></script>

<!-- Better (relative path) -->
<script src="./js/app.js"></script>

<!-- Best (for frameworks, use imports) -->
```

**Check browser console:**
- Open deployed site
- Press F12
- Look for 404 errors
- Fix file paths accordingly

### Issue: Site Not Updating

**Solutions:**
1. Hard refresh browser: `Ctrl/Cmd + Shift + R`
2. Check if GitHub has your latest code
3. Check Vercel deployment status
4. Force redeploy in Vercel dashboard

---

## Vercel Features

### Analytics
Vercel provides free analytics:
1. Go to project > Analytics
2. See page views, performance, etc.

### Preview Deployments
Every push gets its own preview URL - great for testing!

### Serverless Functions
Vercel supports serverless functions in `api/` folder (advanced feature).

---

## Vercel vs Netlify

**Choose Vercel if:**
- Using Next.js, React, or modern frameworks
- Want better performance for dynamic content
- Like the interface better

**Choose Netlify if:**
- Simple HTML/CSS/JS project
- Need form handling built-in
- Prefer simpler setup

**Both are great - use whichever you prefer!**

---

## Deployment Checklist

Before deploying:
- [ ] All features work locally
- [ ] No errors in browser console
- [ ] All files are saved and committed
- [ ] Code is pushed to GitHub
- [ ] Removed sensitive data from code
- [ ] Environment variables are ready (if needed)

After deploying:
- [ ] Site loads correctly
- [ ] All features work on deployed site
- [ ] Tested on mobile
- [ ] No console errors
- [ ] URL shared with team/trainer

---

## Troubleshooting Tips

**Build fails:**
1. Read the error message carefully
2. Check if you can build locally: `npm run build`
3. Fix errors locally first, then push

**Functions don't work:**
1. Check browser console for errors
2. Verify API calls are using correct URLs
3. Check environment variables are set

**Slow site:**
1. Check Vercel Analytics
2. Optimize images (compress them)
3. Remove unused code/libraries

---

## Getting Help

**Vercel Docs:** https://vercel.com/docs

**Common issues:**
- Build errors: Check deployment logs
- 404 errors: Check file paths and routing
- Environment variables: Settings > Environment Variables

**Still stuck?** Ask your PIC with:
- Link to GitHub repository
- Link to Vercel deployment
- Screenshot of error
- What you've tried

---

## Success

If you can:
- Access your site at the Vercel URL
- All features work correctly
- No console errors
- Tested on mobile

**Congratulations! Your app is deployed and live!**

Your project is now accessible worldwide. Share your URL with anyone who needs it!

---

## Next Steps (Optional)

After successful deployment:
- Set up a custom domain (if you have one)
- Monitor analytics
- Keep improving your project
- Deploy updates as needed

**Remember:** Every push to GitHub automatically deploys to Vercel!
