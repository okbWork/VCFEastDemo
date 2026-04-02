# VCF East Demo - CMS Application

A menu-driven CMS REXX application for the IBM VCF East Demo booth, providing banner printing, games, and utilities.

## Quick Start

From the CMS command line, type:
```
VCFHOME
```

That's it! No setup required.

## Requirements

- Files must be on your A-disk (191) with filetype EXEC:
  - VCFHOME EXEC A
  - VCFPRINT EXEC A
  - VCFGAMES EXEC A
  - VCFMISC EXEC A

## Features

### 1. Banner Printing
Print custom text banners in various fonts:
- **Cursive** - Landscape text
- **Gothic** - Landscape text
- **Blockhead** - Landscape text
- **BIGWORD2** - Landscape text
- **Tinysign** - Portrait text

The application generates the banner and automatically submits it to the printer.

### 2. Games
Play classic games:
- Space Invaders
- SUBHUNT
- BLACKJACK
- Mastermind
- Checkers
- KALAH

### 3. Miscellaneous Applications
Utility programs:
- Digital Clock
- Boogie!
- Couch

## Navigation

- Enter a **number** (1-6 depending on menu) to select an option
- Enter **X** to return to the previous menu or exit
- Press **ENTER** after each selection

## How It Works

### Banner Printing Process
1. Select font (1-5)
2. Enter your message (keep it around 20 characters)
3. The application runs: `font message` (e.g., `gothic hello world`)
4. Then automatically prints with: `PRINT font LISTING`

### Games and Applications
Simply select the number and the program launches immediately.

## Files

- `vcfhome.exec` - Main menu
- `vcfprint.exec` - Banner printing module
- `vcfgames.exec` - Games menu
- `vcfmisc.exec` - Miscellaneous applications menu

## Technical Details

- Pure CMS REXX implementation
- No ISPF dependencies
- Uses VMFCLEAR for screen management
- Direct CMS command execution
- Automatic error handling

## Troubleshooting

### "Command not found" error
Ensure:
1. Files are on your A-disk (191)
2. Files have filetype EXEC
3. Your A-disk is accessed

Check with: `LISTFILE * EXEC A`

### Game or font not available
If a game or font command fails, that program is not installed on your system. The application will return you to the menu to try another option.

### Print command fails
If printing fails, the banner will still be displayed on screen. The LISTING file may need to be printed manually with: `PRINT fontname LISTING`

## Notes

- All user input is case-insensitive
- The application loops until you exit with X
- Screen clears between menus for better readability
- Each module returns to its parent menu when finished
