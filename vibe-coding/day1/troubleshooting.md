# Day 1 Troubleshooting Guide

Common issues participants may encounter during setup and their solutions.

## Visual Studio Code Issues

### Issue: "code is not recognized" (Windows)
**Symptoms:** Can't run `code` command in terminal

**Solution:**
1. Reinstall VS Code with "Add to PATH" option checked
2. Or manually add to PATH:
   - Search "Environment Variables" in Windows
   - Edit PATH variable
   - Add: `C:\Users\{YourUsername}\AppData\Local\Programs\Microsoft VS Code\bin`
3. Restart terminal

### Issue: "command not found: code" (macOS)
**Symptoms:** Can't run `code` command in terminal

**Solution:**
1. Open VS Code
2. Press `Cmd + Shift + P`
3. Type and select: **Shell Command: Install 'code' command in PATH**
4. Restart terminal

### Issue: Extensions won't install
**Symptoms:** Extensions panel shows errors or won't download

**Solution:**
1. Check internet connection
2. Disable proxy/VPN if using
3. Try: `Ctrl/Cmd + Shift + P` > "Developer: Reload Window"
4. Restart VS Code

---

## Node.js / npm Issues

### Issue: "node is not recognized" (Windows)
**Symptoms:** Node.js installed but command not found

**Solution:**
1. Verify installation path: `C:\Program Files\nodejs\`
2. Add to PATH if missing:
   - Windows Search > "Environment Variables"
   - Edit PATH
   - Add: `C:\Program Files\nodejs\`
3. Restart terminal

### Issue: npm permission errors (macOS/Linux)
**Symptoms:** `EACCES` errors when installing global packages

**Solution:**
```bash
# Fix npm permissions
sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}
```

---

## Google Gemini CLI Issues

### Issue: "Execution Policy" error (Windows)
**Full error message:**
```
gemini.ps1 cannot be loaded because running scripts is disabled on this system
```

**Solution:**
1. Open PowerShell as Administrator:
   - Win key > type "PowerShell"
   - Right-click > "Run as administrator"
2. Run:
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```
3. Type `Y` and press Enter
4. Close PowerShell and open a normal terminal

**Alternative (if above doesn't work):**
Use `ExecutionPolicy Bypass` for current session only:
```powershell
powershell -ExecutionPolicy Bypass
```

### Issue: "gemini is not recognized"
**Symptoms:** Command not found after installation

**Solution for Windows:**
1. Find npm global path:
   ```bash
   npm config get prefix
   ```
2. Add to PATH: `{prefix}\node_modules\.bin`
3. Restart terminal

**Solution for macOS:**
1. Find npm global path:
   ```bash
   npm config get prefix
   ```
2. Add to `.zshrc` or `.bash_profile`:
   ```bash
   export PATH="$PATH:$(npm config get prefix)/bin"
   ```
3. Reload: `source ~/.zshrc`

### Issue: API Key not working
**Symptoms:** Authentication errors, "API key invalid"

**Solutions:**

**Check 1: Verify environment variable is set**
- Windows: `echo %GEMINI_API_KEY%`
- macOS: `echo $GEMINI_API_KEY`

If it shows nothing, the variable isn't set correctly.

**Check 2: Restart terminal**
Environment variables only load when terminal starts. Close and reopen terminal.

**Check 3: Verify API key validity**
1. Go to https://aistudio.google.com/app/apikey
2. Check if key exists and is enabled
3. Generate new key if needed

**Check 4: Copy-paste issues**
- Make sure no extra spaces when copying key
- No quotes needed in environment variable value
- Key should be exactly as shown in Google AI Studio

**Windows specific:**
```bash
# Set in current session (temporary)
set GEMINI_API_KEY=your-actual-key

# Permanent: Use Environment Variables GUI
```

**macOS specific:**
```bash
# Make sure you used correct syntax
export GEMINI_API_KEY="your-actual-key"  # Quotes are OK here
```

### Issue: Rate limit / Quota exceeded
**Symptoms:** "Resource exhausted" or "Quota exceeded" errors

**Solution:**
- Free tier has usage limits
- Wait 1-2 minutes between heavy requests
- If frequently hitting limits, consider paid tier
- Check quota at https://aistudio.google.com/app/apikey

---

## Network / Firewall Issues

### Issue: Can't download packages (npm, extensions, etc.)
**Symptoms:** Timeouts, network errors during installation

**Solutions:**
1. Check internet connection
2. Try different network (mobile hotspot as test)
3. Disable VPN temporarily
4. Check company firewall settings
5. Try npm with different registry:
   ```bash
   npm config set registry https://registry.npmjs.org/
   ```

### Issue: Corporate proxy blocking access
**Symptoms:** "ETIMEDOUT", "ECONNREFUSED" errors

**Solution:**
Configure npm proxy:
```bash
npm config set proxy http://proxy.company.com:8080
npm config set https-proxy http://proxy.company.com:8080
```

Ask IT department for correct proxy settings.

---

## VS Code Terminal Issues

### Issue: Wrong shell is being used
**Symptoms:** Commands don't work in integrated terminal

**Solution:**
1. Open Settings: `Ctrl/Cmd + ,`
2. Search: `terminal.integrated.defaultProfile`
3. Set to:
   - Windows: PowerShell or Command Prompt
   - macOS: zsh or bash

### Issue: Terminal won't open
**Symptoms:** Terminal panel is blank or shows error

**Solution:**
1. Try: `Ctrl/Cmd + Shift + P` > "Terminal: Kill All Terminals"
2. Then: `Ctrl/Cmd + `` to open new terminal
3. If still broken, restart VS Code

---

## General Tips

### When Stuck
1. **Read error messages carefully** - they often tell you exactly what's wrong
2. **Restart everything** - Terminal, VS Code, even your computer
3. **Check spelling** - Command names, paths, API keys
4. **Search the error** - Copy error message to Google
5. **Ask your trainer/PIC** - Don't stay blocked!

### Before Asking for Help
Have this information ready:
- Operating system (Windows 10/11, macOS version)
- What command you ran
- Full error message (screenshot is helpful)
- What you've already tried

### Still Having Issues?
Contact your assigned PIC (Person In Charge) or raise your hand during the session!
