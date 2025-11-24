# PlayVideo - FiveM Video Player

An advanced video player resource for FiveM that supports both YouTube and Kick.com streams with comprehensive admin controls.

## 🌟 Features

- **Multi-Platform Support**: Play both YouTube videos and Kick.com streams
- **Multiple Display Modes**: Small corner player or fullscreen large player
- **Admin Permission System**: Configurable access control with ACE, group, or identifier-based permissions
- **Zone-Based Playback**: Play videos for players within a specific radius
- **Server-Wide Controls**: Play videos for all players or stop videos for everyone
- **Interactive Player Controls**: For Kick streams - volume adjustment, mute/unmute toggle, and pause/resume functionality
- **Framework Compatibility**: Works with ESX, QB, QBOX, and standalone servers

## 📋 Commands

### Personal Commands (admin-restricted by default):
- `/playsmall [url]` - Play video in small corner player
- `/playlarge [url]` - Play video in fullscreen player
- `/stopvideo` - Stop currently playing video

### Zone Commands (admin-only):
- `/playvideozone [small/large] [url] [radius] [current/x y z]` - Play video for players in radius
- `/stopvideozone [radius] [current/x y z]` - Stop videos for players in radius

### Server Commands (admin-only):
- `/playvideoall [small/large] [url]` - Play video for all players on server
- `/stopvideoall` - Stop videos for all players on server
- `/stopvideoplayer [player_id]` - Stop video for specific player

## 🚀 Installation

1. Download the resource
2. Place it in your FiveM server resources folder
3. Add `start PlayVideo` to your server.cfg
4. Configure permissions in `config.lua`

## ⚙️ Configuration

Admin permissions can be configured via `config.lua`:
- Three permission methods: ACE permissions, group-based, or identifier-based
- Individual command restrictions can be enabled/disabled
- Set `Config.UsePermissions = false` to disable all restrictions

### Permission Methods

1. **ACE Permissions** (Recommended):
   ```lua
   Config.PermissionType = 'ace'
   Config.AcePermission = 'playvideo.admin'
   ```
   Add to server.cfg: `add_ace group.admin playvideo.admin allow`

2. **Group-based**:
   ```lua
   Config.PermissionType = 'group'
   Config.AdminGroups = { 'admin', 'superadmin' }
   ```

3. **Identifier-based**:
   ```lua
   Config.PermissionType = 'identifier'
   Config.AdminIdentifiers = { 'steam:110000000000000' }
   ```

## 🔄 Framework Compatibility

Works with all major FiveM frameworks:
- **ESX**: Use group-based permissions
- **QB/QBOX/QBCore**: Use group-based permissions (supports 'admin', 'superadmin', 'god')
- **Standalone**: Use ACE or identifier-based permissions

### QBCore Specific Configuration

For QBCore servers, the resource automatically recognizes common admin groups. To ensure compatibility:

1. **Group-based permissions** (default):
   ```lua
   Config.PermissionType = 'group'
   Config.AdminGroups = { 'admin', 'superadmin', 'god' } -- Already configured for QBCore
   ```

2. **ACE permissions** (alternative):
   Add to your server.cfg:
   ```
   add_ace group.admin playvideo.admin allow
   add_ace group.superadmin playvideo.admin allow
   add_ace group.god playvideo.admin allow
   ```

## 📋 Requirements

- FiveM server with `game 'gta5'` and `fx_version 'cerulean'`

## 🛠️ Support

For issues and feature requests, please create an issue on GitHub.
