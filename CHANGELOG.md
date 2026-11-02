# 更新日誌 Changelog

## 0.3.0（2026-11-03）

### 新功能
- **日誌**：在儀表板上單擊一張卡片，打開那張卡片的紀錄：7 天的每小時最高溫度和降頻次數圖（滑鼠移上去看那一小時），
  加上事件清單（何時降頻、過熱、風扇停了、連不上、guest 停了、Proxmox 的啟動／關機／備份…）。
  點標題列看那台的全部。儀表板收著也在背景記（本機每分鐘、遠端每 5 分鐘），保留 35 天。
- **降頻、過熱記下「當時在跑」**：那段時間最吃 CPU 的服務／程式和用了幾核；Proxmox 上看得到是哪個容器的哪個服務、
  是排程（附換成本機時間的排程時間）還是手動下的指令，取樣之間已經跑完的也算得到。
  Proxmox 要更新主機上的 agent（`bin/remote-agent.sh`，多了 `cpu`、`who` 兩種輸出）；沒更新就是不記這一行。
- **有狀況當下就通知**：過熱、風扇停了、連不上、guest 停了、硬碟快滿、備份失敗…記到的那一刻就跳通知（降頻和沒到 100°C 的過熱太常發生，只記在日誌）。
  原本中午的每日檢查不再跳通知（它回頭看 24 小時，會把昨天的降頻當成剛發生）。
- **通知開關**：設定 →「一般」多了「跳桌面通知」，取消勾選就不跳通知，狀況照樣記在日誌。
- **直式版型**：螢幕轉成直立的就自動換成直式（開著時轉向也會跟著換），轉回橫的換回原本的版型。卡片排成兩欄，型號、開機時間、網速那行移到大標題下面。

### New
- **Log**: click a card on the dashboard to see its history: a 7-day chart of the hourly max temperature and throttle
  count (hover for that hour), plus a list of events (throttling, overheating, stopped fans, lost connections, stopped
  guests, Proxmox start/shutdown/backup tasks…). Click the header for everything on that machine. Recording runs in the
  background even while the dashboard is closed (every minute locally, every 5 minutes for servers) and keeps 35 days.
- **Throttling and overheating events record what was busy**: the services/apps using the most CPU at the time and how
  many cores. On Proxmox it shows which container and service, whether it was scheduled (with the schedule converted to
  local time) or run by hand, including jobs that finished between samples. Requires updating the agent on the host
  (`bin/remote-agent.sh`, new `cpu` and `who` modes); without it this line is simply not recorded.
- **Alerts as they happen**: overheating, stopped fans, lost connections, stopped guests, nearly full disks, failed
  backups… pop up a notification the moment they are recorded (throttling, and overheating below 100°C, happen too
  often, so they are only logged). The noon daily check no longer notifies (it looked back 24 hours, so yesterday's
  throttling showed up as if it had just happened).
- **Notification switch**: Settings → General has a new “Show desktop notifications” option. When unchecked,
  nothing pops up, but alerts are still recorded in the log.
- **Portrait layout**: when the monitor is rotated upright the dashboard switches to it automatically (also while
  open), and back to your chosen layout when it is landscape again. Cards in two columns, with the model / uptime /
  network line moved under the title.

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
