# WinTabsGo

**Language:** **English** | [中文](version.md)

Version zh_2026.09.26.1. Maintainer: zhihuikeji.

This file records only what zh_2026.09.26.1 adds and fixes on top of upstream WindowTabs (through ss_2026.09.21; original author Maurice Flanagan; ss_ line maintained by Satoshi Yamamoto). It does not include the upstream changelog.

## version zh_2026.09.26.1

On top of zh-2026092501. Windows records the installer version as 26.09.26.1. The interface shows zh_2026.09.26.1.

- When an ordinary page goes full screen, Remote Desktop windows in the same group only stretch their frames over that area. They stay ordinary windows and do not enter exclusive mode.
- Switch to a Remote Desktop, then click its own top-right button, to put that one window into exclusive mode. The other Remote Desktop windows in the group do not follow. Each one has to be selected and clicked on its own.
- While any Remote Desktop in the group is exclusive, restoring another page or dragging its title bar does not take the group out of full screen. A warning asks you to leave exclusive mode first. The warning follows the interface language, plays the system alert sound, and appears in the center of the current screen. The heading is larger than the body, and the text is centered. Left open, it closes after six seconds. Closing it with the title-bar button or OK lets the next drag show it again immediately.
- After the group enters full screen, the other windows in the group fill the same area. Remote Desktop windows only stretch. One enters exclusive mode only when its own top-right button is clicked. When one does, the other windows still follow into full screen.
- Leaving Remote Desktop exclusive mode does not resize the other windows in the group.
- The tray language menu has two items. In Chinese it shows 语言 / 英文 / 中文. In English it shows Language / English / Chinese.
- Each tab group has a screen-ratio tab at the end of the strip. It is drawn like the other tabs and follows them to the left or the right. Click it, or rest the pointer on it, to choose 25%, 50%, or 75%. With no exclusive Remote Desktop, the window is centered on the current screen, and both its width and its height take that percentage. If the group still has an exclusive window, the size stays and the existing warning is shown. Dragging the title bar or resizing on the same screen clears the ratio. Dragging onto another screen recenters the window there.

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
