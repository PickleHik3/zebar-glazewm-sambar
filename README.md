# GlazeWM & Zebar Config sync

Optimized GlazeWM (tiling window manager) and Zebar (status bar) configuration for dual-monitor Windows setups.

## 🎯 Current Active Configuration

### **Personalized Zebar Theme** (`personalized-zebar/`)
- **Framework**: Svelte + Tailwind CSS
- **Features**: Numbered workspace indicators, Rose Pine color scheme, enhanced media controls
- **Layout**: CSS Grid (3 equal columns) prevents center shifting
- **Workspace indicators**: Colored squares (1,2,3,4,5) with glow effects
- **App icons**: 1rem size with cyan glow for focused apps
- **Widget consistency**: All groups use consistent heights

### **GlazeWM Configuration** (`glazewm/`)
- **Dual-monitor optimized**: Primary monitor (workspaces 1-4), Laptop workspace
- **Purple theme**: Focused border `#9bdbf9`, unfocused `#7d5e8c`
- **Transparency**: 70% opacity for non-focused windows
- **Application routing**: Intelligent workspace assignment for productivity
- **Keybindings**: Arrow-based navigation with resize mode

## 📁 Directory Structure

```
├── glazewm/                    # GlazeWM window manager configuration
│   └── config.yaml            # Main configuration file
├── zebar/                     # Zebar status bar configuration
│   ├── personalized-zebar/    # Current active theme (Svelte-based)
│   ├── personalized-zebar-backup/ # Stable backup configuration
│   └── settings.json          # Zebar startup configuration
└── custom-glazewm-configs/    # Working directory for custom configurations

Local only (not in git):
├── archived-themes/           # Collection of alternative themes
└── research-configs/          # Research and reference configurations
```

## ⚙️ Configuration Details

### Workspace Architecture
- **Workspaces 1-4**: Primary monitor (external display) for main productivity
- **"laptop" workspace**: Laptop monitor for auxiliary tasks like email
- **Keybindings**: `alt+1-4` for primary workspaces, `alt+l` for laptop workspace

### Visual Styling
- **Zebar Height**: 42px with top docking
- **GlazeWM Gaps**: 5px top, 12px others with DPI scaling
- **Window Borders**: Blue focused (`#9bdbf9`), purple unfocused (`#7d5e8c`)
- **Transparency**: 70% opacity for non-focused windows
- **Corner Style**: Small rounded corners on Windows 11

### Application Routing
Applications are automatically routed to appropriate workspaces:
- **Development tools** → Workspace 1 (primary monitor)
- **Email/communication** → Laptop workspace
- **Creative/Office apps** → Workspace 1 (primary monitor)

## 📝 Documentation

- **CLAUDE.md**: Complete project development guide and configuration patterns

---

*Optimized dual-monitor Windows desktop environment with GlazeWM tiling and personalized Zebar theming.*
