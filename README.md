---

# 🎬 PlayVideo – FiveM Advanced Video Player

An advanced **video player resource for FiveM** supporting both **YouTube** and **Kick.com** streams, built with powerful admin controls and full framework compatibility.

---

## 🌟 Core Features

* **Multi-Platform Support** – Play YouTube videos and Kick live streams
* **Multiple Display Modes** – Small corner player or fullscreen player
* **Advanced Admin Permission System**

  * ACE-based
  * Framework group-based
  * Identifier-based
* **Zone-Based Playback** – Play videos within a configurable radius
* **Server-Wide Controls** – Broadcast or stop videos globally
* **Player Target Controls** – Stop videos for individual players
* **Interactive Kick Controls**

  * Volume adjustment
  * Mute / Unmute
  * Pause / Resume
* **Framework Compatible**

  * ESX
  * QBCore
  * QBOX
  * Standalone

---

# 📋 Commands

## 🔹 Personal Commands (Admin-Restricted by Default)

```
/playsmall [url]
/playlarge [url]
/stopvideo
```

---

## 🔹 Zone Commands (Admin Only)

```
/playvideozone [small/large] [url] [radius] [current/x y z]
/stopvideozone [radius] [current/x y z]
```

---

## 🔹 Server Commands (Admin Only)

```
/playvideoall [small/large] [url]
/stopvideoall
/stopvideoplayer [player_id]
```

---

# 🚀 Installation

1. Download the resource
2. Place it inside your `resources` folder
3. Add to `server.cfg`:

   ```
   ensure PlayVideo
   ```
4. Configure permissions inside `config.lua`

---

# ⚙️ Configuration

Permissions are fully configurable inside:

```
config.lua
```

You can:

* Enable / disable restrictions entirely
* Restrict individual commands
* Choose between 3 permission methods

Disable all restrictions:

```lua
Config.UsePermissions = false
```

---

## 🔐 Permission Methods

### 1️⃣ ACE Permissions (Recommended)

```lua
Config.PermissionType = 'ace'
Config.AcePermission = 'playvideo.admin'
```

Add to `server.cfg`:

```
add_ace group.admin playvideo.admin allow
```

---

### 2️⃣ Group-Based Permissions

```lua
Config.PermissionType = 'group'
Config.AdminGroups = { 'admin', 'superadmin' }
```

---

### 3️⃣ Identifier-Based Permissions

```lua
Config.PermissionType = 'identifier'
Config.AdminIdentifiers = {
    'steam:110000000000000'
}
```

---

# 🔄 Framework Compatibility

## ESX

Use **group-based permissions**

## QBCore / QBOX

Supports:

```lua
{ 'admin', 'superadmin', 'god' }
```

### Optional ACE Setup for QBCore

```
add_ace group.admin playvideo.admin allow
add_ace group.superadmin playvideo.admin allow
add_ace group.god playvideo.admin allow
```

## Standalone

Use:

* ACE permissions (recommended)
* or identifier-based permissions

---

# 🎛 Advanced Administration Update

PlayVideo now includes powerful new admin management tools.

---

## 🔹 1. Video Presets

Define common or favorite videos in `config.lua`.

```lua
Config.Presets = {
    { label = "My Favorite Stream", url = "https://example.com/stream" },
    { label = "Event Countdown", url = "https://example.com/countdown" }
}
```

Accessible under the **Presets** menu.

✔ Quick access
✔ Perfect for events
✔ No URL retyping

---

## 🔹 2. Recent History Tracking

The server tracks recently played videos.

* Default: **Last 10 videos**
* Fully configurable
* Replay directly from menu

Change limit:

```lua
Config.MaxHistory = 15
```

---

## 🔹 3. Active Stream Management

New **Current Streams** panel shows:

* Active zone streams
* Server-wide streams

Admins can:

✔ View all active streams
✔ Stop individual streams directly
✔ No need to remember coordinates or radius

---

## 🔹 4. Consolidated Menu UI

Rebuilt using **ox_lib submenus**.

### Menu Categories:

* ▶ Play New
* ⭐ Presets
* 🕘 Recent History
* 📊 Current Streams
* 🛑 Manual Stop

Cleaner structure. Faster navigation. Better admin workflow.

---

# ✅ How To Verify

### 1️⃣ Open Menu

Press **F10** or:

```
/playmenu
```

### 2️⃣ Test Presets

Select a preset video.

### 3️⃣ Test History

Play multiple URLs → Check **Recent History**.

### 4️⃣ Test Active Streams

Start a zone video → Open **Current Streams** → Stop it directly.

---

# 📂 Code Changes Overview

### config.lua

* Added `Config.Presets`
* Added `Config.MaxHistory`

### server.lua

* Added:

  * `videoHistory` tracking
  * `currentStatus` tracking

### client.lua

* Refactored `OpenMenu`
* Added categorized ox_lib submenus

---

# 📋 Requirements

* FiveM server
* `game 'gta5'`
* `fx_version 'cerulean'`

---

# 📞 Support

**Discord:**
[https://discord.gg/eXACMTyQNK](https://discord.gg/eXACMTyQNK)

**Support Development:**
[https://ko-fi.com/chapo_511](https://ko-fi.com/chapo_511)

---

# 🚀 Final Result

PlayVideo is now a **fully manageable streaming control system** designed for:

* Events
* Cinemas
* Clubs
* Admin announcements
* Roleplay enhancements

Free. Open source. Extendable.

---
