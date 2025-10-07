# Visual Studio Code Installation Guide

## For Windows

### Download and Install
1. Visit https://code.visualstudio.com/
2. Click the **Download for Windows** button
3. Run the downloaded installer (`VSCodeUserSetup-{version}.exe`)
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose installation location (default is recommended)
   - **Important:** Check these boxes:
     - ✅ Add "Open with Code" action to Windows Explorer file context menu
     - ✅ Add "Open with Code" action to Windows Explorer directory context menu
     - ✅ Add to PATH (this is important!)
5. Click **Install** and wait for completion
6. Launch VS Code

### Verify Installation
1. Open Command Prompt (Win + R, type `cmd`, press Enter)
2. Type: `code --version`
3. You should see version information

## For macOS

### Download and Install
1. Visit https://code.visualstudio.com/
2. Click the **Download for Mac** button
3. Open the downloaded `.zip` file
4. Drag **Visual Studio Code.app** to your **Applications** folder
5. Launch VS Code from Applications

### Add to PATH (Optional but Recommended)
1. Open VS Code
2. Press `Cmd + Shift + P` to open Command Palette
3. Type `shell command` and select **Shell Command: Install 'code' command in PATH**
4. Restart your terminal

### Verify Installation
1. Open Terminal
2. Type: `code --version`
3. You should see version information

## First Launch Setup

### Install Essential Extensions
Once VS Code is open, install these recommended extensions:

1. **Open Extensions panel:** Click the Extensions icon in the left sidebar (or press `Ctrl+Shift+X` / `Cmd+Shift+X`)

2. **Search and install:**
   - **Prettier - Code formatter** (for code formatting)
   - **ESLint** (for JavaScript/TypeScript linting)
   - **Live Server** (for local development server)
   - Any language-specific extensions you need (Python, Go, etc.)

### Configure Basic Settings
1. Open Settings: `File > Preferences > Settings` (or `Ctrl+,` / `Cmd+,`)
2. Recommended settings:
   - **Auto Save:** Set to `afterDelay`
   - **Format On Save:** Enable this
   - **Tab Size:** 2 or 4 (based on preference)

## Troubleshooting

### Windows: "code is not recognized as a command"
- Reinstall VS Code and ensure "Add to PATH" is checked
- Or manually add to PATH:
  1. Search for "Environment Variables" in Windows
  2. Edit PATH variable
  3. Add: `C:\Users\{YourUsername}\AppData\Local\Programs\Microsoft VS Code\bin`

### macOS: "command not found: code"
- Follow the "Add to PATH" steps above
- Or add manually to `.zshrc` or `.bash_profile`:
  ```bash
  export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
  ```

### Performance Issues
- Disable unnecessary extensions
- Exclude large folders from file watching (Settings > Files: Exclude)
- Increase memory limit if needed

## Next Steps
Once VS Code is installed, proceed to install Google Gemini CLI. See `installation-guide-gemini.md`
