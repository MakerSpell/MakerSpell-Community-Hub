# 🌐 Network Discovery & Stable Hardware Identity (`stableId`)

In home and workshop networks, 3D printers often receive dynamic IP addresses via DHCP. When routers reboot, IP assignments frequently swap (e.g., an address previously used by a K1 might be reassigned to a Snapmaker U1).

MakerSpell prevents fleet confusion through its **Stable Hardware ID (`stableId`)** and intelligent network discovery engine.

---

## 📌 1. Resolving Stable Hardware Identity

The device identity resolution follows a strict priority chain:
1. **Network Hardware MAC Address:** Physical Wi-Fi or Ethernet MAC address (`b4:0e:xx:yy:zz`).
2. **Device Serial Number:** Reported hardware serial number from firmware.
3. **Klipper Machine UUID:** Moonraker unique machine instance ID (`printer.info.instance_id`).
4. **Fallback:** Ephemeral `ip:port` used temporarily until the first successful probe response resolves the permanent hardware identity.

---

## 📌 2. Dynamic IP Swaps & Collision Isolation

### The Problem Scenario:
Yesterday, `192.168.1.105` belonged to a **Snapmaker U1**. Today, the router rebooted and assigned `192.168.1.105` to a **Creality K1**, while the Snapmaker moved to `192.168.1.111`.

### The MakerSpell Solution:
1. **Identity-Based Matching:** Devices are matched and updated by their unique `stableId`, never blindly by raw IP.
2. **Clean Slot Transition:** When a probe on `192.168.1.105` returns Creality K1 credentials:
   - The existing Snapmaker U1 entry is **never overwritten or morphed into a K1**.
   - Snapmaker U1 is updated to `192.168.1.111` as soon as its mDNS packet arrives.
   - `192.168.1.105` receives a clean, dedicated Creality K1 device slot.
3. **Property Isolation:** Old filament states, camera settings, and model metadata remain strictly isolated to the original hardware.
