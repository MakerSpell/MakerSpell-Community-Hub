# 🛡️ Safe-Mode Hardware Safety Protocol

> [!CAUTION]
> **Physical Safety Priority:** 3D printers reach temperatures above 300°C and execute high-speed mechanical motions. An unintended network command could result in collisions or fire hazards. MakerSpell enforces a strict "Safety-First" architecture.

---

## 📌 1. Verified Hardware vs. Community Hardware

| Hardware Fleet | Status | Control Mode | Telemetry | Firmware Requirement |
| :--- | :--- | :--- | :--- | :--- |
| **Creality K1 / K1 Max / K1C** | 🟢 **Verified** | Full Bi-directional | Live Temps, Chamber, LiDAR, Camera | CrealityOS / Moonraker |
| **Creality Hi / Hi Combo** | 🟢 **Verified** | Full Bi-directional | 4-Color CFS Telemetry, Camera | CrealityOS v2 |
| **Snapmaker U1 / Artisan** | 🟢 **Verified** | Full Bi-directional | Toolchanger Telemetry, MQTT | Snapmaker Extended FW |
| **Moonraker / Klipper Ecosystem** | 🟢 **Verified** | Full Bi-directional | Full WebSocket / REST Telemetry | Klipper / Moonraker |
| **Bambu Lab (X1, P1, A1)** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Local MQTT Broker (No Cloud) | Local LAN Mode |
| **Elegoo / Anycubic / Voron** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Discovery & Staging | Standard Firmware |

---

## 📌 2. Mandatory Safe-Mode (`UPLOAD_ONLY`)

For all unverified or community-contributed models:

1. **`auto_start = false` Mandatory Rule:** Slicing upload requests never include automated print start commands.
2. **File Transfer Only:** Sliced G-code files are transferred directly to internal storage (SD card / eMMC / virtual_sdcard).
3. **Physical Inspection Required:** The operator must verify bed cleanliness and physical adhesion, then press Start on the physical machine touchscreen.
4. **Thermal & Motion Interlocks:** Manual motion controls are strictly locked while the printer reports an active or heating state.
