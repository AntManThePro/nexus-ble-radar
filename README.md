# NEXUS · BLE Tactical Radar v3

**NExtended Xperimental USers**  
Operator: DoubleA · AntManThePro

Elite field radar for BLE advertisement scanning. Real `requestLEScan` path + high-fidelity simulation. **KalmanJS** (MIT) for smoother signal strength readings.

## Live Demo
https://antmanthepro.github.io/nexus-ble-radar/

## What's new in v3
- Distances shown in **feet**
- Plain-language labels ("About X feet away", "Signal Strength", "Type of device")
- Compass directions (N/NE/E/etc.) on the radar and in details
- **3D Walk View** — select a device, hit the button, and walk toward the glowing signal on a simple perspective street
- Cleaner status messages

## Features
- Live Web Bluetooth LE scan (Chrome/Edge + experimental flag) or practice mode
- Rough distance from signal strength + Kalman smoothing
- Modes, saved devices, trails, export
- Honest notes: direction is estimated, no real angle-of-arrival without special hardware

## Browser
- Chromium (Chrome, Edge)
- HTTPS or localhost
- Enable `chrome://flags/#enable-experimental-web-platform-features`
- Not supported on iOS Safari / Firefox

## Open Source
- **KalmanJS** — https://github.com/wouterbulten/kalmanjs (MIT)

MIT
