# NEXUS · BLE Tactical Radar v4.0.2 — Live Mode

**NExtended Xperimental USers** · DoubleA (AntManThePro)

Single-file Bluetooth Low Energy radar for the browser. Decodes nearby devices, helps you find your own stuff, and runs a personal-safety **FOLLOWING ME?** check for unknown item trackers when a full scan is available. NEXUS palette. No paywall in this cut.

**Live demo (still v3 until promote):** https://antmanthepro.github.io/nexus-ble-radar/

## LIVE vs PRACTICE (honest)

| Mode | When | What you see |
|---|---|---|
| **LIVE** | Browser actually grants Web Bluetooth (full scan or pick-one) | Real advertisements. Distances are estimates. Link % (Bluefy) is never shown as dBm. |
| **PRACTICE** | No Web Bluetooth / permission denied / iOS Safari | Simulated devices, every row labeled PRACTICE. |
| **PAUSED** | You stopped | Nothing updates. |

NEXUS never claims LIVE without a real radio path.

### How to go LIVE
1. **Android / Windows / macOS / Linux / ChromeOS:** Chrome or Edge. Enable `chrome://flags/#enable-experimental-web-platform-features`, relaunch, open over HTTPS (or localhost), tap **START LIVE SCAN**.
2. **iPhone / iPad:** Safari and every other iOS browser stay **PRACTICE** (Apple WebKit has no Web Bluetooth). Use free **[Bluefy – Web BLE Browser](https://apps.apple.com/app/id1492822055)** → open this page → **GO LIVE · PICK DEVICE** / **+ TRACK A DEVICE**. Bluefy is pick-one + optional **link %** (not dBm). Full nearby scan + passive Tracker Watch on iPhone need the planned **native NEXUS iOS app**.
3. If START can't go live, the app opens **HOW TO GO LIVE** with the exact reason.

## Features
- Manufacturer / company decode (Bluetooth SIG subset + Apple Continuity, Tile, Chipolo, SmartTag, Fast Pair, Eddystone / Find Hub, DULT). Junk broadcast names (`BLE-xxxx`, MAC-like, bare hex, `N/A`) are cleaned; UI shows brand/product or `Unidentified · #XXXX`. Raw advertised name stays in the Decoder.
- **FOLLOWING ME?** (PROTO): alerts when an item tracker that isn't marked *mine* stays near you with a strong signal. Needs **full scan** (real dBm). In Bluefy / pick-one mode the tab says Tracker Watch is not available there — use the phone's built-in unknown-tracker alerts.
- Pro tools (free): Signal Strength Monitor, Advertisement Decoder, GATT Explorer (PROTO), calibration, CSV/JSON export.
- Find mode: HOT/COLD, Geiger (muteable), vibration when supported, SWEEP, COMPASS (hollow dots = direction unknown).
- Session nicknames, favorites, MINE, Walk View, Eco / Normal / Outside / Advanced profiles.

## Browser matrix
| Client | Mode |
|---|---|
| Chrome/Edge + experimental flag (Android/desktop) | Full LIVE scan |
| Chrome/Edge without flag | LIVE pick-one (if Web Bluetooth on) |
| Bluefy on iPhone | LIVE pick-one (+ link % fallback) |
| iOS Safari / Chrome/Edge/Firefox on iPhone | PRACTICE only |
| Firefox desktop | PRACTICE only |

## Open source
KalmanJS (MIT) — https://github.com/wouterbulten/kalmanjs — inlined.

MIT · © 2026 DoubleA / AntManThePro
