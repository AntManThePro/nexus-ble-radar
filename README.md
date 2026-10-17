# NEXUS · BLE Tactical Radar

**NExtended Xperimental USers**  
Operator: DoubleA · AntManThePro

Elite-class field radar for BLE advertisement scanning. Real `requestLEScan` path with high-fidelity simulation fallback, EMA-filtered RSSI, log-distance path loss, persistent radial slots, and neon field-plate UI.

## Live Demo
https://antmanthepro.github.io/nexus-ble-radar/

## Features
- Attempts live Web Bluetooth LE advertisement scanning (Chrome/Edge + experimental flag)
- High-fidelity simulation with random-walk RSSI, EMA smoothing, device churn
- Log-distance path loss distance estimation (adjustable n and TxPower in Pro)
- Modes: ECO / PRECISION / STREET / PRO TOOLS
- Favorites (persisted), target detail with RSSI sparkline + hex telemetry
- Export state JSON
- Honest radio status and limitation notes (no AoA without multi-antenna hardware)

## Browser Requirements
- Chromium-based (Chrome, Edge)
- HTTPS or localhost
- Enable `chrome://flags/#enable-experimental-web-platform-features`
- Not supported on iOS Safari or Firefox
- Distances are RSSI estimates. Native app owns the antenna.

## Local
Open `index.html` in a supported browser.

## Architecture
Single self-contained HTML. Canvas radar loop + Map-backed device pool. Real scan or sim both feed the same update/draw path. Path loss model and EMA are pure functions.

## License
MIT
