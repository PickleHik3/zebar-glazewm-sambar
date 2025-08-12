# Comprehensive Zebar Widget Reference

This document provides a complete reference of all available Zebar widgets, both official providers and community-created components.

## Official Zebar Providers

### Core System Providers
- **audio** - Audio device control and volume management
  - `defaultPlaybackDevice.volume` - Current volume level
  - `setVolume(level)` - Set volume programmatically
  - Access to all audio devices and their properties

- **battery** - Battery status and power information
  - `chargePercent` - Battery charge percentage
  - `isCharging` - Charging status
  - `powerSource` - Current power source
  - `designCapacity` - Battery design capacity

- **cpu** - CPU usage and performance metrics
  - `usage` - Current CPU usage percentage
  - `frequency` - Current CPU frequency
  - `logicalCoreCount` - Number of logical cores
  - `physicalCoreCount` - Number of physical cores

- **date** - Date and time formatting
  - `formatted` - Formatted date/time string
  - `new` - JavaScript Date object
  - Customizable formatting patterns (e.g., "yyyy LLL dd ccc", "hh:mm:ss a")

- **disk** - Disk usage and storage information
  - `usage` - Disk usage percentage
  - `freeBytes` - Available free space
  - `totalBytes` - Total disk capacity

- **glazewm** - Window manager integration
  - `allWorkspaces` - All available workspaces
  - `currentWorkspaces` - Currently visible workspaces
  - `focusedWorkspace` - Currently focused workspace
  - `focusedContainer` - Currently focused window/container
  - `tilingDirection` - Current tiling direction
  - `bindingModes` - Active binding modes
  - `runCommand(cmd)` - Execute GlazeWM commands

- **host** - System host information
  - `hostname` - System hostname
  - `osName` - Operating system name
  - `osVersion` - OS version string
  - `friendlyOsVersion` - Human-readable OS version
  - `bootTime` - System boot timestamp

- **ip** - Network IP address information
  - `address` - Current IP address
  - `approxCity` - Approximate city location
  - `approxCountry` - Approximate country location

- **keyboard** - Keyboard layout and input status
  - `layout` - Current keyboard layout
  - `capsLock` - Caps Lock status
  - `numLock` - Num Lock status

- **komorebi** - Komorebi window manager integration
  - Similar to GlazeWM provider for Komorebi users
  - Workspace and window management commands

- **media** - Media player control and information
  - `currentSession` - Current media session
  - `allSessions` - All available media sessions
  - `title` - Currently playing track title
  - `artist` - Currently playing artist
  - `isPlaying` - Playback status
  - `togglePlayPause()` - Toggle play/pause
  - `next()` - Skip to next track
  - `previous()` - Go to previous track

- **memory** - System memory usage
  - `usage` - Memory usage percentage
  - `freeBytes` - Available free memory
  - `usedBytes` - Currently used memory
  - `totalBytes` - Total system memory

- **network** - Network connectivity and traffic
  - `defaultInterface` - Default network interface
  - `interfaces` - All network interfaces
  - `traffic` - Network traffic statistics
  - Connection status and bandwidth information

- **systray** - System tray icon management
  - `icons` - Array of system tray icons
  - Icon interaction and management capabilities
  - Support for custom icon actions

- **weather** - Weather information and forecasting
  - `status` - Current weather status
  - `celsiusTemp` - Temperature in Celsius
  - `fahrenheitTemp` - Temperature in Fahrenheit
  - `humidity` - Humidity percentage
  - `windSpeed` - Wind speed
  - Weather condition icons and descriptions

## Community Widget Components

### Overline Zebar Theme Components

#### Media Control Widget
**File**: `research-configs/overline-zebar/src/components/media/Media.tsx`
- **Features**:
  - Multi-session media control with Alt+Click session cycling
  - Play/pause/next/previous controls with keyboard shortcuts
  - Progress bar with seek functionality
  - Animated title scrolling for long track names
  - Support for multiple media players simultaneously

- **Keyboard Shortcuts**:
  - Click: Toggle play/pause
  - Shift+Click: Previous track
  - Ctrl+Click: Next track
  - Alt+Click: Cycle between media sessions

#### Volume Control Widget
**File**: `research-configs/overline-zebar/src/components/volume/VolumeControl.tsx`
- **Features**:
  - Interactive volume slider with smooth animations
  - Mouse wheel volume adjustment
  - Visual volume level indicators (muted/low/medium/high)
  - Click-outside-to-close functionality
  - Shift+Click to toggle mute

- **Interactions**:
  - Click: Show/hide volume slider
  - Wheel: Adjust volume in 3% increments
  - Shift+Click: Toggle between 0% and 100% volume

#### System Tray Widget
**File**: `research-configs/overline-zebar/src/components/systray/Systray.tsx`
- **Features**:
  - Expandable carousel for system tray icons
  - Configurable icon cutoff limit (default: 4 visible)
  - Smooth expand/collapse animations
  - Shift+Click to toggle expansion

#### Window Title Widget
**File**: `research-configs/overline-zebar/src/components/windowTitle/WindowTitle.tsx`
- **Features**:
  - Dynamic window title display with fallback to workspace name
  - Window process name copying (Alt+Click)
  - Window control buttons (minimize, maximize, close)
  - Smart title truncation for long window titles
  - Special handling for applications like Spotify

- **Advanced Features**:
  - Process exclusion list for special applications
  - Title regex splitting for cleaner display
  - Animated transitions between window focus changes

#### Workspace Controls Widget
**File**: `research-configs/overline-zebar/src/components/WorkspaceControls.tsx`
- **Features**:
  - Interactive workspace switcher with visual feedback
  - Mouse wheel navigation between workspaces
  - Animated workspace indicator bubble
  - Support for custom workspace display names
  - Smooth transitions with spring animations

#### System Statistics Widget
**File**: `research-configs/overline-zebar/src/components/stat/Stat.tsx`
- **Features**:
  - Dual display modes: ring and inline
  - Customizable thresholds for color coding
  - Support for CPU, memory, disk, and custom metrics
  - Animated value transitions
  - Color-coded alerts based on usage levels

### WM Zebar Theme Components

#### Comprehensive Status Bar
**File**: `research-configs/wm/zebar/src/App.tsx`
- **Features**:
  - Full-featured status bar with all major system components
  - Toggleable media information display
  - Interactive volume control with slider
  - Weather integration with condition-specific icons
  - Battery status with color-coded indicators
  - Scrolling text for long media titles
  - Nerd Font icon integration

- **Interactive Elements**:
  - Workspace buttons with click navigation
  - Volume slider toggle
  - Media control buttons (play/pause/next/previous)
  - Weather information tooltip
  - Media info toggle switch

### Catppuccin Theme Components

#### Status Badge System
**File**: `research-configs/glazewm-catppuccin/src/features/status-badge/components/status-badge.tsx`
- **Features**:
  - Themed status badges with Catppuccin color palette
  - Icon-based status indicators
  - Consistent styling across all system metrics
  - Configurable color schemes per badge type

#### Minimal Status Bar
**File**: `research-configs/glazewm-catppuccin/src/App.tsx`
- **Features**:
  - Clean, minimal design with essential information
  - Weather status with condition-specific icons
  - Tiling direction toggle button
  - Date and time display with custom formatting
  - Binding mode indicators

## Advanced Professional Themes

### Ajay-056's Professional GlazeWM Config
**Repository**: `https://github.com/Ajay-056/glazewm-config`

#### Professional System Integration Features
- **Multi-Provider System**: 11 integrated providers with custom refresh intervals
  - Network, GlazeWM, CPU, Date, Battery, Memory, Weather, Host, IP, Disk, Audio
- **Interactive Shell Integration**: VBS/PowerShell/AHK script execution via UI buttons
- **Smart Status Indicators**: Threshold-based color coding for system metrics
- **Advanced Network Display**: Real-time upload/download speeds with signal-strength icons
- **Battery Intelligence**: Charging indicators, cycle count tracking, color-coded status
- **Action Center Integration**: Custom widgets launch Windows system utilities
- **Task Manager Integration**: Direct system utility launching

#### Technical Innovations
```javascript
// Dynamic threshold-based styling
className={output.cpu.usage > 85 ? 'high-usage' : ''}

// Advanced network icon selection
function getNetworkIcon(networkOutput) {
  switch (networkOutput.defaultInterface?.type) {
    case 'ethernet': return <i className="nf nf-md-ethernet_cable"></i>;
    case 'wifi':
      if (networkOutput.defaultGateway?.signalStrength >= 80) {
        return <span className="nf nf-md-wifi_strength_4"></span>;
      }
      // Progressive signal strength indication
  }
}

// Shell script integration
output.glazewm.runCommand('shell-exec %userprofile%/.glzr/zebar/script/OpenTaskManager.vbs')
```

### Quiet Velvet Taskbar (ariafatah0711)
**Repository**: `https://github.com/ariafatah0711/zebar-glazewm`

#### Advanced Taskbar Experience Features
- **Spotify API Integration**: Real-time playback with OAuth2 token management
  - Automatic token refresh and localStorage persistence
  - Playback controls (requires Spotify Premium)
  - Currently playing track display with hover controls
- **Google Search Widget**: Integrated search with workspace/file manager launching
- **Settings Widget System**: Dynamic widget visibility with persistent preferences
- **Shortcut Widget Framework**: Configurable command execution with icon mapping
- **Active App Highlighting**: Visual feedback for focused applications
- **Taskbar Previews**: Windows-style hover previews

#### Configuration System
```javascript
// External config.js for sensitive data
export default {
    spotifyClientId: '<YOUR-SPOTIFY-CLIENT-ID>',
    spotifyClientSecret: '<YOUR-SPOTIFY-CLIENT-SECRET>',
    spotifyRefreshToken: '<YOUR-SPOTIFY-REFRESH-TOKEN>',
    explorerPath: '<YOUR-EXPLORER-PATH>',
    powershellPath: '<YOUR-POWERSHELL-PATH>'
}

// Settings widget with state management
<Settings widgetObj={[
    { name: 'XWidget', changeState: setShowXWidget },
    { name: 'YWidget', changeState: setShowYWidget }
]}/>

// Configurable shortcuts
<Shortcut commandRunner={output.glazewm.runCommand}
          commands={['focus --workspace 2', `shell-exec ${config.powershellPath}`]}
          iconClass="nf-cod-terminal_powershell" 
          name="Powershell" />
```

### Neobrutal Zebar (adriankarlen/kylekce fork)
**Repository**: `https://github.com/kylekce/neobrutal-zebar`

#### Svelte-Powered Design System Features
- **Svelte Framework**: Modern reactive framework with superior performance
- **Advanced Theming Engine**: Four complete themes (Rosé Pine, Catppuccin, Nord, Material)
- **CSS Variable Configuration**: Extensive customization via CSS custom properties
- **Process Icon Mapping**: Dynamic application icons with focus indicators
- **Power Control Integration**: Shutdown/restart buttons with GlazeWM shell execution
- **Dynamic Coloring**: Contextual state-based color changes
- **Styling Recipes**: Pre-configured aesthetic combinations
- **Media Display**: Browser and music player integration
- **System Information Meters**: Advanced CPU/memory/battery monitoring

#### Advanced CSS Variable System
```css
/* Contextual theming with CSS variables */
:root {
  /* System metrics with threshold colors */
  --memory: var(--rp-iris);
  --memory-medium: var(--rp-gold);
  --memory-high: var(--rp-love);
  --cpu: var(--rp-rose);
  --cpu-high-usage: var(--rp-love);
  
  /* Workspace-specific coloring */
  --ws-1: var(--rp-gold);
  --ws-2: var(--rp-love);
  --ws-3: var(--rp-pine);
  --ws-4: var(--rp-foam);
  --ws-5: var(--rp-iris);
  
  /* Volume level indicators */
  --volume-muted: var(--rp-foam);
  --volume-low: var(--rp-iris);
  --volume-medium: var(--rp-pine);
  --volume-high: var(--rp-rose);
}

/* Styling recipes */
--radius: 9999px; /* Soft Brutal aesthetic */
--border-size: 1px;
--shadow-size-bar: 0px; /* Clean minimal look */
```

#### GlazeWM Power Integration
```yaml
# Shell execution for power controls
general:
  shell_exec:
    enabled: true

# Custom keybindings for power management
keybindings:
  - command: "shell-exec shutdown /s /t 0"
    bindings: ["Alt+F4"]
  - command: "shell-exec shutdown /r /t 0"  
    bindings: ["Alt+Shift+F4"]
```

## Advanced Widget Patterns

### Animation Libraries
- **Framer Motion**: Used extensively for smooth transitions and spring animations
- **React Transition Group**: Alternative animation system for state changes
- **CSS Animations**: Custom animations with Tailwind CSS classes

### State Management Patterns
- **React Hooks**: useState, useEffect for local component state
- **Custom Hooks**: useAutoTiling, usePlayPause, useMeasure for specialized functionality
- **Context API**: ConfigContext for theme and configuration management

### Styling Approaches
- **Tailwind CSS**: Utility-first CSS framework with custom color schemes
- **CSS-in-JS**: Style objects and dynamic styling
- **Custom CSS Classes**: Traditional CSS with BEM-like naming conventions
- **Theme Variables**: CSS custom properties for consistent theming

### Interactive Features
- **Keyboard Shortcuts**: Alt, Shift, Ctrl modifiers for advanced interactions
- **Mouse Events**: Click, wheel, hover interactions
- **Touch Support**: Mobile-friendly touch interactions
- **Drag and Drop**: Advanced widget positioning and customization

### Performance Optimizations
- **React.memo**: Memoization for expensive components
- **useCallback**: Callback memoization for event handlers
- **Virtualization**: Large list rendering optimization
- **Debouncing**: Input and scroll event optimization

## Widget Development Best Practices

### Component Structure
```typescript
// Standard widget component pattern
interface WidgetProps {
  provider: ProviderOutput | null;
  config?: WidgetConfig;
}

export function Widget({ provider, config }: WidgetProps) {
  if (!provider) return null;
  
  // Component logic
  return (
    <div className="widget-container">
      {/* Widget content */}
    </div>
  );
}
```

### Provider Integration
```typescript
// Using Zebar providers
const providers = createProviderGroup({
  system: { type: "cpu" },
  memory: { type: "memory" },
  glazewm: { type: "glazewm" }
});

function useProviders() {
  const [output, setOutput] = useState(providers.outputMap);
  
  useEffect(() => {
    providers.onOutput(() => setOutput(providers.outputMap));
  }, []);
  
  return output;
}
```

### Theme Integration
```typescript
// Theme-aware component
interface ThemedComponentProps {
  theme?: 'light' | 'dark' | 'auto';
  accentColor?: string;
}

function ThemedComponent({ theme = 'auto', accentColor }: ThemedComponentProps) {
  const computedTheme = theme === 'auto' ? detectSystemTheme() : theme;
  
  return (
    <div 
      className={`themed-component ${computedTheme}`}
      style={{ '--accent-color': accentColor }}
    >
      {/* Component content */}
    </div>
  );
}
```

## Widget Configuration Examples

### Basic System Monitor
```typescript
// Simple CPU/Memory monitor
function SystemMonitor() {
  const providers = createProviderGroup({
    cpu: { type: "cpu" },
    memory: { type: "memory" }
  });
  
  const [output, setOutput] = useState(providers.outputMap);
  
  useEffect(() => {
    providers.onOutput(() => setOutput(providers.outputMap));
  }, []);
  
  return (
    <div className="system-monitor">
      <div className="metric">
        CPU: {Math.round(output.cpu?.usage ?? 0)}%
      </div>
      <div className="metric">
        Memory: {Math.round(output.memory?.usage ?? 0)}%
      </div>
    </div>
  );
}
```

### Advanced Media Player
```typescript
// Media player with session management
function MediaPlayer() {
  const [currentSessionIdx, setCurrentSessionIdx] = useState(0);
  
  const handleSessionCycle = (e: React.MouseEvent) => {
    if (e.altKey) {
      setCurrentSessionIdx(prev => 
        prev < allSessions.length - 1 ? prev + 1 : 0
      );
    }
  };
  
  return (
    <div className="media-player" onClick={handleSessionCycle}>
      {/* Media controls */}
    </div>
  );
}
```

This reference provides a comprehensive overview of all available Zebar widgets and components, from official providers to advanced community implementations. Each component can be customized and integrated into your Zebar configuration based on your specific needs and preferences.