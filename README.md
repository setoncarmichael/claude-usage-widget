# Claude Usage Widget

A beautiful, highly customizable Windows desktop widget that displays your Claude.ai usage statistics in real-time with system tray integration.

**[SCREENSHOT: Main widget showing session and weekly usage]**

## Features

### Core Features
- 🎯 **Real-time Usage Tracking** - Monitor both 5-hour session and 7-day weekly usage limits
- 📊 **Visual Progress Bars** - Clean, gradient progress indicators with customizable colors
- ⏱️ **Countdown Timers** - Circular timers showing time until session/weekly reset
- 🔄 **Configurable Auto-refresh** - Adjustable update interval (10-300 seconds)
- 🎨 **Fully Customizable UI** - Toggle any element on/off, customize all colors and theme
- 📍 **Always on Top** - Stays visible across all workspaces
- 🔒 **Secure** - Encrypted credential storage using electron-store

### System Tray Integration
- 💾 **Live Tray Icon** - Real-time usage percentage displayed in system tray
- 🎨 **Customizable Tray Colors** - Independent color schemes for tray icon
- ⚙️ **Tray Update Interval** - Configurable refresh rate (10-300 seconds)
- 📊 **Switchable Metrics** - Display either session or weekly usage in tray
- 🔢 **Toggle Percentage Text** - Show/hide percentage number on tray icon

### Advanced Customization
- 🎨 **Theme Editor** - Customize background gradients, text colors, borders, and title bar
- 🖼️ **Element Visibility Controls** - Show/hide any UI element independently:
  - Section labels (Current Session / Weekly Limit)
  - Progress bars
  - Percentage text
  - Countdown circles
  - Time remaining text
- 📏 **Dynamic Resizing** - Window automatically adjusts to fit visible elements
- 💎 **Static or Gradient Colors** - Choose between static colors or gradient progressions
- 🎯 **Color Coding by Usage** - Different colors for normal (0-74%), warning (75-89%), and danger (90-100%)

### Application Settings
- 🚀 **Start on System Boot** - Automatically launch when Windows starts
- 🔽 **Start Minimized** - Begin in system tray without showing window
- 📌 **Close to Tray** - Minimize to tray instead of exiting application
- 💾 **Persistent Window Position** - Remembers and restores window location

## Installation

### Download Pre-built Release
1. Download the latest `Claude-Usage-Widget-Setup.exe` from [Releases](https://github.com/SlavomirDurej/claude-usage-widget/releases)
2. Run the installer
3. Launch "Claude Usage Widget" from Start Menu

### Build from Source

**Prerequisites:**
- Node.js 18+ ([Download](https://nodejs.org))
- npm (comes with Node.js)

**Steps:**

```bash
# Clone the repository
git clone https://github.com/yourusername/claude-usage-widget.git
cd claude-usage-widget

# Install dependencies
npm install

# Run in development mode
npm start

# Build installer for Windows
npm run build:win
```

The installer will be created in the `dist/` folder.

## Usage

### First Launch

1. Launch the widget
2. The app will attempt to auto-login using stored credentials
3. If no credentials exist, click "Login to Claude"
4. A browser window will open - login to your Claude.ai account
5. The widget will automatically capture your session
6. Usage data will start displaying immediately

**[SCREENSHOT: Login screen]**

### Widget Controls

**Title Bar:**
- **Drag** - Click and drag anywhere on the title bar to move the widget
- **Settings Icon** - Open the comprehensive settings panel
- **Refresh Icon** - Update usage data immediately
- **Minimize** - Hide to system tray
- **Close** - Minimize to tray or exit (depending on settings)

**[SCREENSHOT: Widget with controls highlighted]**

### System Tray

**Tray Icon:**
- Displays real-time usage percentage
- Color changes based on usage level (normal/warning/danger)
- Switches between session and weekly usage (configurable in settings)
- Updates independently with configurable interval

**Tray Menu (Right-click):**
- **Show/Hide Widget** - Toggle main window visibility
- **Refresh Usage** - Update data immediately
- **Re-login** - Clear credentials and login again
- **Settings** - Open settings panel
- **Exit** - Quit application completely

**[SCREENSHOT: System tray icon and menu]**

## Settings

Access settings by clicking the gear icon on the widget or via the system tray menu.

### Main Window Settings

#### Colors
Customize progress bar colors with gradient or static options:

**Static Color Mode:**
- Enable "Use Static Color" toggle
- Choose a single color for the progress bar (ignores usage levels)

**Gradient Mode (Default):**
- **Normal** (0-74% usage) - Default: Purple gradient (#8b5cf6 → #a78bfa)
- **Warning** (75-89% usage) - Default: Orange gradient (#f59e0b → #fbbf24)
- **Danger** (90-100% usage) - Default: Red gradient (#ef4444 → #f87171)

Each level has independent start and end colors for smooth gradients.

**[SCREENSHOT: Color customization panel]**

#### Theme
Customize the entire widget appearance:
- **Background Gradient** - Start and end colors
- **Text Colors** - Primary and secondary text
- **Title Bar** - Background color and opacity (0-100%)
- **Borders** - Border color and opacity (0-100%)

**[SCREENSHOT: Theme customization panel]**

#### Update Interval
- Range: 10-300 seconds (default: 30 seconds)
- Controls how often the main widget refreshes usage data
- Lower values = more current data, higher API usage
- Slider with real-time value display

#### Current Session Elements
Control visibility of each element in the Current Session section:
- **Show Current Session** - Master toggle for entire section
- **Show Label Text** - "CURRENT SESSION" label
- **Show Progress Bar** - Usage progress bar
- **Show Percentage Text** - Usage percentage number
- **Show Countdown Circle** - Circular timer graphic
- **Show Time Text** - Time remaining until reset

**[SCREENSHOT: Element visibility controls]**

#### Weekly Limit Elements
Identical controls for the Weekly Limit section:
- Master toggle to show/hide entire section
- Individual toggles for label, bar, percentage, circle, and time

**Example Configurations:**
- Minimal: Just progress bars (hide everything else)
- Data-rich: All elements visible (default)
- Custom: Any combination you prefer

### Tray Icon Settings

#### Display Mode
Choose which metric to display in the system tray:
- **Session Usage** (5-hour limit)
- **Weekly Usage** (7-day limit)

#### Update Interval
- Range: 10-300 seconds (default: 30 seconds)
- Independent from main widget update interval
- Tray icon updates on its own schedule

#### Show Percentage Text
- Toggle percentage number on/off in tray icon
- When disabled, shows only the colored ring

#### Colors
Separate color customization for tray icon:
- Static or gradient mode (same as main widget)
- Independent color schemes
- Normal/Warning/Danger levels

**[SCREENSHOT: Tray icon settings]**

### Application Settings

#### Start on System Boot
- Automatically launch widget when Windows starts
- Registers with Windows startup items
- Disable to manually start the widget

#### Start Minimized
- Launch hidden in system tray
- Widget won't show window on startup
- Access via tray icon

#### Close to Tray
- When enabled: Clicking X minimizes to tray
- When disabled: Clicking X exits application
- Minimize button always goes to tray

**[SCREENSHOT: Application settings]**

### Account

**Log Out** - Clears stored credentials and returns to login screen

## Understanding the Display

### Current Session (5-Hour Limit)
- **Progress Bar** - Visual representation of usage (0-100%)
- **Percentage** - Exact usage percentage
- **Countdown Circle** - Circular timer showing progress toward reset
- **Time Remaining** - Hours and minutes until session resets (e.g., "2h 34m")
- **Color Coding**:
  - Purple: Normal usage (0-74%)
  - Orange: High usage (75-89%)
  - Red: Critical usage (90-100%)

### Weekly Limit (7-Day Rolling Window)
- **Progress Bar** - Weekly usage from 0-100%
- **Percentage** - Exact weekly usage percentage
- **Countdown Circle** - Progress toward weekly reset
- **Time Remaining** - Days/hours until weekly reset (e.g., "3d 5h")
- Same color coding as session usage

**[SCREENSHOT: Usage display explanation with labels]**

## Window Behavior

### Dynamic Resizing
- Window automatically resizes based on visible elements
- Shows only what you've enabled in settings
- Maintains minimum size for readability
- Cannot be manually resized smaller than content

### Manual Resizing
- Drag edges to resize window
- Constraints: 320-600px width, 96-180px height
- Content stays centered at all sizes

### Position Persistence
- Window position saved automatically when moved
- Restored on next launch
- Per-display awareness

## Keyboard Shortcuts

Currently, the widget does not have keyboard shortcuts. This may be added in a future version.

## Troubleshooting

### "Login Required" keeps appearing
- Your Claude.ai session may have expired
- Click "Login to Claude" to re-authenticate
- Check that you're logging into the correct account
- Verify Claude.ai is accessible in your region

### Widget not updating
- Check your internet connection
- Click the refresh button manually
- Ensure Claude.ai API is accessible
- Try increasing update interval if experiencing rate limits
- Re-login from system tray menu

### Tray icon not showing/updating
- Check that "Show Percentage Text" is enabled to see text
- Verify update interval isn't too long
- Try changing display mode (session ↔ weekly)
- Restart the application

### Window too small/elements cut off
- Check element visibility settings
- Enable more elements to expand window
- Window automatically sizes to fit enabled elements
- Reset to defaults if layout seems broken

### Auto-start not working
- Verify "Start on System Boot" is enabled in settings
- Check Windows Task Manager > Startup tab
- May require administrator rights on some systems

### Build errors
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

## Privacy & Security

- **Local Storage Only** - Your session credentials are stored locally using encrypted electron-store
- **No Third-Party Servers** - No data is sent to any servers except Claude.ai official API
- **Official API Only** - Widget only communicates with Claude.ai API endpoints
- **Secure Cookies** - Session cookies stored using Electron's secure storage
- **Open Source** - All code is publicly available for audit

## Technical Details

**Built with:**
- Electron 28.0.0
- Pure JavaScript (no framework overhead)
- Native Node.js APIs
- electron-store for encrypted secure storage
- axios for HTTP requests
- Canvas API for tray icon generation

**API Endpoints:**
```
https://claude.ai/api/organizations/{org_id}/usage
https://claude.ai/api/organizations
```

**Storage Location:**
```
%APPDATA%/claude-usage-widget/config.json (encrypted)
```

**Configuration Keys:**
- `sessionKey` - Encrypted Claude.ai session token
- `organizationId` - Your Claude organization UUID
- `colorPreferences` - Custom color settings
- `traySettings` - Tray icon configuration
- `themeSettings` - Widget theme preferences
- `appSettings` - Application behavior settings
- `uiVisibility` - Element visibility toggles
- `windowPosition` - Saved window location

## Project Structure

```
claude-usage-widget/
├── main.js                  # Electron main process
├── preload.js              # IPC bridge (security)
├── package.json            # Dependencies and scripts
├── assets/
│   ├── icon.ico           # Application icon
│   └── logo.png           # Widget logo
└── src/
    └── renderer/
        ├── index.html     # Main widget UI
        ├── app.js         # Widget logic
        ├── styles.css     # Widget styles
        ├── settings.html  # Settings panel UI
        ├── settings.js    # Settings logic
        └── settings-styles.css  # Settings styles
```

## Version History

### v1.4.2 (Current)
- ✨ Added comprehensive UI element visibility controls
- ✨ Added system tray icon with live usage display
- ✨ Added customizable tray icon colors and update interval
- ✨ Added application settings (start on boot, start minimized, close to tray)
- ✨ Added theme customization (backgrounds, text colors, borders, opacity)
- ✨ Added configurable update intervals for UI and tray
- ✨ Added static color mode for progress bars
- ✨ Added dynamic window resizing based on visible elements
- 🎨 Improved settings organization with collapsible sections
- 🎨 Consistent typography and spacing throughout settings
- 🐛 Fixed element centering and responsive layout
- 🐛 Fixed timer container visibility handling

### v1.4.1
- Added color customization
- Added settings panel
- Improved window position persistence

### v1.4.0
- Added custom color themes
- Added settings window
- Remember window position

### v1.3.0
- Initial public release
- Real-time usage tracking
- System tray support
- Auto-refresh functionality

## Roadmap

### Planned Features
- [ ] macOS support
- [ ] Linux support
- [ ] Notification alerts at usage thresholds
- [ ] Usage history graphs
- [ ] Export usage data (CSV/JSON)
- [ ] Multiple account support
- [ ] Keyboard shortcuts
- [ ] Mini mode (ultra-compact view)
- [ ] Desktop widget mode (frameless, always-on-desktop)
- [ ] Custom notification sounds

### Completed
- [x] Custom color themes
- [x] Remember window position
- [x] Settings panel
- [x] System tray integration
- [x] Tray icon with live usage
- [x] Element visibility controls
- [x] Theme customization
- [x] Configurable update intervals
- [x] Auto-start on boot
- [x] Static color mode

## Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add some amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Guidelines
- Follow existing code style
- Test thoroughly before submitting PR
- Update README if adding features
- Add comments for complex logic

## License

MIT License - feel free to use, modify, and distribute as needed.

See [LICENSE](LICENSE) file for full details.

## Disclaimer

**This is an unofficial tool and is not affiliated with, endorsed by, or connected to Anthropic or Claude.ai in any way.**

- Use at your own risk and discretion
- No warranties or guarantees provided
- Not responsible for any issues arising from use
- May break if Claude.ai changes their API
- Respect Anthropic's Terms of Service

## Support

If you encounter issues:

1. **Check existing issues** - [Issues page](../../issues)
2. **Create a new issue** with:
   - Your Windows version
   - Widget version
   - Steps to reproduce
   - Error messages (if any)
   - Screenshots (if relevant)

**Before reporting:**
- Try restarting the widget
- Try re-logging in
- Check if Claude.ai is accessible in browser
- Verify you have the latest version

## Acknowledgments

- Built for the Claude.ai community
- Inspired by the need for easy usage monitoring
- Thanks to all contributors and users

---

**Made with ❤️ for the Claude.ai community**

**Star ⭐ this repo if you find it useful!**
