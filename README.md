<h1 align="center">GHI Game Launcher</h1>
<p align="center">
  <b>by OGSuperio</b> • <b>GamersHubIndia</b> — eSports &amp; hangout 🇮🇳
</p>

<p align="center">
  <a href="https://github.com/kingrj1295-design/GHI-Launcher/releases/latest"><b>⬇ Download the latest version</b></a>
</p>

---

**GHI Game Launcher** is a free, local-first game launcher for Windows. It brings all your PC games into one place,
launches them with one click, tracks your playtime, and keeps an eye on crashes — with a built-in Spotify mini player.

> Your library, settings and playtime stay on your PC. GHI does not upload your data and does not host or download any games.

## ✨ Features

### 🏠 Home
- Personalised dashboard with **Continue playing**, total playtime and live CPU/RAM
- Four game views: **Slides, Grid, List, Compact**
- Search, sorting, and **All / Recent / Favorites** tabs

### 📚 Game Library
- One-click detection of **Steam, Epic and GOG** games
- Add games by EXE or by folder, or run a deep scan of your drives
- Categories, favorites, filters and automatic cover art (Steam covers need no key)

### 🚀 Smarter launching
- Steam/Epic games start through their own launcher
- Custom launch arguments, working folder and **run as administrator**
- Pre-launch checks for common problems (e.g. missing Visual C++ runtime)

### ⚡ Game Optimizer
- Live CPU and memory graphs, top memory users
- Per-game boost profiles: CPU priority, High-performance power plan, memory trim, lower priority of chosen background apps
- **Everything is reverted when the game closes.** GHI never kills your apps or edits the registry, and it does not promise extra FPS.

### 🎵 Spotify
- Now playing, play/pause/next/previous and playlist links inside the launcher
- Works with the **Spotify desktop app, no login needed** (Free or Premium)
- Optional Spotify API login for album art and your playlist list

### 🛠 Crash Reports
- Records launcher errors, failed launches and game crashes
- Plain-language explanation of common crash codes, with things to try
- One-click export of a report ZIP for bug reports

### ⬆ Auto-updates
- Checks this repository's Releases for new versions
- Installer is verified with a **SHA-256 checksum** before it runs
- Your current version is backed up first, so you can **roll back**

## 📥 Install

1. Go to the [**Releases**](https://github.com/kingrj1295-design/GHI-Launcher/releases/latest) page.
2. Download **`GHISetup.exe`** and run it.
3. Windows SmartScreen may show "unknown publisher" because the app is not code-signed yet.
   Click **More info → Run anyway**.
4. On first start, let GHI detect your installed games.

**Requirements:** Windows 10/11 (64-bit).

## 🎧 Spotify setup (optional)

The basic Spotify controls work out of the box with the desktop app. For album art and playlist list:

1. Open the [Spotify developer dashboard](https://developer.spotify.com/dashboard) and create an app (Web API).
2. Add this Redirect URI exactly: `http://127.0.0.1:8888/callback`
3. In GHI go to **Music**, paste your **Client ID** and press **Connect**.

> Spotify now requires the app owner to have Premium and allows 5 users per app, so every person uses their own Client ID.

## 🖼 Covers for non-Steam games (optional)
Get a free API key from [SteamGridDB](https://www.steamgriddb.com) (Preferences → API) and paste it in **Settings**.

## 🧑‍💻 Run from source

```bash
git clone https://github.com/kingrj1295-design/GHI-Launcher.git
cd GHI-Launcher
python -m pip install -r requirements.txt
python main.py
```
Requires Python 3.12+. Tests (no GUI needed): `python tests/test_core.py`

### Build the exe and installer
```bash
python -m pip install pyinstaller
python -m PyInstaller --noconfirm "GHI Game Launcher.spec"
"C:\Program Files (x86)\Inno Setup 6\ISCC.exe" GHIInstaller.iss
```
Each release needs both `GHISetup.exe` and `GHISetup.exe.sha256` (SHA-256 of the installer), uploaded together.

## ❓ Troubleshooting
- **A game won't start:** open **Crash Reports** for a plain-language reason, or right-click the game → *Game settings* and try *Run as administrator*.
- **Games missing from the library:** use **Library → Detect Games**, or add the EXE / folder manually.
- **Antivirus warning:** the app is unsigned and built with PyInstaller, which some antivirus tools flag by mistake. You can inspect the source in this repository.

## 🐞 Reporting bugs
Open an [Issue](https://github.com/kingrj1295-design/GHI-Launcher/issues) and attach the ZIP from **Crash Reports → Export report ZIP**.

## 📜 Credits
Made by **OGSuperio** for the **GamersHubIndia** community.
Built with Python, PySide6, SQLite and psutil.
