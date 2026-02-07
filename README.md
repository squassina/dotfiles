# Noctalia Dotfiles

My personal configuration files for a modern Linux desktop using **Niri** and **MangoWC** Wayland compositors with the **noctalia** desktop shell.

## Overview

This repository contains my daily-driver configurations for:
- **Niri** - A scrollable-tiling Wayland compositor
- **MangoWC** - A high-performance Wayland compositor  
- **Noctalia Shell** - Modern desktop shell with panels, widgets, and theming

## What's Included

- Clean, consistent theming across both compositors
- Modular configuration files (easy to customize individual components)
- Well-documented keybindings with overlay support
- Dark theme optimized for long coding sessions
- Custom noctalia plugins for productivity and monitoring
- Audio visualizer, network indicator, pomodoro timer, and privacy indicator widgets

## Repository Structure

```
.
├── mango/              # MangoWC (Hyprland) configuration
│   ├── config.conf     # Main config with sourced modules
│   ├── keybindings.conf
│   ├── appearance.conf
│   ├── animations.conf
│   ├── layouts.conf
│   ├── input.conf
│   ├── env.conf
│   ├── init.conf
│   ├── screenshots.conf
│   └── noctalia.conf   # Noctalia theme integration
│
├── niri/               # Niri window manager configuration
│   ├── config.kdl      # Main config
│   ├── noctalia.kdl    # Noctalia theme colors
│   └── cfg/            # Modular config files
│       ├── keybinds.kdl
│       ├── display.kdl
│       ├── input.kdl
│       ├── layout.kdl
│       ├── rules.kdl
│       ├── misc.kdl
│       └── autostart.kdl
│
└── noctalia/           # Noctalia shell configuration
    ├── settings.json   # Main shell settings
    ├── colors.json     # Color scheme
    ├── plugins.json    # Plugin configuration
    ├── user-templates.toml
    ├── colorschemes/
    └── plugins/        # Custom plugins
        ├── fancy-audiovisualizer/
        ├── network-indicator/
        ├── pomodoro/
        └── privacy-indicator/
```

## Dependencies

### Core
- **Niri** - [https://github.com/YaLTeR/niri](https://github.com/YaLTeR/niri)
- **MangoWC** - [https://github.com/DreamMaoMao/mangowc](https://github.com/DreamMaoMao/mangowc)
- **Noctalia Shell** - [https://noctalia.dev](https://noctalia.dev)
- **QuickShell** (qs) - Required for noctalia

### Applications I Use
- `alacritty` - Terminal
- `brave` - Browser
- `thunar` - File manager
- `heroic` - Game launcher
- `cliphist` - Clipboard history

### Optional
- `wl-paste` - Wayland clipboard utilities
- `qt6ct` - Qt6 theming

## Installation

### 1. Clone this repo

```bash
git clone https://github.com/yourusername/dotfiles.git ~/dotfiles
cd ~/dotfiles
```

### 2. Backup your current configs

```bash
# Backup your current configurations
mkdir -p ~/.config/backup
cp -r ~/.config/niri ~/.config/backup/ 2>/dev/null
cp -r ~/.config/mango ~/.config/backup/ 2>/dev/null
cp -r ~/.config/noctalia ~/.config/backup/ 2>/dev/null
```

### 3. Link the configs

```bash
# Niri
ln -sf ~/dotfiles/niri ~/.config/niri

# MangoWC
ln -sf ~/dotfiles/mango ~/.config/mango

# Noctalia
ln -sf ~/dotfiles/noctalia ~/.config/noctalia
```

### 4. Install dependencies

Package names will vary depending on your distro:

```bash
# Arch example
sudo pacman -S niri alacritty brave-bin thunar wl-clipboard

# For noctalia, follow the official docs:
# https://docs.noctalia.dev/getting-started/installation/
```

### 5. Reload configs

```bash
# For Niri
niri msg reload-config

# For MangoWC - usually MOD+SHIFT+R or just restart the compositor
```

## Keybindings

### Main shortcuts

| Keybinding | Action |
|------------|--------|
| `MOD + Return` | Open terminal (Alacritty) |
| `MOD + Space` | Open app launcher |
| `MOD + Q` | Close window |
| `MOD + B` | Open browser (Brave) |
| `MOD + E` | Open file manager (Thunar) |
| `MOD + H` | Open game launcher (Heroic) |
| `MOD + Alt + L` | Lock screen |
| `MOD + Shift + Esc` | Show hotkey overlay |

`MOD` is the Super key (Windows key). Full keybinding lists are in [mango/keybindings.conf](mango/keybindings.conf) and [niri/cfg/keybinds.kdl](niri/cfg/keybinds.kdl).

## Customization

### Colors

Edit these files to change the theme:
- [noctalia/colors.json](noctalia/colors.json) - Main color definitions
- [niri/noctalia.kdl](niri/noctalia.kdl) - Niri colors
- [mango/noctalia.conf](mango/noctalia.conf) - MangoWC colors

### Keybindings

Add or modify keybindings here:
- **Niri:** [niri/cfg/keybinds.kdl](niri/cfg/keybinds.kdl)
- **MangoWC:** [mango/keybindings.conf](mango/keybindings.conf)

### Display settings

For Niri, edit [niri/cfg/display.kdl](niri/cfg/display.kdl). Get your output names with:
```bash
niri msg outputs
```

### Gaps and borders

- **Niri:** [niri/cfg/layout.kdl](niri/cfg/layout.kdl)
- **MangoWC:** [mango/appearance.conf](mango/appearance.conf)

## Plugins

I've included a few noctalia plugins that I use daily:
- **fancy-audiovisualizer** - Audio visualization with shader effects
- **network-indicator** - Shows network status in the bar
- **pomodoro** - Timer for focused work sessions
- **privacy-indicator** - Alerts when camera/mic are active

Configure them in [noctalia/plugins.json](noctalia/plugins.json).

## Notes

- All paths use `~` instead of hardcoded home directories, so these configs should work on any system
- Everything is split into modular files - you can tweak individual aspects without touching the main configs
- The noctalia theme is sourced in both compositors to keep things looking consistent
- Keybindings have descriptions that show up in the hotkey overlay (press MOD+SHIFT+ESC)

## License

MIT License - See [LICENSE](LICENSE) for details.

## Thanks

- [Niri](https://github.com/YaLTeR/niri) by YaLTeR
- [Noctalia](https://noctalia.dev) by the Noctalia team
- Inspired by warm, cozy dark themes

---

Feel free to use these configs however you want. If they help you out, drop a star!
