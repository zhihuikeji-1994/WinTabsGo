# WinTabsGo

**Language:** **English** | [中文](version.md)

Version zh-2026092501. Maintainer: zhihuikeji.

This file records only what zh-2026092501 adds and fixes on top of upstream WindowTabs (through ss_2026.09.21; original author Maurice Flanagan; ss_ line maintained by Satoshi Yamamoto). It does not include the upstream changelog.

## version zh-2026092501

### Product

- The product name is WinTabsGo. The tray icon, the Settings window, and the settings file all show zh-2026092501.
- Settings are stored in `%APPDATA%\WinTabsGo`. An old `%APPDATA%\WindowTabs` folder is not read or copied.
- Windows records the installer version as 26.09.25.1. Windows Installer only accepts a numeric version. The interface still shows zh-2026092501.
- The online update check has been removed, so the program can run on a private network or with no network.

### Added on top of the upstream program

- **Tabs can dock on four edges.** In Settings, on the Behavior page, choose top, bottom, left, or right. Top matches the upstream behavior. Bottom is a horizontal strip inside the window, along the bottom edge. Left and right are vertical strips inside the window, and clicks line up with the rotated tabs. The default is still top. Choosing a different edge for each tab group is not available yet.
- **The close button on a tab is off by default.** You can turn it on from the Behavior page. On that page, the dock edge and the options under it sit on one row.
- **Hovering a tab activates it.** You can set how long the pointer must stay. The default is 200 milliseconds.
- **Remote Desktop full screen.** The tab strip stays visible in full screen, and you can choose not to hide tabs in full screen. After leaving full screen, windows in the same group follow back into place, so the Remote Desktop connection bar is not pushed out of layout.
- **Settings are saved by hand.** Changes in the dialog stay in a draft until you click Save. Save writes them to disk and applies them to windows and shortcut keys. Closing with unsaved changes asks you to save, discard, or cancel.
- **Explanations in Settings.** The Appearance, Behavior, Shortcut keys, and Workspace pages have explanation lines. Numeric fields are more compact, and the Settings window is wider. On the Shortcut keys page, the number keys line up with the hotkey boxes, and the Ctrl and Alt modes sit on one row.

### Fixed on top of the upstream program

- Saving settings now applies the appearance and custom tab colors. Saving is less likely to freeze the window. Opening Settings no longer crashes on the case that used to fail. Switching dark mode no longer leaves a stale cache. Shortcut-key numbers are read from more JSON value types.
- Tab tooltips on all four edges are anchored to the edge they belong to, and they stay inside the window's client area.
- Dragging the title bar while a window is full screen no longer flashes back to full screen. After the drag ends, the group is laid out again.
