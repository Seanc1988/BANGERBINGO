# BANGER BINGO Roadmap

## Immediate beta fixes

### Spotify metadata latency
The current local Spotify Desktop integration launches a PowerShell helper repeatedly to read the Windows media session. That process startup cost plus Windows media-session update latency can make track changes appear late.

Planned direction:
1. Keep a persistent Windows media-session watcher alive instead of launching PowerShell for every poll.
2. Push track-change events to Node immediately.
3. Keep a low-frequency fallback poll in case an event is missed.
4. When a Spotify account is connected, optionally use playback-state reads as a secondary source.

Target: most song changes should populate within roughly 1-3 seconds, not tens of seconds.

### 30-second Spotify round mode
Add optional Music Bingo clip mode:
- configurable clip length, default 30 seconds
- automatic advance after the clip
- manual Next still available
- toggle per round or globally

### Smooth Spotify transitions
Preferred implementation for connected Spotify playback:
- fade volume down briefly
- advance to next track
- fade volume back up
- configurable transition duration

For local-only Spotify Desktop control, true per-app volume crossfading is more limited, so the first implementation may use a best-effort fade or require connected playback control.

## Before commercial release
- finalize product name / branding
- native Windows packaging
- installer
- desktop shortcut
- code signing
- automatic updates
- subscription licensing
- 30-day offline license lease
- device activation management
- billing integration
