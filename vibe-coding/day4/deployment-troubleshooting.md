# Deployment Troubleshooting Guide

Common issues when deploying to Netlify or Vercel, and how to fix them.

---

## Before You Start Troubleshooting

### Basic Checklist

- [ ] Does your project work locally?
- [ ] Are all files saved?
- [ ] Did you commit all changes?
- [ ] Did you push to GitHub?
- [ ] Can you see your files on GitHub?

If you answered "No" to any, fix that first before debugging deployment issues.

---

## GitHub Issues

### Issue: Can't push to GitHub

**Error:** `fatal: repository not found` or `permission denied`

**Solutions:**

1. **Check repository URL:**
```bash
git remote -v
```
Make sure it shows your correct GitHub username and repository name.

2. **Fix remote URL:**
```bash
git remote set-url origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
```

3. **Check authentication:**
- Make sure you're logged into the correct GitHub account
- If using token, make sure it's valid

### Issue: Merge conflict

**Error:** `CONFLICT (content): Merge conflict in...`

**Solution:**
1. Open the conflicted file in VS Code
2. Look for conflict markers:
```
<<<<<<< HEAD
Your local changes
=======
Remote changes
>>>>>>> main
```
3. Decide which version to keep (or merge both)
4. Remove the conflict markers (`<<<<`, `====`, `>>>>`)
5. Save the file
6. Commit:
```bash
git add .
git commit -m "Resolve merge conflict"
git push
```

### Issue: Files missing on GitHub

**Cause:** Forgot to add files before committing

**Solution:**
```bash
# Add all files
git add .

# Commit
git commit -m "Add missing files"

# Push
git push
```

---

## Build Failures

### Issue: Build fails with "Command not found"

**Error:** `npm: command not found` or `build: command not found`

**Cause:** Missing build configuration

**For simple HTML/CSS/JS projects:**
- Build command should be empty
- Publish directory should be empty or `.`

**For React/Vite/npm projects:**
- Build command: `npm run build`
- Check `package.json` has build script:
```json
{
  "scripts": {
    "build": "vite build"  // or appropriate build command
  }
}
```

### Issue: "Module not found" during build

**Error:** `Error: Cannot find module 'package-name'`

**Cause:** Dependency not in package.json

**Solution:**
```bash
# Install the missing package
npm install package-name

# Make sure to commit package.json and package-lock.json
git add package.json package-lock.json
git commit -m "Add missing dependency"
git push
```

### Issue: Build fails on Netlify/Vercel but works locally

**Common causes:**

1. **Case-sensitive file names:**
   - Local (Windows/Mac) might not care about case
   - Servers are case-sensitive
   - Fix: Make sure file names match exactly

2. **Environment variables:**
   - Missing API keys or env variables
   - Solution: Add them in Netlify/Vercel dashboard

3. **Node version mismatch:**
   - Specify Node version in `package.json`:
```json
{
  "engines": {
    "node": "18.x"
  }
}
```

---

## Deployment Issues

### Issue: Site shows blank page

**Check browser console:**
1. Open deployed site
2. Press F12
3. Go to Console tab
4. Look for errors

**Common causes:**

1. **Wrong file paths:**
```html
<!-- Wrong (absolute paths may not work) -->
<script src="/js/app.js"></script>

<!-- Right (relative paths) -->
<script src="./js/app.js"></script>
```

2. **Missing index.html:**
- Make sure `index.html` exists in root (or publish directory)

3. **JavaScript errors:**
- Fix errors shown in console
- Test locally first

### Issue: 404 Page Not Found

**For static sites:**
1. Check publish directory in deployment settings
2. Make sure `index.html` is in that directory

**For Single Page Apps (React Router, etc.):**

**Netlify solution:**
Create `public/_redirects` file:
```
/*    /index.html   200
```

**Vercel solution:**
Create `vercel.json` in root:
```json
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/" }
  ]
}
```

Then commit and push:
```bash
git add .
git commit -m "Fix routing"
git push
```

### Issue: CSS not loading

**Solutions:**

1. **Check file path in HTML:**
```html
<!-- Make sure path is correct -->
<link rel="stylesheet" href="./style.css">
```

2. **Check browser Network tab:**
- F12 > Network
- Refresh page
- Look for 404 errors on CSS file
- Fix the path

3. **Clear cache:**
- Hard refresh: Ctrl/Cmd + Shift + R

### Issue: Images not showing

**Solutions:**

1. **Check image paths:**
```html
<!-- If images are in 'images' folder -->
<img src="./images/photo.jpg" alt="Photo">
```

2. **Check file names:**
- Case-sensitive on servers
- `Photo.jpg` ≠ `photo.jpg`

3. **Check image files are committed:**
```bash
git add images/
git commit -m "Add images"
git push
```

---

## Environment Variables

### Issue: API calls not working

**Cause:** Missing environment variables (API keys)

**Netlify solution:**
1. Go to Site settings > Environment variables
2. Add your variables:
   - Key: `VITE_API_KEY` (match your .env file)
   - Value: your-api-key
3. Save
4. Trigger redeploy: Deploys > Trigger deploy > Clear cache and deploy

**Vercel solution:**
1. Go to Settings > Environment Variables
2. Add your variables
3. Redeploy

**Important naming:**
- Vite: Variables must start with `VITE_`
- Create React App: Variables must start with `REACT_APP_`
- Next.js: Variables can start with `NEXT_PUBLIC_`

### Issue: Environment variables not working

**Check:**

1. **Variable naming:**
```javascript
// In code, access like this:
// Vite
const apiKey = import.meta.env.VITE_API_KEY;

// Create React App
const apiKey = process.env.REACT_APP_API_KEY;
```

2. **Rebuild after adding variables:**
- Environment variables only apply to new builds
- Trigger a new deployment

---

## Performance Issues

### Issue: Site is slow to load

**Solutions:**

1. **Optimize images:**
- Compress images before uploading
- Use appropriate image sizes
- Consider using WebP format

2. **Remove unused code:**
- Delete unused files
- Remove unused npm packages

3. **Check bundle size:**
```bash
# For Vite projects
npm run build
# Check dist folder size
```

---

## Site Not Updating

### Issue: Changes don't appear on deployed site

**Solutions:**

1. **Make sure you pushed to GitHub:**
```bash
git status  # Should show "nothing to commit"
```

2. **Check GitHub:**
- Go to your repository
- Make sure you see your latest changes

3. **Check deployment status:**
- Netlify/Vercel dashboard
- Look at recent deployments
- Check if deployment succeeded

4. **Clear browser cache:**
- Hard refresh: Ctrl/Cmd + Shift + R

5. **Force redeploy:**
- Netlify: Deploys > Trigger deploy
- Vercel: Deployments > ... > Redeploy

---

## Common Error Messages

### "Failed to compile"

**Meaning:** Code has syntax errors

**Solution:**
1. Read the error message carefully
2. Fix the error in your code
3. Test locally: `npm run build`
4. Commit and push

### "Error: ENOENT: no such file or directory"

**Meaning:** File not found

**Solution:**
1. Check file path in error message
2. Make sure file exists
3. Check file name spelling/case
4. Make sure file is committed to Git

### "Port already in use"

**Meaning:** (Only affects local development)

**Solution:**
- This doesn't affect deployment
- For local: kill the process or use different port

---

## Getting More Help

### Check Deployment Logs

**Netlify:**
1. Go to Deploys
2. Click on failed deployment
3. Read the log
4. Look for errors in red

**Vercel:**
1. Go to Deployments
2. Click on failed deployment
3. Read the build log
4. Look for error messages

### What to Share When Asking for Help

Provide your PIC with:
- [ ] Link to GitHub repository
- [ ] Link to deployed site (if it deployed)
- [ ] Screenshot of error message
- [ ] Deployment logs (copy the error)
- [ ] What you've already tried

### Useful Links

**Netlify Docs:** https://docs.netlify.com/
**Vercel Docs:** https://vercel.com/docs
**Stack Overflow:** https://stackoverflow.com/ (search for your error)

---

## Prevention Tips

### Before Deploying

1. **Test locally thoroughly:**
- All features work?
- No console errors?
- Works in different browsers?

2. **Clean commit:**
```bash
git status          # Check what's changed
git add .           # Add all files
git commit -m "Descriptive message"
git push            # Push to GitHub
```

3. **Verify on GitHub:**
- Check files are there
- Check latest commit shows

4. **Then deploy**

### After Deploying

1. **Test deployed site:**
- Try all features
- Check on mobile
- Test with fresh browser (incognito)

2. **Fix issues immediately:**
- Fix locally
- Test locally
- Commit and push
- Wait for automatic redeploy

---

## Emergency: Site is Broken

**If your live site is broken:**

1. **Don't panic**
2. **Check what changed:**
   - Last commit that broke it
3. **Quick fix options:**

**Option A: Fix forward**
- Fix the bug quickly
- Test locally
- Push fix

**Option B: Revert to working version** (Advanced)
```bash
# Find last working commit
git log

# Revert to that commit
git revert <commit-hash>
git push
```

4. **Ask for help if stuck**

---

## Success Checklist

Your site is successfully deployed if:
- [ ] Can access the URL
- [ ] All features work
- [ ] No console errors (F12 > Console)
- [ ] Works on mobile
- [ ] Data persists (if using localStorage)
- [ ] Forms submit correctly
- [ ] All pages/routes load

**If all checked: Congratulations!**

---

## Remember

- Read error messages carefully - they tell you what's wrong
- Test locally before deploying
- Check browser console on deployed site
- Google the error message
- Ask your PIC if stuck for 15+ minutes

**Every developer deals with deployment issues - you're learning valuable skills!**
