# BANGER BINGO Phone Controller v1.18.0

This folder is the GitHub Pages phone controller for the matching **Banger Bingo v1.18.0 GitHub Phone Controller Host** build.

It uses the same general approach as the working Ultimate Game Show Controller package: a static GitHub Pages site plus PeerJS/WebRTC, so guest phones can connect over cellular data or a different Wi-Fi network without exposing the BANGER BINGO laptop as a public web server.

## Upload to GitHub

Repository:

`https://github.com/Seanc1988/BANGERBINGO`

Upload **all files in this folder to the ROOT of the repository**. Do not upload an enclosing folder if you want the default controller URLs below to work.

Required root files:

- `index.html` — Music Bingo / Classic Bingo / Keno phone controller
- `trivia.html` — Trivia Intermission phone controller
- `phone-controller.js`
- `trivia-controller.js`
- `phone.css`
- `trivia.css`
- `peerjs.min.js`
- `qrcode.min.js`
- `rtc-config.js`
- `banger-logo.png`
- `README.md`

## Enable GitHub Pages

In GitHub:

1. Open **Settings** for the BANGERBINGO repository.
2. Open **Pages**.
3. Under Build and deployment, choose **Deploy from a branch**.
4. Select the branch containing these files, normally `main`.
5. Select `/ (root)`.
6. Save.

The public controller should become available at approximately:

`https://seanc1988.github.io/BANGERBINGO/`

Trivia:

`https://seanc1988.github.io/BANGERBINGO/trivia.html`

## How the game code works

The matching BANGER BINGO host build creates the existing six-digit Phone Cards room code. The GitHub controller connects to a PeerJS/WebRTC host room named internally from that code.

Guests can either:

- scan the QR code shown in the BANGER BINGO host, or
- open the GitHub Pages controller and type the six-digit game code.

The phone does **not** need to be on the same Wi-Fi as the host laptop.

## Supported phone games

`index.html` supports the current phone-card engine:

- Music Bingo
- Classic Bingo
- Keno

`trivia.html` supports:

- Trivia Intermission
- Standalone Trivia mode

The public controller does not duplicate the game engine. It sends only allowed player requests to the live host over WebRTC. The host remains authoritative for cards, calls, Keno validation, claims, Trivia scoring, timers and answers.

## Important

This package requires the matching **v1.18.0 host build**. Uploading the GitHub files alone does not make an older BANGER BINGO host listen for PeerJS phone connections.

Keep `rtc-config.js` with the other controller files. It contains the same WebRTC relay configuration used by the matching host build.

## Testing mobile-data access

1. Start the matching BANGER BINGO v1.18.0 host build.
2. Open **Phone Cards**.
3. Look for **GitHub Internet Phone Controller**.
4. Confirm it says **Internet phone controller ready**.
5. On a phone, turn Wi-Fi OFF.
6. Scan the Bingo QR or Trivia QR.
7. Join using cellular data.
8. Confirm the host shows the internet phone connection count increasing.

If the phone says it cannot reach the host, confirm:

- the host laptop itself has internet access,
- GitHub Pages has finished publishing,
- only one BANGER BINGO host is trying to own the same six-digit room,
- browser/firewall software is not blocking WebRTC.

## v1.18 Trivia fixes

- Trivia join no longer requires host authorization.
- Player seat tokens persist in localStorage and a refreshed phone automatically reconnects.
- Phones use a fresh PeerJS identity after drops instead of reusing stale connections.
- Host can force reconnects and clear the Trivia player pool.
- Trivia phones display the question, all four answers, and full round results.
- The public Trivia page is the preferred QR target for mobile-data play.
