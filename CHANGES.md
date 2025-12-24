# Changes for Upstream PR

## Feature: Customizable Progress Bar Colors

### Modified Files

#### main.js
- Added `DEFAULT_COLOR_PREFERENCES` constant with default color scheme (normal, warning, danger states)
- Added IPC handler `get-color-preferences` to retrieve stored color preferences from electron-store
- Added IPC handler `set-color-preferences` to save color preferences to electron-store
- Storage schema: `colorPreferences: { normal: {start, end}, warning: {start, end}, danger: {start, end} }`

#### src/renderer/styles.css
- TODO: Add CSS custom properties (--color-normal-start, --color-normal-end, etc.)
- TODO: Convert hardcoded gradient colors to use CSS variables
- TODO: Apply to both .progress-fill and .timer-progress elements

#### src/renderer/app.js
- TODO: Add `applyColorPreferences()` function to set CSS custom properties
- TODO: Load and apply color preferences on init
- TODO: Add event listeners for color picker changes

#### src/renderer/index.html
- TODO: Add color picker UI in settings overlay (6 inputs for simplified scheme)
- TODO: Add "Reset to Defaults" button

#### preload.js
- TODO: Expose `getColorPreferences` and `setColorPreferences` IPC methods

---

## Feature: Dynamic Tray Icon with Usage Display (Planned)
- Not yet started

---

## Storage Changes
- Using existing electron-store, no additional files
- New keys: `colorPreferences`, `trayDisplayMode` (planned)
