# Google Gemini CLI Installation Guide

## Prerequisites
- Visual Studio Code installed (see `installation-guide-vscode.md`)
- Google account (for Gemini API access)

## For Windows

### Step 1: Install Node.js (if not already installed)
1. Visit https://nodejs.org/
2. Download the **LTS (Long Term Support)** version (Node.js 20 or higher required)
3. Run the installer and follow the wizard (use default settings)
4. Verify installation:
   - Open Command Prompt
   - Type: `node --version` (should show v20.x.x or higher)
   - Type: `npm --version`

### Step 2: Set Execution Policy
Before installing Gemini CLI, you need to allow script execution:

1. **Open PowerShell as Administrator:**
   - Press Win key
   - Type `PowerShell`
   - Right-click on **Windows PowerShell**
   - Select **Run as administrator**

2. **Set execution policy:**
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

3. Type `Y` and press Enter to confirm

### Step 3: Install Google Gemini CLI
1. Open Command Prompt or PowerShell (doesn't need to be admin)
2. Run:
   ```bash
   npm install -g @google/gemini-cli
   ```
3. Wait for installation to complete

### Step 4: Verify Installation
```bash
gemini --version
```

### Step 5: Authentication

**Option 1: Login with Google (Recommended)**

This is the easiest method and gives you better rate limits (60 requests/min):

1. Open Command Prompt or PowerShell
2. Run:
   ```bash
   gemini
   ```
3. When prompted, choose **"Login with Google"**
4. Follow the browser prompts to sign in with your Google account
5. Done! You're authenticated and ready to use Gemini

**Option 2: Use API Key (Alternative)**

If you prefer using an API key instead:

1. Go to https://aistudio.google.com/app/apikey
2. Sign in with your Google account
3. Click **Create API Key**
4. Copy the API key

5. **Set environment variable (Windows):**
   - Search for "Environment Variables" in Windows
   - Click **Environment Variables** button
   - Under **User variables**, click **New**
   - Variable name: `GEMINI_API_KEY`
   - Variable value: Paste your API key
   - Click **OK** to save
   - **Restart Command Prompt/PowerShell** for changes to take effect

   Note: API key has lower rate limits (100 requests/day)

## For macOS

### Step 1: Install Homebrew (if not already installed)

Homebrew is a package manager for macOS that makes installing developer tools easy.

**Check if you have Homebrew:**
```bash
brew --version
```

**If you don't have Homebrew, install it:**
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Follow the on-screen instructions. You may need to:
- Enter your Mac password
- Press Enter to continue
- Follow any additional setup commands shown at the end

### Step 2: Install Gemini CLI

**Option 1: Using Homebrew (Easiest - Recommended)**

```bash
brew install gemini-cli
```

This automatically handles dependencies including Node.js. Skip to Step 4: Authentication.

**Option 2: Using npm**

1. **Install Node.js first (if not already installed):**

   Using Homebrew:
   ```bash
   brew install node
   ```

   Or download from website:
   - Visit https://nodejs.org/
   - Download the **LTS** version (Node.js 20 or higher required)
   - Run the installer

2. **Verify Node.js installation:**
   ```bash
   node --version  # Should show v20.x.x or higher
   npm --version
   ```

3. **Install the Gemini CLI package:**
   ```bash
   npm install -g @google/gemini-cli
   ```

### Step 3: Verify Installation
```bash
gemini --version
```

### Step 4: Authentication

**Option 1: Login with Google (Recommended)**

This is the easiest method and gives you better rate limits (60 requests/min):

1. Open Terminal
2. Run:
   ```bash
   gemini
   ```
3. When prompted, choose **"Login with Google"**
4. Follow the browser prompts to sign in with your Google account
5. Done! You're authenticated and ready to use Gemini

**Option 2: Use API Key (Alternative)**

If you prefer using an API key instead:

1. Go to https://aistudio.google.com/app/apikey
2. Sign in with your Google account
3. Click **Create API Key**
4. Copy the API key

5. **Add to shell configuration:**

   For **Zsh** (default on newer macOS):
   ```bash
   echo 'export GEMINI_API_KEY="your-api-key-here"' >> ~/.zshrc
   source ~/.zshrc
   ```

   For **Bash**:
   ```bash
   echo 'export GEMINI_API_KEY="your-api-key-here"' >> ~/.bash_profile
   source ~/.bash_profile
   ```

   Replace `your-api-key-here` with your actual API key.

   Note: API key has lower rate limits (100 requests/day)

## Test Your Setup

### Test in Terminal
1. Open a **new** terminal/command prompt window
2. Run:
   ```bash
   gemini
   ```
3. You should see the Gemini CLI interface
4. Type a test message like "Hello, can you help me code?"
5. Press `Ctrl+C` to exit

### Test in VS Code
1. Open VS Code
2. Open the integrated terminal: `View > Terminal` (or `Ctrl+`` / `Cmd+``)
3. Run the same test:
   ```bash
   gemini
   ```

## Troubleshooting

### Windows: "gemini is not recognized as a command"
**Solution 1: Check npm global path**
```bash
npm config get prefix
```
Add the returned path + `\node_modules\.bin` to your PATH environment variable.

**Solution 2: Reinstall**
```bash
npm uninstall -g @google/gemini-cli
npm install -g @google/gemini-cli
```

### Windows: "Execution Policy" Error
If you see: `cannot be loaded because running scripts is disabled`

Run PowerShell as Administrator and execute:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### macOS: "command not found: gemini"
Check npm global bin path:
```bash
npm config get prefix
```

Add to your PATH in `.zshrc` or `.bash_profile`:
```bash
export PATH="$PATH:$(npm config get prefix)/bin"
```

### API Key Not Working
- Make sure you copied the entire key (no extra spaces)
- Verify the environment variable is set:
  - Windows: `echo %GEMINI_API_KEY%`
  - macOS: `echo $GEMINI_API_KEY`
- Restart your terminal/command prompt after setting environment variables
- Check API key is valid at https://aistudio.google.com/app/apikey

### Rate Limit Errors
Free tier has usage limits. If you hit them:
- Wait a few minutes
- Consider upgrading to paid tier if needed during heavy usage

## Usage Tips

### Basic Commands
```bash
# Start interactive session (default)
gemini

# Start in a specific directory
gemini /path/to/your/project

# Ask a non-interactive question
gemini -p "How do I create a React component?"

# Use a specific model
gemini -m gemini-2.0-flash

# Include specific directories
gemini --include-directories ../lib,../docs
```

### Best Practices
- Keep your API key secret (don't share or commit to git)
- Use specific prompts for better results
- Break complex tasks into smaller prompts

## Next Steps
You're ready to start coding with AI! See `prompting-best-practices.md` for tips on how to effectively use Gemini.
