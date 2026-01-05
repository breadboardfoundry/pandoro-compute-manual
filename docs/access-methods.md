# Access Methods

Pandoro provides two browser-based methods to access your machine. No local software installation required.

## SSH in Browser

**URL**: `https://ssh001.pandoro.today/` (replace `001` with your machine number)

The browser-based SSH terminal provides a traditional command-line interface directly in your web browser.

### When to Use SSH

- Running scripts and commands
- Managing files via command line
- Monitoring processes with `htop` or `nvidia-smi`
- Quick tasks that don't require a full IDE

### Tips

- Use [tmux](tmux-guide.md) to keep sessions alive during disconnects
- The terminal supports copy/paste (Ctrl+Shift+C / Ctrl+Shift+V on most browsers)
- Resize your browser window to adjust terminal dimensions

## VSCode in Browser

**URL**: `https://code001.pandoro.today/` (replace `001` with your machine number)

A full Visual Studio Code environment running in your browser, connected directly to your machine.

### When to Use VSCode

- Editing code with syntax highlighting and IntelliSense
- Managing files with a graphical file browser
- Running Jupyter notebooks
- Downloading files to your local machine (see [File Management](file-management.md))
- Using integrated terminal alongside code editing

### Features Available

- **File Explorer**: Browse and manage files in the left sidebar
- **Integrated Terminal**: Access the command line without leaving VSCode
- **Extensions**: Install Python, Jupyter, and other extensions
- **Git Integration**: Built-in version control support

### Getting Started with VSCode

1. Open your VSCode URL in a browser
2. Complete authentication (GitHub or email passcode)
3. The file explorer shows your home directory by default
4. Open the integrated terminal with `` Ctrl+` `` or via the menu

## Choosing Between SSH and VSCode

| Task | Recommended |
|------|-------------|
| Quick command execution | SSH |
| Code editing | VSCode |
| File downloads | VSCode |
| Long-running training jobs | SSH + tmux |
| Jupyter notebooks | VSCode |
| Monitoring GPU usage | Either |

## Network Considerations

Both interfaces run entirely in your browser. Performance depends on:

- Your internet connection stability
- Browser memory (close unused tabs for better performance)
- Using a modern browser (Chrome, Firefox, Edge recommended)
