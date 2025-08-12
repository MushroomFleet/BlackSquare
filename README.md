# BlackSquare

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![.NET](https://img.shields.io/badge/.NET-6.0-purple.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![Release](https://img.shields.io/badge/version-1.0.0-green.svg)

**A lightweight Windows application for on-screen censoring with draggable overlay rectangles.**

Perfect for live streaming, screen recording, presentations, or any situation where you need to quickly hide sensitive information on your screen.

## ✨ Features

- 🖥️ **System Tray Integration** - Minimal UI footprint, runs in background
- ⌨️ **Global Hotkeys** - Create and clear overlays with customizable keyboard shortcuts
- 🖱️ **Drag & Drop Overlays** - Click and drag to create censoring rectangles
- 📐 **Multiple Overlays** - Create unlimited overlay rectangles simultaneously
- 🎨 **Customizable Colors** - Change overlay color with hex color codes
- 💾 **Persistent Settings** - Your preferences are saved and restored
- 🔧 **Enhanced Settings UI** - Visual hotkey picker with real-time validation
- 🚀 **Windows Integration** - Optional startup with Windows

## 📋 System Requirements

> **⚠️ Important:** This application requires **Microsoft .NET 6.0 Desktop Runtime**

- **OS:** Windows 10 or Windows 11 (64-bit)
- **Runtime:** [Microsoft .NET 6.0 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/6.0)
- **Resources:** ~5-10MB RAM, minimal CPU usage

## 🚀 Installation

### For End Users

1. **Download** the latest installer from [Releases](../../releases)
2. **Run** `BlackSquare-Setup-v1.0.0.exe`
3. **Follow** the setup wizard
4. **Launch** from Start Menu or desktop

The installer will automatically check for .NET 6.0 and guide you through installation if needed.

### For Developers

```bash
# Clone the repository
git clone https://github.com/yourusername/BlackSquare.git
cd BlackSquare

# Restore dependencies
dotnet restore

# Build the application
dotnet build

# Run in development mode
dotnet run
```

## 🎯 Quick Start

1. **Launch BlackSquare** → Application minimizes to system tray
2. **Create Overlay** → Press `Ctrl+Shift+B` (default) and drag to create rectangle
3. **Clear All** → Press `Ctrl+Shift+C` (default) to remove all overlays
4. **Configure** → Right-click system tray icon for settings

## 📖 Usage

### Creating Overlays
- Press and hold your configured hotkey (default: `Ctrl+Shift+B`)
- Click and drag on screen to create rectangle
- Release to place the overlay
- Overlay remains until manually cleared

### Managing Overlays
- **Individual Removal:** Right-click any overlay → Remove
- **Clear All:** Use clear hotkey (`Ctrl+Shift+C`) or system tray menu
- **Test Mode:** System tray menu → "Test Create Overlay"

### Customizing Settings
Access via system tray right-click → Settings:

- **Hotkey Configuration:**
  - Visual modifier selection (Ctrl, Alt, Shift, Win)
  - Key dropdown with all available options
  - "Record" button for direct key capture
  - Real-time validation with visual feedback

- **Color Settings:**
  - Hex color input (e.g., `#FF0000`)
  - Live color preview
  - Validation indicators

## 🛠️ Development

### Project Structure
```
BlackSquare/
├── Models/              # Data models (Settings, OverlayRectangle)
├── Services/            # Business logic (OverlayService, HotkeyManager)
├── Utilities/           # Helper classes (GlobalHotkey)
├── Windows/             # UI windows (Main, Settings, Overlay)
├── App.xaml[.cs]        # Application entry point
└── MainWindow.xaml[.cs] # Main window (hidden, tray only)
```

### Technology Stack
- **Framework:** .NET 6.0 WPF
- **UI:** Windows Presentation Foundation (WPF)
- **Packaging:** Inno Setup installer
- **Architecture:** MVVM pattern with services

### Building Release
```bash
# Build release version
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true

# Or use the automated script
.\build-distribution.bat
```

### Key Components
- **Global Hotkey System:** Win32 API integration for system-wide hotkeys
- **Overlay Management:** WPF windows with transparent backgrounds
- **Settings Persistence:** JSON-based configuration storage
- **System Tray:** NotifyIcon with context menu integration

## 📦 Distribution

The project includes complete distribution setup:
- **Standalone executable** (155MB, self-contained)
- **Professional installer** (Inno Setup script included)
- **Automated build process** (`build-distribution.bat`)

See [DISTRIBUTION.md](DISTRIBUTION.md) for detailed distribution guide.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

### Development Setup
1. Install [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
2. Clone this repository
3. Open in Visual Studio or VS Code
4. Build and run

### Code Style
- Follow standard C# conventions
- Use meaningful variable and method names  
- Comment complex logic
- Maintain MVVM pattern

## 🐛 Troubleshooting

### Common Issues

**Hotkeys not working:**
- Check for conflicting applications
- Try different modifier combinations
- Restart application after changes

**Application won't start:**
- Ensure .NET 6.0 Desktop Runtime is installed
- Check Windows Event Viewer for errors
- Try running as administrator (temporarily)

**Overlays not appearing:**
- Verify hotkey configuration
- Ensure minimum drag area (5x5 pixels)
- Test with system tray menu option

## 🔒 Privacy & Security

- **Offline Operation:** No network connectivity required
- **Local Storage:** Settings stored in `%AppData%\BlackSquare\`
- **No Telemetry:** Zero data collection or transmission
- **Standard Privileges:** Runs without administrator rights

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📊 Technical Details

- **Memory Usage:** ~5-10MB baseline + ~100KB per overlay
- **Startup Time:** <2 seconds on modern hardware
- **File Size:** ~155MB (self-contained executable)
- **Dependencies:** Newtonsoft.Json for settings serialization

## 🏷️ Version History

### v1.0.0 (Current)
- Initial release
- Global hotkey support with enhanced picker UI
- Drag-and-drop overlay creation
- Customizable colors and settings
- System tray integration
- Professional installer with .NET runtime check

---

**Built with ❤️ for the Windows community**

[Download Latest Release](../../releases) | [Report Bug](../../issues) | [Request Feature](../../issues)
