# 更新日誌 Changelog

## 0.2.0（2026-10-07）

### 新功能
- **立刻黑屏**：按 `Ctrl+Alt+L`（或右鍵選單「立刻黑屏」），所有螢幕直接關掉；按任一鍵或動一下滑鼠就回到儀表板。
  儀表板沒開的話會先打開。叫醒用的那個鍵也會送到前面的視窗，建議按 Shift 或動滑鼠。
- **快捷鍵檢查**：設快捷鍵時，馬上列出它跟這台電腦上哪些快捷鍵重複（系統、輸入法、瀏覽器、VS Code、終端機、
  Steam、Discord）和按鍵順序的風險，並建議幾組沒人用的組合，點一下就填好；有重複時會再問一次要不要用。
- **快捷鍵被佔走時提醒**：程式啟動時檢查自己的快捷鍵有沒有被系統快捷鍵、輸入法佔走，有就跳通知。
- 右鍵選單直接顯示快捷鍵；「快捷鍵」改成子選單，兩組都能換。

### 修正
- Linux（Wayland）：讀不到螢幕型號時，儀表板會跑到別台螢幕。
- Linux（Wayland＋NVIDIA，Ubuntu 24.04）：儀表板很久才完整出現、相框照片一直是黑的。

### 其他
- 已在 Ubuntu 24.04、26.04 實測。

### New
- **Screen off now**: press `Ctrl+Alt+L` (or "Screen off now" in the tray menu) to turn all screens off; press any key
  or move the mouse to come back to the dashboard. Opens the dashboard first if it is closed. The key you press also
  reaches the window in front, so Shift or a mouse move is safest.
- **Hotkey check**: when you set a hotkey, it lists which shortcuts on this computer already use it (system, input
  method, browsers, VS Code, terminal, Steam, Discord) and any key-order risk, and suggests a few free combinations you
  can pick with one click; if there is a clash it asks you again before using it.
- **Clash alerts**: at startup the program checks whether a system shortcut or input method has taken its hotkeys and
  shows a notification if so.
- The tray menu shows the hotkeys; "Hotkeys" is now a submenu where both can be changed.

### Fixed
- Linux (Wayland): the dashboard could open on the wrong monitor when the monitor model could not be read.
- Linux (Wayland + NVIDIA, Ubuntu 24.04): the dashboard took a long time to appear completely and frame photos stayed black.

### Other
- Tested on Ubuntu 24.04 and 26.04.

## 0.1.0（2026-10-06）

- 第一個測試版：Windows 安裝檔、Linux 安裝包。
- First beta: Windows installer and Linux package.
