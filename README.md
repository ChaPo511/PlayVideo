# PlayVideo - FiveM Video Player

An advanced video player resource for FiveM that supports both YouTube and Kick.com streams with comprehensive admin controls.

## Features

- **Multi-Platform Support**: Play both YouTube videos and Kick.com streams
- **Multiple Display Modes**: Small corner player or fullscreen large player
- **Admin Permission System**: Configurable access control with ACE, group, or identifier-based permissions
- **Zone-Based Playback**: Play videos for players within a specific radius
- **Server-Wide Controls**: Play videos for all players or stop videos for everyone
- **Interactive Player Controls**: For Kick streams - volume adjustment, mute/unmute toggle, and pause/resume functionality

## Commands

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

## Installation

1. Download the resource
2. Place it in your FiveM server resources folder
3. Add `start PlayVideo` to your server.cfg
4. Configure permissions in `config.lua`

## Configuration

Admin permissions can be configured via `config.lua`:
- Three permission methods: ACE permissions, group-based, or identifier-based
- Individual command restrictions can be enabled/disabled
- Set `Config.UsePermissions = false` to disable all restrictions

## Requirements

- FiveM server with `game 'gta5'` and `fx_version 'cerulean'`

## Support

For issues and feature requests, please create an issue on GitHub.
