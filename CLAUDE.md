# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a Windows desktop environment configuration using GlazeWM (tiling window manager) and Zebar (status bar). The setup optimizes a dual-monitor workspace with intelligent application routing and purple-themed styling.

## Architecture
- **GlazeWM**: Main window manager configuration in `glazewm/config.yaml`
- **Zebar**: Status bar widget system in `zebar/` directory
- **Configuration pattern**: YAML-based configs with HTML/CSS widgets

## Key Files
- `glazewm/config.yaml` - Primary window manager configuration
- `zebar/settings.json` - Status bar startup configuration  
- `zebar/personal-rose-pine-base/` - Personal Rose Pine theme (HTML/CSS/JSON)
- `zebar/dotfile-bar/` - Original working theme (backup)
- `research-configs/` - Collection of cloned configuration repositories

## Common Operations

### Testing Configuration Changes
```bash
# Check GlazeWM config syntax (if errors.log exists after reload)
type glazewm\errors.log

# Restart GlazeWM to apply changes (via keybinding)
# Use alt+shift+r in the actual WM
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
- **Focused border**: `#8839ef` (purple)
- **Unfocused border**: `#babbf1` (light purple)  
- **Transparency**: 85% opacity for non-focused windows
- **Gaps**: 50px top (status bar space), 15px others

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

### Development Stack Preferences
1. **Modern web technologies**: React, TypeScript, Vite, Tailwind CSS
2. **Configuration formats**: zpack.json (modern), YAML (GlazeWM), HTML/CSS (widgets)
3. **Build systems**: Vite with hot reload, pnpm package management
4. **Styling**: CSS variables for theming, Tailwind utilities, component libraries

## Troubleshooting
- Check `glazewm/errors.log` for configuration parsing errors
- Check `zebar/errors.log` for status bar widget issues
- YAML syntax is strict - validate indentation and escaping
- Window matching rules are case-sensitive and regex-based