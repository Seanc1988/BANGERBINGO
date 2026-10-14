# BANGER BINGO

BANGER BINGO is a Windows-first live game-show platform for event hosts and DJs.

Current game modes:
- Music Bingo
- Classic Bingo
- Keno

Current integrations:
- VirtualDJ
- Spotify Desktop control
- Optional Spotify account connection for playlist selection and playback controls
- Dual-screen Host + Audience display
- Bingo card generator
- Welcome / Intermission slideshow
- Progressive jackpot features
- Sound FX and themed audience displays

## Current beta

The current beta line is based on the v1.11 Music Bingo 3D build and is being actively field-tested at live events.

### Known live-event priorities
- Reduce Spotify now-playing detection latency.
- Add a timed ~30-second Music Bingo playback workflow for Spotify.
- Add a smooth transition / fade strategy when advancing Spotify tracks.
- Continue final UI cleanup before packaging as a commercial Windows application.
- Package as an installer with desktop shortcut, auto-update, and subscription licensing after beta.

## Architecture

- Node.js
- Express
- Socket.IO
- HTML / CSS / JavaScript
- Windows PowerShell helper for Spotify Desktop media-session control
- VirtualDJ bridge + history monitoring

## Distribution direction

The final product is intended to be packaged as a normal Windows desktop application with:
- one-click installer
- desktop / Start Menu shortcut
- automatic updates
- subscription entitlement
- signed offline license lease with periodic internet verification

## Repository status

This repository is now the source-control home for BANGER BINGO as the project transitions from ZIP-based beta releases to normal version-controlled development.
