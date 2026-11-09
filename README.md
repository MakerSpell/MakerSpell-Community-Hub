# 🌐 MakerSpell Community Hub & Hardware Documentation

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![MakerSpell](https://img.shields.io/badge/MakerSpell-Ecosystem-indigo.svg)](https://www.makerspell.com)
[![Status: Active](https://img.shields.io/badge/Status-Live%20Hub-emerald.svg)](https://github.com/MakerSpell/MakerSpell-Community-Hub)

Welcome to the **MakerSpell Community Hub** — the official, open-source repository for community-driven 3D printer profiles, hardware integration guides, OrcaSlicer configurations, and platform documentation.

> **One platform, every 3D model, direct to your printer.**  
> MakerSpell connects 26 model repositories, cloud & local slicing engines, and multi-brand 3D printers into a unified workspace.

---

## 📚 What's Inside This Repository

- **📖 Hardware Guides:** Step-by-step setup guides for Klipper/Moonraker, CrealityOS, Snapmaker, OctoPrint, Bambu Lab, and Prusa devices.
- **🖨️ Community Printer Profiles:** Declarative JSON definitions for community hardware (bed sizes, extrusion capabilities, network discovery contracts, and G-code flavors).
- **⚙️ Slicer Core Documentation:** OrcaSlicer engine integration details, filament presets, and multi-color toolchange matrices.
- **🛡️ Hardware Safety Protocol:** Zero-risk hardware control standards, physical safety rules, and sandboxed safe-mode specifications.

---

## 🖨️ Supported Hardware Compatibility Matrix

| Hardware / Protocol | Status | Control Mode | Telemetry | Firmware Requirement |
| :--- | :--- | :--- | :--- | :--- |
| **Creality K1 / K1 Max / K1C** | 🟢 **Verified** | Full Bi-directional | Live Temps, Chamber, LiDAR, Camera | CrealityOS / Moonraker |
| **Creality Ender-3 V3 (CoreXZ)** | 🟢 **Verified** | Full Bi-directional | Live Status, Stage tracking | CrealityOS / Moonraker |
| **Snapmaker U1 / Artisan** | 🟢 **Verified** | Full Bi-directional | 4-Toolchanger Telemetry, MQTT | Snapmaker Extended FW |
| **Moonraker / Klipper Ecosystem** | 🟢 **Verified** | Full Bi-directional | Full WebSocket / REST Telemetry | Klipper / Moonraker |
| **OctoPrint v1 Ecosystem** | 🟢 **Verified** | Full Bi-directional | MJPEG Webcam, REST API v1 | OctoPrint 1.8+ |
| **Prusa MK4 / XL / MINI** | 🟡 **Community** | Safe-Mode Print | PrusaLink REST / Digest Auth | Firmware 5.0+ |
| **Bambu Lab (P1, X1, A1 Series)** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Local MQTT Broker (No Cloud) | Local Mode (auto_start=false) |
| **Elegoo / Anycubic / Voron** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Discovery & Staging | Standard Firmware |

> [!IMPORTANT]
> **Community Hardware Safety Rule:** All unverified or community-contributed printer profiles default strictly to **Safe-Mode (`UPLOAD_ONLY`)**. MakerSpell will transfer sliced print files to the printer's local storage, but the physical heating and print start must be initiated on the machine by the operator.

---

## 🤝 How to Contribute a Printer Profile

We welcome community-tested profiles for all 3D printers!

1. Fork this repository: `https://github.com/MakerSpell/MakerSpell-Community-Hub`
2. Create a new profile file under `profiles/printers/<brand>/<model>.json`:
   ```json
   {
     "id": "my_printer_id",
     "brand": "MyBrand",
     "model": "Model X1",
     "protocol": "moonraker",
     "buildVolume": { "x": 250, "y": 250, "z": 250 },
     "heatedBedMax": 110,
     "nozzleMax": 300,
     "defaultPort": 7125,
     "safeModeOnly": true
   }
   ```
3. Submit a Pull Request. Once reviewed, it will be validated and automatically synchronized with the MakerSpell app and [makerspell.com/community-printers](https://www.makerspell.com/community-printers).

---

## 🔗 Official Ecosystem Links

- **Web Platform:** [makerspell.com](https://www.makerspell.com)
- **Community Printers Hub:** [makerspell.com/community-printers](https://www.makerspell.com/community-printers)
- **3D Deals & Coupons:** [makerspell.com/deals](https://www.makerspell.com/deals)
- **Pricing & Membership:** [makerspell.com/pricing](https://www.makerspell.com/pricing)
- **Discord Topluluğu & Destek:** [makerspell.com/contact](https://www.makerspell.com/contact)

---

## ⚖️ License

Distributed under the **MIT License**. See `LICENSE` for details.
