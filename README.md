# BigLinux Nano Configuration

This package provides a custom nano editor configuration for BigLinux, offering an enhanced editing experience with a beautiful blue theme while maintaining nano's characteristic simplicity.

## Features

- Elegant blue color theme inspired by BigLinux branding
- Enhanced text readability with improved contrast
- Full syntax highlighting for various programming languages
- Automatic indentation
- Tab size set to 2 spaces
- Automatic tab to spaces conversion
- Line numbers enabled
- Enhanced navigation with F1 help key
- Multi-buffer support for editing multiple files
- Position log to remember cursor position between sessions
- Better visibility with file position indicator
- Intuitive keyboard shortcuts for common operations

## Configuration File

The main configuration file `/etc/nanorc` contains the following settings:

```bash
## Behavior settings
set autoindent
set constantshow
set historylog
set positionlog
set tabsize 2
set tabstospaces
set unix

## Show help bar at bottom
unset nohelp
set multibuffer

## BigLinux theme colors - improved contrast
set titlecolor brightwhite,blue
set statuscolor brightwhite,blue
set errorcolor brightwhite,red
set selectedcolor black,brightcyan
set stripecolor ,blue
set numbercolor brightcyan
set keycolor brightcyan
set functioncolor brightblue

## Better visibility options
set constantshow
set linenumbers
set indicator

## Syntax highlighting
include "/usr/share/nano/*.nanorc"

## Intuitive keyboard shortcuts
bind ^Q exit all
bind ^F whereis all
bind ^L findnext all
bind F3 findnext all
bind ^C copy main
bind ^V paste all
bind ^Y cut all
bind ^G gotoline main
bind ^/ comment main
```

## Keyboard Shortcuts

The configuration includes intuitive keyboard shortcuts:

- **F1**: Display help screen
- **Ctrl+Q**: Exit
- **Ctrl+F**: Find text
- **Ctrl+L** or **F3**: Find next occurrence
- **Ctrl+C**: Copy text (must select with Alt+A first)
- **Ctrl+V**: Paste text
- **Ctrl+Y**: Cut text
- **Ctrl+G**: Go to line number
- **Ctrl+/**: Comment/uncomment line
- **Alt+A**: Start text selection

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

## Syntax Highlighting

This package includes extensive syntax highlighting support for numerous programming languages and file formats. All syntax definitions from `/usr/share/nano/*.nanorc` are automatically included.

## Troubleshooting

- If text selection is not working as expected, remember to use **Alt+A** to start selection, then arrow keys to select, and **Ctrl+K** to cut or delete the selected text
- For permission issues when editing system files, remember to use `sudo` when necessary
- If you experience configuration problems, you can always restore the original backup

## Contributing

Suggestions and contributions are welcome! Feel free to open an issue or submit a pull request to improve the BigLinux nano experience.
