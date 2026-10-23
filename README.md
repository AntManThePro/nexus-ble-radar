# NEXUS · BLE Radar v4 — Live Mode

**NExtended Xperimental USers**  
Operator: DoubleA · AntManThePro

BLE radar for nearby Bluetooth devices. **Live Mode** uses the real radio wherever the browser allows it; everywhere else it falls back to **Practice Mode** (simulated devices) and says honestly why, with a "how to go live" hint. **KalmanJS** (MIT) smooths the signal.

## Live Demo
https://antmanthepro.github.io/nexus-ble-radar/

## Where Live Mode works
| Browser | What you get |
|---|---|
| **iPhone / iPad → Bluefy – Web BLE Browser** (free, App Store) | Pick devices one at a time with **+ TRACK A DEVICE** (or START LOOKING). Bluefy does not expose a full scan or dBm, so NEXUS runs a gentle *link check* (connect / disconnect) and shows a **link %** (not dBm). Distance from it is very rough. If a future Bluefy exposes the full scan, NEXUS uses it automatically. |
| **Android Chrome** | Track one device at a time out of the box. For the **full "everything nearby" scan** with live dBm: enable `chrome://flags/#enable-experimental-web-platform-features`, relaunch. Needs Bluetooth + Location on and Nearby-devices permission. |
| **Desktop Chrome / Edge** (Win/Mac/Linux/ChromeOS) | Same as Android: track one device, or the full scan with the flag above. |
| iOS Safari, Chrome/Edge/Firefox on iPhone, desktop Safari, Firefox | **Practice Mode** only. All iPhone browsers use Apple's WebKit, which has no Web Bluetooth — the app tells you to open the page in Bluefy (button + copy link). |

The **PRACTICE / LIVE** badge in the header (or **HOW TO GO LIVE**, or key `L`) opens a panel that checks what *this* browser can actually do.

## What's new in v4
- Real Live Mode: `requestLEScan` full scan → `requestDevice` single-device tracking → Bluefy link-check fallback
- Practice devices are cleared when you go live; **BACK TO PRACTICE** brings them back
- Decodes real adverts: iBeacon / Eddystone (uses their announced 1 m strength for better distance), Apple (AirPods, Find My, Nearby…), Microsoft, Samsung, Google, Tile, Garmin, Fitbit…, heart-rate / audio / HID services
- Devices that go quiet for 90 s drop off (saved / tracked ones stay); "seen Ns ago" freshness
- **Direction for real**: tap **COMPASS**, turn slowly in a full circle — NEXUS remembers where each device was strongest. Hollow dot = direction not known yet. No fake angles.
- 3D Walk View in Live Mode: real distance, "turn left/right", **WARMER / COLDER**
- Screen stays awake while looking (Wake Lock); radar now uses true compass bearings (N up, clockwise)

## Honest limits
- Distance from signal strength is a rough guess (walls, bodies and pockets change it a lot).
- Phones can't measure the angle of a signal; direction only comes from your turn-in-a-circle.
- Browsers show a random per-site device ID, never the MAC address. Many phones/earbuds rotate their Bluetooth identity every few minutes, so one device can appear as a new entry.
- Live Mode only listens to public advertisements (except Bluefy's link check on the one device you pick). Nothing leaves your phone.

## Requirements
HTTPS (GitHub Pages) or `localhost`. Bluetooth on.

## Open Source
- **KalmanJS** — https://github.com/wouterbulten/kalmanjs (MIT)

MIT
