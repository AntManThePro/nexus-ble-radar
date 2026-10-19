# NEXUS · BLE Tactical Radar v2

**NExtended Xperimental USers**  
Operator: DoubleA · AntManThePro

Elite field radar for BLE advertisement scanning. Real `requestLEScan` path + high-fidelity simulation. **KalmanJS** (MIT) RSSI filtering for more stable distance estimates via log-distance path loss.

## Live Demo
https://antmanthepro.github.io/nexus-ble-radar/

## What's new in v2
- **KalmanJS** integrated (MIT, Wouter Bulten) — proper 1D Kalman filter per device for RSSI noise reduction
- Device trails on the radar
- Range ring labels (meters)
- Adjustable Kalman Q in Pro mode
- Raw vs filtered RSSI in detail panel
- Trails toggle + keyboard (T)
- Cleaner status and attribution

## Features
- Live Web Bluetooth LE scan (Chrome/Edge + experimental flag) or high-fidelity sim
- Log-distance path loss distance estimation
- Modes: ECO / PRECISION / STREET / PRO TOOLS
- Favorites (localStorage), detail sparkline, export JSON
- Honest limitations (no AoA without multi-antenna hardware)

## Browser
- Chromium (Chrome, Edge)
- HTTPS or localhost
- Enable `chrome://flags/#enable-experimental-web-platform-features`
- Not supported on iOS Safari / Firefox
- Distances remain estimates. Native owns the antenna.

## Open Source
- **KalmanJS** — https://github.com/wouterbulten/kalmanjs (MIT)  
  Inlined for zero-dependency RSSI smoothing. Recommended for BLE signal noise.

## Local
Open `index.html` in a supported browser.

MIT
