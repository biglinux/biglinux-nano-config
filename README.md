# BigLinux Nano Configuration

This package provides a custom nano editor configuration for BigLinux, offering an enhanced editing experience while maintaining nano's characteristic simplicity.

## Features

- Full mouse support for copy/paste in terminal
- Automatic indentation
- Tab size set to 4 spaces
- Automatic tab to spaces conversion
- Line numbers enabled
- Smart Home key (moves to first non-space character)
- Automatic file backup
- Soft wrapping of long lines
- Maximum width of 80 columns
- Command history
- Syntax highlighting for various programming languages

## Configuration File

The main configuration file `/etc/nanorc` contains the following settings:

```bash
# Include existing syntax definitions
include "/usr/share/nano/*.nanorc"

# Enable automatic indentation
set autoindent

# Set tab size to 4 spaces
set tabsize 4

# Convert tabs to spaces
set tabstospaces

# Disable automatic line wrapping
set nowrap

# Mouse support (commented to work correctly in terminal)
#set mouse

# Show line numbers
set linenumbers

# Smart Home key
set smarthome

# Save command history
set historylog

# Enable backups
set backup

# Enable soft line wrapping
set softwrap

# Limit screen width to 80 columns
set fill 80
```

## Backup and Customization

During installation, the package automatically:
1. Backs up your original `/etc/nanorc` file as `/etc/nanorc.bkp`
2. Installs the new configuration in `/etc/nanorc`

### Customization Options

You have several options to customize or restore settings:

1. **Modify current configuration:**
   - Edit the `/etc/nanorc` file directly
   ```bash
   sudo nano /etc/nanorc
   ```

2. **Restore original configuration:**
   - Remove the package using pacman
   ```bash
   sudo pacman -R biglinux-nano-config
   ```
   - The original file will be automatically restored

3. **Use manual backup:**
   - Original backup is available at `/etc/nanorc.bkp`
   - You can restore it manually:
   ```bash
   sudo cp /etc/nanorc.bkp /etc/nanorc
   ```

## Troubleshooting

- If mouse copy/paste isn't working, verify that the `set mouse` line is commented out in the configuration file
- For permission issues when editing files, remember to use `sudo` when necessary
- If you experience configuration problems, you can always restore the original backup

## Contributing

Suggestions and contributions are welcome! Feel free to open an issue or submit a pull request.
