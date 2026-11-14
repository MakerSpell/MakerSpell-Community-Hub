# 3D Printer Connectivity & Integration Architecture

The MakerSpell ecosystem features a modular, hybrid connection architecture designed to discover, monitor, and stream G-code to hundreds of 3D printer models across all major manufacturers.

---

## 1. Architectural Layers

```mermaid
flowchart TD
    subgraph UI_Layer["Presentation Layer (Flutter Desktop & Mobile)"]
        UI_Dash["Responsive Control Cockpit"]
        UI_PrintCenter["Print Center (Fleet View)"]
        UI_Sender["Wireless G-code Sender"]
    end

    subgraph State_Layer["Unified State Layer (Single Source of Truth)"]
        CentralManager["Central Device Manager"]
        StableRegistry["Stable Hardware ID Resolver"]
        LivePoller["Telemetry & Heartbeat Engine"]
    end

    subgraph Driver_Layer["Dynamic Driver Layer"]
        V2Engine["Declarative profile-v2 Runtime Engine"]
        HardwareAdapters["Hardware Protocol Adapters"]
    end

    subgraph Protocol_Layer["Physical Network Protocols"]
        Moonraker["Moonraker / Klipper (WS/REST :7125)"]
        Creality["Creality Local (HTTP :80 / WS :9999)"]
        Octo["OctoPrint v2 Bridge (REST/WS)"]
        Bambu["Bambu Lab Local LAN (MQTT / FTPS)"]
        Elegoo["Elegoo SDCP (UDP Discovery / WS)"]
        Prusa["PrusaLink (REST / Digest Auth)"]
    end

    UI_Dash --> CentralManager
    UI_PrintCenter --> CentralManager
    UI_Sender --> CentralManager
    CentralManager --> StableRegistry
    CentralManager --> LivePoller
    LivePoller --> V2Engine
    V2Engine --> HardwareAdapters
    HardwareAdapters --> Moonraker
    HardwareAdapters --> Creality
    HardwareAdapters --> Octo
    HardwareAdapters --> Bambu
    HardwareAdapters --> Elegoo
    HardwareAdapters --> Prusa
```

1. **Declarative JSON Drivers (`profile-v2`):** Adding a new printer model or customizing its UI controls requires zero source code compilation. JSON driver profiles declare communication channels (`channels`), endpoints (`operations`), telemetry mapping (`state`), and user actions (`actions`).
2. **Audited Hardware Transports:** Network sockets, HTTP requests, and binary protocols are managed by battle-tested transport adapters.
3. **Safe-Mode (Physical Safety First):** Only lab-verified machines (Creality K1, Snapmaker U1, Creality Hi) receive remote start privileges. All community hardware defaults to strictly sandboxed `UPLOAD_ONLY` mode.

---

## 2. Documentation Directory

- [Safe-Mode Hardware Safety Protocol](safe-mode-protocol.md)
- [Network Discovery & Stable Hardware Identity](network-discovery.md)
- [Transport Adapters & Network Protocols](transport-adapters.md)
- [Multi-Color Systems (Creality CFS, Snapmaker AMS)](filament-ams-cfs.md)
