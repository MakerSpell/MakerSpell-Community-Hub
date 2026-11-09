# 🔌 Transport Adapters & Network Protocols

MakerSpell bridges diverse physical hardware protocols to standard application contracts using modular transport adapters.

---

## 📌 1. Standard Protocol Operations

Every transport adapter satisfies a standard set of operations:
- **Device Probe:** Verifies model credentials and firmware version over local ports.
- **Live Telemetry:** Streams nozzle and bed temperatures, fan speeds, and print progress.
- **File Transfer:** Wireless G-code streaming directly to onboard storage.
- **Job Control:** Pause, resume, abort, and emergency stop (M112) commands.
- **Manual Hardware Overrides:** Temperature targets and calibrated XYZ axis jogging.

---

## 📌 2. Supported Transport Adapters

### 🟢 1. Moonraker Transport (`moonraker`)
- **Target Hardware:** Any machine running Klipper (Voron, RatRig, modded Enders, Sovol, etc.).
- **Protocols:** WebSocket (`ws://<ip>:7125/websocket`) + JSON-RPC 2.0 & HTTP REST API.
- **Capabilities:** Live subscription to `printer.objects.query`, full G-code console, and virtual SD card thumbnails.

### 🟢 2. Creality Local v2 (`creality_local` / `creality_v2`)
- **Target Hardware:** Creality K1, K1 Max, K1C, Ender-3 V3, Hi, Hi Combo.
- **Protocols:** HTTP Port 80 (`/info`, `/downloads/gcode/...`) + WebSocket Port 9999.
- **Capabilities:** Integrated CrealityOS video stream, CFS 4-color RFID slot telemetry, and bed mesh visualization.

### 🟢 3. OctoPrint v2 Bridge (`octoprint` / `octoprint_v2`)
- **Target Hardware:** OctoPrint instances and Snapmaker U1/Artisan bridge adapters.
- **Protocols:** HTTP REST (`/api/printer`, `/api/files/local`) + API Key authentication.
- **Capabilities:** MJPEG webcam streaming and secure delegated file transfers.

### 🟡 4. Bambu Lab Local LAN Transport (`bambu_local`)
- **Target Hardware:** Bambu Lab X1C, P1S, P1P, A1, A1 Mini.
- **Protocols:** Local MQTT (`mqtts://<ip>:8883`) + FTPS (`ftps://<ip>:990`).
- **Safety Mode:** Strictly `UPLOAD_ONLY` (no cloud bridge dependency).

### 🟡 5. Elegoo SDCP Transport (`elegoo_sdcp`)
- **Target Hardware:** Elegoo Centauri Carbon, Neptune 4 Series with SDCP support.
- **Protocols:** UDP Port 3000 Broadcast Discovery + WebSocket Port 3030 JSON-RPC.
