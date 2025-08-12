# Complete Zebar Theme Collection with GlazeWM Configuration

A comprehensive collection of advanced Zebar themes with optimized GlazeWM configuration for dual-monitor Windows setups.

## 🎨 Included Themes

### 1. **Personal Rose Pine Base** (`personal-rose-pine-base/`)
- Custom Rose Pine theme with 15% height reduction
- Proper window management configuration
- Purple-themed styling with transparency effects

### 2. **Adrian Karlen Rose Pine** (`adriankarlen-rose-pine/`)
- Authentic Rose Pine theme adapted to modern zpack format
- Original styling with optimized window behavior
- Minimal and elegant design

### 3. **Neobrutal Zebar** (`neobrutal-zebar/`)
- **Framework**: Svelte + Tailwind CSS
- **Features**: 4 themes (Rosé Pine, Catppuccin, Nord, Material)
- **Advanced**: CSS variable configuration, process icons, power controls
- **Build**: Pre-built and ready to use

### 4. **Quiet Velvet** (`quiet-velvet/`)
- **Framework**: React + Vite
- **Features**: Spotify integration, Google Search widget, Settings system
- **Advanced**: Active app highlighting, taskbar previews, shortcut widgets
- **Build**: Pre-built with config template

### 5. **Ajay Professional** (`ajay-professional/`)
- **Framework**: React (ES6 modules)
- **Features**: 11 system providers, shell script integration
- **Advanced**: System utility launching, threshold-based styling, network monitoring
- **Scripts**: VBS/PowerShell/AHK automation included

## 🚀 Installation on Home PC

### Prerequisites
1. **GlazeWM**: Download from [GitHub](https://github.com/glzr-io/glazewm/releases)
2. **Zebar**: Download from [GitHub](https://github.com/glzr-io/zebar/releases)
3. **Git**: For cloning this repository

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/zebar-glazewm-config.git

# Navigate to the directory
cd zebar-glazewm-config

# Copy to GlazeWM/Zebar directory (Windows)
xcopy /E /I . "%USERPROFILE%\.glzr"

# Or copy manually to: C:\Users\YourUsername\.glzr\
```

### Manual Installation
1. Download/clone this repository
2. Copy entire contents to `C:\Users\YourUsername\.glzr\`
3. Start GlazeWM and Zebar
4. Select desired theme in Zebar settings

## ⚙️ Configuration Details

### Window Management Settings
All themes are configured with:
- **Height**: 42px (consistent across all themes)
- **Dock to Edge**: Enabled, top edge
- **Window Margin**: 0px for seamless integration
- **Monitor Selection**: All monitors

### GlazeWM Configuration
- **Dual-monitor optimized**: Primary monitor (workspaces 1-4), Laptop monitor (laptop workspace)
- **Application routing**: Intelligent workspace assignment
- **Purple theme**: Focused `#FB6060`, unfocused `#22272D`
- **Transparency**: 85% opacity for non-focused windows

## 🎯 Theme-Specific Features

### Neobrutal Zebar
- **CSS Variables**: Extensive theming system
- **Power Controls**: Shutdown/restart integration
- **Process Icons**: Dynamic application icons
- **Styling Recipes**: Pre-configured aesthetics

### Quiet Velvet
- **Spotify API**: Real-time playback control (requires setup)
- **Google Search**: Integrated search with workspace switching
- **Settings Widget**: Dynamic widget visibility
- **Config Required**: Edit `src/config.js` for API credentials

### Ajay Professional
- **System Integration**: Task Manager, Action Center, custom scripts
- **Advanced Monitoring**: Network traffic, battery cycles, threshold alerts
- **Shell Scripts**: VBS/PowerShell automation included
- **Multi-Provider**: 11 integrated system providers

## 📚 Documentation

- **CLAUDE.md**: Project development history and configuration details
- **ZEBAR_WIDGETS_REFERENCE.md**: Comprehensive widget reference
- **CONFIG_INDEX.md**: Research and feature analysis

## 🔧 Customization

### Spotify Integration (Quiet Velvet)
1. Create Spotify app at https://developer.spotify.com/dashboard
2. Get refresh token at https://alecchen.dev/spotify-refresh-token/
3. Update `quiet-velvet/src/config.js`:
```javascript
export default {
    spotifyClientId: 'your-client-id',
    spotifyClientSecret: 'your-client-secret',
    spotifyRefreshToken: 'your-refresh-token',
    explorerPath: 'C:\\Windows\\explorer.exe',
    powershellPath: 'C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe'
}
```

### Theme Switching
Update `zebar/settings.json` to point to desired theme:
```json
{
  "themes": [
    "theme-name/zpack.json"
  ]
}
```

## 🎨 Available Themes
- `personal-rose-pine-base/zpack.json`
- `adriankarlen-rose-pine/zpack.json`
- `neobrutal-zebar/zpack.json`
- `quiet-velvet/zpack.json`
- `ajay-professional/zpack.json`

## 📋 Requirements

- **Windows 10/11**: Required for GlazeWM
- **Node.js**: For rebuilding themes (optional)
- **PowerShell**: For system scripts (Ajay Professional)
- **Spotify Premium**: For playback controls (Quiet Velvet)

## 🤝 Credits

- **Neobrutal**: [kylekce/neobrutal-zebar](https://github.com/kylekce/neobrutal-zebar)
- **Quiet Velvet**: [ariafatah0711/zebar-glazewm](https://github.com/ariafatah0711/zebar-glazewm)
- **Ajay Professional**: [Ajay-056/glazewm-config](https://github.com/Ajay-056/glazewm-config)
- **Adrian Karlen**: [adriankarlen/rose-pine.zebar](https://github.com/adriankarlen/rose-pine.zebar)

## 📝 License

Themes retain their original licenses. Configuration modifications are provided as-is.

---

*This configuration was curated and optimized for consistent Windows desktop integration with advanced Zebar theming capabilities.*