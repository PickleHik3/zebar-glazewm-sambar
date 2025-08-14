# 📦 Installation Guide - GlazeWM & Zebar Configuration

Complete installation guide for setting up this GlazeWM and Zebar configuration on any Windows PC.

## 🎯 **What You'll Get**
- **GlazeWM**: Optimized dual-monitor tiling window manager configuration
- **Zebar**: Custom "personalized-zebar" theme with Rose Pine colors and numbered workspaces
- **Custom Layout System**: 75/25 master-stack keybindings with `Alt+Shift+M`
- **Professional Workspace**: Intelligent application routing and purple-themed styling

---

## 📋 **Prerequisites**

### **Required Software (Install These First):**
1. **GlazeWM** *(Tiling Window Manager)*
   - Download: [GitHub Releases](https://github.com/glzr-io/glazewm/releases)
   - Get the latest `.msi` installer

2. **Zebar** *(Status Bar)*
   - Download: [GitHub Releases](https://github.com/glzr-io/zebar/releases)  
   - Get the latest `.msi` installer

3. **Git** *(For cloning repository)*
   - Download: [git-scm.com](https://git-scm.com/downloads)
   - Required for installation process

4. **Node.js** *(For Svelte theme compilation)*
   - Download: [nodejs.org](https://nodejs.org/)
   - Choose LTS version (18.x or higher)
   - Required for `personalized-zebar` theme

---

## 🚀 **Installation Methods**

### **Method 1: One-Command Installation (Recommended)**

Open **Command Prompt** or **PowerShell** and run:

```bash
# Complete installation in one command block
cd C:\Users\%USERNAME%\ && git clone https://github.com/PickleHik3/zebar-glazewm-sambar.git && cd zebar-glazewm-sambar && mkdir "%USERPROFILE%\.glzr" 2>nul && xcopy /E /I /Y glazewm "%USERPROFILE%\.glzr\glazewm" && xcopy /E /I /Y zebar "%USERPROFILE%\.glzr\zebar" && copy CLAUDE.md "%USERPROFILE%\.glzr\" && copy README.md "%USERPROFILE%\.glzr\" && cd "%USERPROFILE%\.glzr\zebar\personalized-zebar" && npm install && npm run build && echo. && echo ✅ Installation Complete! Launch GlazeWM and Zebar now.
```

### **Method 2: Step-by-Step Installation**

#### **Step 1: Clone Repository**
```bash
cd C:\Users\%USERNAME%\
git clone https://github.com/PickleHik3/zebar-glazewm-sambar.git
cd zebar-glazewm-sambar
```

#### **Step 2: Copy Configuration Files**  
```bash
# Create GlazeWM/Zebar directory
mkdir "%USERPROFILE%\.glzr" 2>nul

# Copy configurations
xcopy /E /I /Y glazewm "%USERPROFILE%\.glzr\glazewm"
xcopy /E /I /Y zebar "%USERPROFILE%\.glzr\zebar"
copy CLAUDE.md "%USERPROFILE%\.glzr\"
copy README.md "%USERPROFILE%\.glzr\"
```

#### **Step 3: Build Zebar Theme (CRITICAL)**
```bash
# Navigate to theme directory
cd "%USERPROFILE%\.glzr\zebar\personalized-zebar"

# Install dependencies and build
npm install
npm run build
```

---

## ⚙️ **Post-Installation Setup**

### **1. Launch Applications**
1. **Start GlazeWM** from Start Menu or desktop shortcut
2. **Start Zebar** from Start Menu or desktop shortcut  
3. **Zebar should automatically load** the "personalized-zebar" theme

### **2. Verify Installation**
Check that your directory structure looks like this:
```
C:\Users\YourUsername\.glzr\
├── glazewm\
│   └── config.yaml              # GlazeWM configuration
├── zebar\
│   ├── personalized-zebar\      # Main theme (built)
│   │   ├── _app\               # Compiled assets (auto-generated)
│   │   ├── src\                # Source code  
│   │   ├── node_modules\       # Dependencies
│   │   └── package.json        # Theme config
│   ├── personalized-zebar-backup\  # Backup theme
│   └── settings.json           # Zebar configuration
├── CLAUDE.md                   # Development guide
└── README.md                   # Project overview
```

### **3. Test Custom Layout System**
1. **Open 2-3 windows** in any workspace
2. **Focus the window** you want as master
3. **Press `Alt + Shift + M`** multiple times
4. **Window should grow** to become master (75% width)

---

## 🔧 **Troubleshooting**

### **Issue: "Zebar theme not loading"**
**Solution:**
```bash
cd "%USERPROFILE%\.glzr\zebar\personalized-zebar"
npm run build
```
Then restart Zebar.

### **Issue: "GlazeWM config not working"**  
**Solution:**
1. Verify file exists: `%USERPROFILE%\.glzr\glazewm\config.yaml`
2. In GlazeWM, press `Alt + Shift + R` to reload config

### **Issue: "npm command not found"**
**Solution:**
1. Install Node.js from [nodejs.org](https://nodejs.org/)
2. Restart Command Prompt
3. Try installation again

### **Issue: "Permission denied during file copy"**
**Solution:**
1. Run Command Prompt as Administrator
2. Retry installation commands

### **Issue: "Wrong theme showing in Zebar"**
**Solution:**
1. Right-click Zebar in system tray
2. Select "Settings" → "Themes"  
3. Choose "personalized-zebar"
4. Click "Apply"

---

## 🎨 **Configuration Details**

### **GlazeWM Features:**
- **Workspaces 1-4**: Primary monitor (external display)
- **"laptop" workspace**: Laptop monitor for auxiliary tasks
- **Custom keybindings**: Arrow-based navigation with resize mode
- **Application routing**: Automatic workspace assignment
- **Layout system**: Custom 75/25 master-stack with `Alt+Shift+M`

### **Zebar Theme Features:**
- **Layout**: CSS Grid (3 columns) prevents center shifting
- **Workspace indicators**: Numbered squares (1,2,3,4,5) with glow effects  
- **Color scheme**: Rose Pine with enhanced visibility
- **App icons**: 1rem size with cyan glow for focused apps
- **Media controls**: Colorful play/pause buttons

### **Custom Layout Commands:**
- **`Alt + Shift + M`**: Master layout (grow focused window)
- **`Alt + Shift + Y`**: Enter layout mode
  - `M`: Master layout
  - `R`: Reset layout  
  - `+`/`-`: Fine adjustments
  - `Escape`: Exit
- **`Alt + Shift + 0`**: Reset all window sizes

---

## 🔄 **Auto-Start Setup (Optional)**

### **Method 1: Windows Startup Folder**
```bash
# Copy shortcuts to startup folder
copy "%USERPROFILE%\Desktop\GlazeWM.lnk" "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\"
copy "%USERPROFILE%\Desktop\Zebar.lnk" "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\"
```

### **Method 2: Task Scheduler (Advanced)**
1. Open **Task Scheduler**
2. Create **Basic Task** for GlazeWM
3. Set trigger to **"At startup"**  
4. Set action to **start GlazeWM executable**
5. Repeat for Zebar

---

## 📚 **Additional Resources**

- **CLAUDE.md**: Complete development guide and configuration patterns
- **README.md**: Project overview and feature descriptions
- **GlazeWM Docs**: [Official Documentation](https://github.com/glzr-io/glazewm)
- **Zebar Docs**: [Official Documentation](https://github.com/glzr-io/zebar)

---

## ⚡ **Quick Start Summary**

1. **Install**: GlazeWM + Zebar + Git + Node.js
2. **Run**: One-command installation from above
3. **Launch**: Start GlazeWM and Zebar  
4. **Test**: Press `Alt + Shift + M` to try custom layout
5. **Enjoy**: Professional dual-monitor workspace with custom theming!

---

**🎉 Installation Complete!** Your Windows desktop now has professional tiling window management with custom theming and advanced layout controls.