# Scoop Bucket for 2b (Second Brain CLI)

This is a [Scoop](https://scoop.sh) bucket for the **2b** (Second Brain) CLI application.

## Installation

Add this bucket to Scoop:

```powershell
scoop bucket add 2b https://github.com/DavidLabett/scoop-2b.git
```

**Note:** The `.git` extension is required for Scoop to recognize the URL.

Then install the application:

```powershell
scoop install 2b
```

## Usage

After installation, you can use the CLI:

```powershell
# Check version
SecondBrain.exe version

# Or if you have an alias set up
2b version
```

## Setting Up the `2b` Alias

By default, the application is installed as `SecondBrain.exe`. To use the shorter `2b` command, you can set up an alias using one of the following methods:

### Method 1: Using Scoop's Alias Feature (Recommended)

Scoop provides a built-in alias system:

```powershell
# Add the alias
scoop alias add 2b "SecondBrain.exe $args"

# Verify it was added
scoop alias list

# Test it
2b version
```

### Method 2: PowerShell Profile (Persistent Across Sessions)

Add the alias to your PowerShell profile for a permanent solution:

1. **Open your PowerShell profile:**
   ```powershell
   notepad $PROFILE
   ```
   
   If the file doesn't exist, create it:
   ```powershell
   New-Item -Path $PROFILE -Type File -Force
   notepad $PROFILE
   ```

2. **Add this function to your profile:**
   ```powershell
   # 2ND BRAIN CLI Alias (Scoop-installed)
   function 2b {
       & SecondBrain.exe $args
   }
   ```

3. **Save and reload your profile:**
   ```powershell
   . $PROFILE
   ```

4. **Test the alias:**
   ```powershell
   2b version
   ```

### Method 3: Command Prompt Alias (CMD)

For Command Prompt users, you can create a batch file or use DOSKEY:

1. **Create a batch file** `2b.bat` in a directory in your PATH:
   ```batch
   @echo off
   SecondBrain.exe %*
   ```

2. **Or use DOSKEY** (temporary, session-only):
   ```cmd
   doskey 2b=SecondBrain.exe $*
   ```

**Note:** Method 2 (PowerShell Profile) is recommended as it works across all PowerShell sessions and automatically uses the correct Scoop-installed version when you update.

## Update

To update to the latest version:

```powershell
scoop update 2b
```

## Uninstall

To remove the application:

```powershell
scoop uninstall 2b
```

## About

**2b** (Second Brain) is a RAG (Retrieval-Augmented Generation) Knowledge Base CLI tool that helps you manage and query your documents using AI.

- **Homepage**: https://github.com/DavidLabett/RAG-CLI-Tool
- **License**: MIT

## Manifest

The manifest file (`2b.json`) contains all the metadata needed for Scoop to install and manage the application.

