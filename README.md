# NEXUS · BLE Tactical Radar v4.1.12

**NExtended Xperimental USers** · DoubleA (AntManThePro)

Single-file Bluetooth Low Energy radar for the browser. Decodes nearby devices, helps you find your own stuff, and runs a personal-safety **FOLLOWING ME?** check for unknown item trackers when a full scan is available. NEXUS palette. No paywall in this cut. Not perfect, just real.

**Live:** https://nexus-ble-radar.netlify.app/

## How to use it

1. Open the live site over HTTPS.
2. Tap **START LIVE SCAN** (Chrome/Edge on Android or desktop — turn on `chrome://flags/#enable-experimental-web-platform-features` first and relaunch).
3. On iPhone, open the page in free **[Bluefy – Web BLE Browser](https://apps.apple.com/app/id1492822055)** and use **GO LIVE · PICK DEVICE** — iOS Safari has no Web Bluetooth, so it stays PRACTICE there.
4. Tap a device to see what it really is in plain words before any name or code. Mark your own stuff **MINE** so the tracker check knows it's yours.
5. Use **FIND** mode (HOT/COLD + Geiger) to walk toward a lost device, or export CSV/JSON from the tools tab.

## LIVE vs PRACTICE (honest)

| Mode | When | What you see |
|---|---|---|
| **LIVE** | Browser actually grants Web Bluetooth (full scan or pick-one) | Real advertisements. Distances are estimates. Link % (Bluefy) is never shown as dBm. |
| **PRACTICE** | No Web Bluetooth / permission denied / iOS Safari | Simulated devices, every row labeled PRACTICE. |
| **PAUSED** | You stopped | Nothing updates. |

NEXUS never claims LIVE without a real radio path. If START can't go live, the app opens **HOW TO GO LIVE** with the exact reason.

## Features

- Manufacturer / company decode (Bluetooth SIG subset + Apple Continuity, Tile, Chipolo, SmartTag, Fast Pair, Eddystone / Find Hub, DULT). Junk broadcast names (`BLE-xxxx`, MAC-like, bare hex, `N/A`) are cleaned; UI shows brand/product or `Unidentified · #XXXX`. Raw advertised name stays in the Decoder.
- **FOLLOWING ME?** (PROTO): alerts when an item tracker that isn't marked *mine* stays near you with a strong signal. Needs **full scan** (real dBm). In Bluefy / pick-one mode the tab says Tracker Watch is not available there — use the phone's built-in unknown-tracker alerts.
- Pro tools (free): Signal Strength Monitor, Advertisement Decoder, GATT Explorer (PROTO), calibration, CSV/JSON export.
- Find mode: HOT/COLD, Geiger (muteable), vibration when supported, SWEEP, COMPASS (hollow dots = direction unknown).
- Session nicknames, favorites, MINE, Walk View, ECO / PRECISE / OUTDOOR / PRO profiles.

## Browser matrix

| Client | Mode |
|---|---|
| Chrome/Edge + experimental flag (Android/desktop) | Full LIVE scan |
| Chrome/Edge without flag | LIVE pick-one (if Web Bluetooth on) |
| Bluefy on iPhone | LIVE pick-one (+ link % fallback) |
| iOS Safari / Chrome/Edge/Firefox on iPhone | PRACTICE only |
| Firefox desktop | PRACTICE only |

## Links

- Live site: https://nexus-ble-radar.netlify.app/
- NEXUS hub: https://nexus-world-hub.netlify.app/
- Repo: https://github.com/AntManThePro/nexus-ble-radar

## Open source

KalmanJS (MIT) — https://github.com/wouterbulten/kalmanjs — inlined.

MIT · © 2026 DoubleA / AntManThePro
