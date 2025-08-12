# GlazeWM & Zebar Configuration Index

*Generated: 2025-01-12*

This index catalogs available configurations, themes, widgets, and functionalities from various repositories for GlazeWM and Zebar customization.

## 📁 Repository Structure Overview

### Core GlazeWM Configurations
| Repository | Focus | Key Features |
|------------|-------|--------------|
| `GlazeWM` | Basic starter config | Standard GlazeWM setup with Zebar integration |
| `Glazewm-configs` | Advanced configs | TypeScript scripts, multiple boilerplates |
| `glazewm-zebar-config` | Simple integration | Basic YAML config with PowerShell scripts |
| `glazewm-catppuccin` | Catppuccin theme | React/TypeScript, modern build system |
| `glzr` | Minimal setup | Clean default configuration |
| `wm` | Modern React setup | shadcn/ui, Tailwind CSS integration |

### Zebar Themes & Widgets
| Repository | Theme/Style | Technology Stack | Special Features |
|------------|-------------|------------------|-----------------|
| `rose-pine.zebar` | Rose Pine aesthetic | YAML config | Color scheme variables, minimal setup |
| `overline-zebar` | Feature-rich widget | React, TypeScript | Media controls, systray, volume slider |
| `laggggg-zebar-config` | Simple HTML/CSS | Vanilla implementation | Lightweight, basic styling |
| `zebar-config` | Starter template | JavaScript/HTML | Clean foundation |
| `zebar-glass` | Glass/transparent | HTML/CSS | Transparency effects |
| `zebarConfig` | Multi-WM support | HTML/CSS | GlazeWM + Komorebi support |
| `zebar_neon_theme` | Neon aesthetic | HTML/CSS | Colorful neon styling |

## 🎨 Available Themes & Color Schemes

### Rose Pine Variants
- **Location**: `rose-pine.zebar/`
- **Colors**: Natural pine-scented theme with Soho vibes
- **Customization**: CSS variables for easy color swapping
- **WM Support**: GlazeWM, Komorebi

### Catppuccin
- **Location**: `glazewm-catppuccin/`
- **Technology**: React + TypeScript + Vite
- **Features**: Status badges, modern component architecture
- **Build System**: Vite with hot reload

### Neon Theme
- **Location**: `zebar_neon_theme/`
- **Style**: Bright, colorful neon aesthetic
- **Implementation**: Pure HTML/CSS

### Glass/Transparent
- **Location**: `zebar-glass/`
- **Effect**: Transparency and glass-like appearance
- **Extras**: Volume mixer integration

## 🔧 Advanced Widget Features

### overline-zebar Capabilities
- **Media Controls**: Play/pause, previous/next track support
- **System Tray**: Expandable carousel with system icons  
- **Volume Control**: Interactive slider with mute toggle
- **Window Management**: Current window display with controls
- **Workspace Controls**: Click to focus, scroll to switch
- **Auto-tiling**: WebSocket integration for advanced tiling
- **Search Integration**: Flow Launcher integration

### Technical Implementations
- **React Components**: Modern component-based architecture
- **TypeScript Support**: Type-safe development
- **Tailwind CSS**: Utility-first styling
- **Hot Reload**: Development workflow optimization
- **Config Management**: JSON-based configuration

## 📜 Scripting & Automation

### TypeScript/JavaScript Features
- **Location**: `Glazewm-configs/glazewm/scripts/javaScript/`
- **Modules**:
  - `helper_functions.ts` - Utility functions
  - `query_status.ts` - Status querying
  - `workspace_focus.ts` - Focus management
  - `workspace_swap.ts` - Workspace switching

### PowerShell Scripts
- **Location**: `glazewm-zebar-config/zebar/scripts/`
- **Features**: 
  - `sign.ps1` - Script signing utilities
  - Batch file launchers (`start.bat`)

## 🛠 Build Systems & Development

### Modern Development Stack
- **Vite**: Fast build tool with hot reload
- **TypeScript**: Type-safe development
- **ESLint**: Code quality enforcement
- **Tailwind CSS**: Utility-first styling
- **shadcn/ui**: Modern component library

### Package Managers
- **pnpm**: Fast, disk space efficient (preferred)
- **npm**: Standard Node.js package manager

## 🔧 Configuration Patterns

### Zebar Configuration Types
1. **zpack.json**: Modern widget packaging format
2. ***.zebar.json**: Legacy configuration format  
3. **settings.json**: Global Zebar settings
4. **YAML configs**: GlazeWM-style configuration

### GlazeWM Configuration Features
- **Multi-monitor support**: Monitor binding configurations
- **Workspace management**: Custom workspace definitions
- **Window rules**: Automatic window placement
- **Keybinding modes**: Context-sensitive controls
- **Visual effects**: Border styling, transparency

## 📦 Widget Component Library

### Common Components
- **Status Badges**: System status indicators
- **Progress Bars**: Visual progress representation
- **Sliders**: Interactive controls (volume, etc.)
- **Chips**: Compact information display
- **Buttons**: Interactive elements
- **Dividers**: Visual separation

### Advanced Components
- **Expanding Carousel**: Systray icon management
- **Conditional Panels**: Dynamic UI sections
- **Ring Charts**: Circular progress indicators
- **Media Players**: Music/video controls

## 🎛 System Integration

### Supported Providers
- **GlazeWM**: Primary window manager integration
- **Komorebi**: Alternative WM support  
- **System Audio**: Volume control, device management
- **Media Session**: Current playing detection
- **System Tray**: Native Windows integration
- **Network Status**: Connection monitoring
- **Battery**: Power management (laptops)
- **CPU/Memory**: Performance monitoring
- **Weather**: Location-based weather data

### External Tool Integration
- **Flow Launcher**: Application launcher
- **Auto-tiling**: Advanced window management
- **PowerShell**: Script execution
- **Volume Mixer**: System audio controls

## 🚀 Getting Started Recommendations

### For Beginners
1. Start with `rose-pine.zebar` for simple theming
2. Use `glazewm-zebar-config` for basic integration
3. Customize colors via CSS variables

### For Advanced Users  
1. Explore `overline-zebar` for full-featured widgets
2. Study `glazewm-catppuccin` for modern React patterns
3. Build custom widgets using TypeScript boilerplates

### For Developers
1. Use `Glazewm-configs/zebar/boilerplate-*` as starting points
2. Leverage Vite + TypeScript for fast development
3. Implement hot reload for efficient iteration

## 💡 Customization Guidelines

### Theme Adaptation
- Use CSS variables for easy color changes
- Maintain consistent spacing and typography
- Consider both light and dark variants

### Component Development
- Follow React best practices for reusable components
- Implement proper TypeScript typing
- Use Tailwind utilities for responsive design

### Integration Best Practices
- Test with multiple monitor setups
- Ensure keyboard accessibility
- Optimize for performance with large datasets

---

*This index serves as a reference for building personalized GlazeWM and Zebar configurations. All repositories are available in `C:\Users\AmalVajdan\.glzr\research-configs\` for detailed exploration.*