# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a Windows desktop environment configuration using GlazeWM (tiling window manager) and Zebar (status bar). The setup optimizes a dual-monitor workspace with intelligent application routing and purple-themed styling.

## Architecture
- **GlazeWM**: Main window manager configuration in `glazewm/config.yaml`
- **Zebar**: Status bar widget system in `zebar/` directory with multiple themes
- **Configuration pattern**: YAML-based configs with HTML/CSS/JavaScript widgets

### Theme Architecture Types
1. **HTML/CSS Themes** (`personal-rose-pine-base`, `dotfile-bar`): Simple HTML templates with CSS styling
2. **Svelte Themes** (`personalized-zebar`, `neobrutal-zebar`): Full Svelte applications with TypeScript, build systems
3. **React Themes** (`quiet-velvet`): React applications with Vite build system
4. **Legacy Themes** (`ajay-professional`): Traditional HTML with VBS/PowerShell scripts

### Build System Integration
- **Svelte themes**: Use `vite.config.ts`, `svelte.config.js`, support hot reload during development
- **Package management**: `package.json` with npm scripts for `dev`, `build`, `preview` commands
- **Asset compilation**: CSS processing via PostCSS, Tailwind CSS integration where applicable
- **Static generation**: Builds produce `index.html` and assets in `_app/` directory

## Key Files
- `glazewm/config.yaml` - Primary window manager configuration
- `zebar/settings.json` - Status bar startup configuration  
- `zebar/personalized-zebar/` - **Current active theme** - Customized neobrutal theme with numbered workspaces
- `zebar/personalized-zebar-backup/` - **Stable backup** of working personalized configuration
- `zebar/personal-rose-pine-base/` - Personal Rose Pine theme (HTML/CSS/JSON)
- `zebar/dotfile-bar/` - Original working theme (backup)
- `research-configs/` - Collection of cloned configuration repositories

## Common Operations

### Development Commands
```bash
# Zebar theme development (Svelte-based themes like personalized-zebar)
cd zebar/personalized-zebar
npm run dev          # Start development server with hot reload
npm run build        # Build theme for production
npm run preview      # Preview built theme

# Check configuration syntax
type glazewm\errors.log     # Check GlazeWM config parsing errors
type zebar\errors.log       # Check Zebar widget/theme errors

# Theme switching
# Update zebar/settings.json startupConfigs.pack value to switch themes
# Available themes: personalized-zebar, neobrutal-zebar, quiet-velvet, ajay-professional

# Restart services (via keybindings in WM)
# alt+shift+r - Restart GlazeWM to apply config changes
# Zebar restarts automatically with config changes
```

### Testing Configuration Changes
```bash
# Validate YAML syntax before applying
# Backup current config before major changes
# Test window rules with: alt+shift+i (show window info overlay in GlazeWM)
```

### Workspace Architecture
- **Workspaces 1-4**: Primary monitor (external display) for main productivity
- **"laptop" workspace**: Laptop monitor for auxiliary tasks like email
- **Keybindings**: `alt+1-4` for primary workspaces, `alt+l` for laptop workspace

### Window Rules System
The configuration uses complex window matching rules:
- Process name matching (e.g., `OUTLOOK.EXE`)
- Window title regex patterns
- Window class filtering
- Auto-floating vs tiling decisions

### Status Bar Integration
Zebar runs as startup command and provides system information display. Widget configuration follows zpack format with HTML templates and CSS styling.

## Configuration Patterns

### YAML Escaping
When editing window rules with regex patterns, escape backslashes properly:
```yaml
# Correct
window_class: "Microsoft\\.WindowsStore.*"
# Incorrect (causes parsing errors)  
window_class: "Microsoft\.WindowsStore.*"
```

### Monitor Binding
- Use `bind_to_monitor: 1` for primary external monitor
- Use `bind_to_monitor: 0` for laptop monitor
- Coordinate workspace assignments with monitor bindings

### Application Routing
Applications are automatically routed to appropriate workspaces:
- Development tools → Workspace 1 (primary monitor)
- Email/communication → Laptop workspace  
- Creative/Office apps → Workspace 1 (primary monitor)

## Theme Configuration

### GlazeWM Styling
- **Focused border**: `#8839ef` (purple)
- **Unfocused border**: `#babbf1` (light purple)  
- **Transparency**: 85% opacity for non-focused windows
- **Gaps**: 50px top (status bar space), 15px others

### Zebar Theme Features (personalized-zebar)
- **Layout**: CSS Grid (3 equal columns) prevents center shifting when media appears
- **Workspace indicators**: Numbered squares (1,2,3,4,5) with colored backgrounds and glow effects
- **Color scheme**: Rose Pine with workspace 3 using `--rp-rose` for better visibility
- **App icons**: 1rem size with cyan glow for focused apps (`--rp-foam` color with text-shadow)
- **Widget consistency**: All groups use consistent heights with `right-group-element` class
- **Media widget**: Colorful play/pause buttons (teal for playing, red for not playing)
- **Network widget**: Added to left group (implementation needs refinement for proper activity tracking)
- **Removed widgets**: Audio device, battery, and network indicator from right group for cleaner appearance
- **Theme naming**: Fixed duplicate naming conflicts - main theme shows as "personalized-zebar" without "(2)" suffix

## Development Workflow & Best Practices

### Task Management
- **Always use TodoWrite tool** to track complex tasks and subtasks
- **Divide complex tasks** into smaller, manageable subtasks for efficient processing
- **Be mindful of token consumption** - prefer focused, incremental work over large operations
- **Complete todos immediately** after finishing tasks, don't batch completions

### Research and Development 
- **Always use Context7 MCP** to access GitHub repositories instead of WebFetch
- **Prioritize existing implementations** as reference before creating custom solutions
- **Study research-configs repository** - comprehensive collection of GlazeWM/Zebar configurations
- **Reference CONFIG_INDEX.md** for structured overview of available features and patterns
- **Focus on GlazeWM and Zebar** primarily - avoid creating custom icons, themes, fonts from scratch
- **Use existing configs** to create personalized themes based on user preferences

### Configuration Philosophy
- **Reuse and adapt** rather than reinvent
- **Component-based approach** - build from existing widgets and themes
- **User preference-driven** - customize based on explicit user instructions
- **Iterative development** - create base versions then refine progressively

### Available Resources
- **Context7 MCP**: Zebar (`/glzr-io/zebar`), themes (`/adriankarlen/rose-pine.zebar`, `/mushfikurr/overline-zebar`)
- **Local research repos**: `research-configs/` with 12+ configuration examples
- **Configuration index**: `research-configs/CONFIG_INDEX.md` with categorized features
- **Package ecosystem**: glazewm-js (if available), React/TypeScript/Vite toolchains

### Widget Component System
Zebar widgets follow a component-based architecture:
- **Provider system**: Glazewm, battery, network, media providers supply reactive data
- **Component structure**: Left/Center/Right groups with consistent height styling
- **Icon mapping**: `icon_map.json` maps process names to display icons
- **Theming variables**: CSS custom properties for colors, fonts, spacing
- **Responsive behavior**: CSS Grid prevents layout shifts when widgets appear/disappear

### Development Stack Preferences
1. **Modern web technologies**: React, TypeScript, Vite, Tailwind CSS
2. **Configuration formats**: zpack.json (modern), YAML (GlazeWM), HTML/CSS (widgets)
3. **Build systems**: Vite with hot reload, pnpm package management
4. **Styling**: CSS variables for theming, Tailwind utilities, component libraries

## Known Issues & Future Improvements

### Current Issues
- **Network Activity Widget**: Currently shows static fallback values (30% medium activity) instead of real-time network throughput
  - Requires time-based delta calculation for bytes sent/received
  - WiFi signal strength integration partially implemented
  - Planned for future refinement

### Completed Features
- ✅ Numbered workspace indicators with colored backgrounds and glow effects
- ✅ CSS Grid layout preventing center widget shifting
- ✅ Enhanced focused app icons with cyan glow
- ✅ Improved icon mappings for Edge, Outlook, and additional applications
- ✅ Colorful media widget play/pause buttons
- ✅ Theme naming conflicts resolved
- ✅ Consistent widget heights across all groups
- ✅ Clean right-side layout (removed redundant network indicator)

## Troubleshooting
- Check `glazewm/errors.log` for configuration parsing errors
- Check `zebar/errors.log` for status bar widget issues
- YAML syntax is strict - validate indentation and escaping
- Window matching rules are case-sensitive and regex-based
- For theme issues: Use "Empty cache and reload configs" in Zebar settings