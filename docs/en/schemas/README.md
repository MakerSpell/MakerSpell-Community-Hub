# JSON Driver & Profile Schema (v2) Overview

The core of MakerSpell's dynamic printer driver architecture is the **`profile-v2.schema.json`** specification.

This open specification empowers the community to define communication protocols, network discovery rules, telemetry maps, hardware controls, and dashboard layouts in a single declarative JSON file.

---

## 1. Why Declarative JSON Drivers?

Traditional slicers and 3D printing software (Creality Print, Bambu Studio, Cura) require modifying and recompiling C++/Dart code to support new printer models.

In MakerSpell:
1. **Dynamic Distribution:** New printer drivers are published directly to the open GitHub Community Hub.
2. **Instant Download:** MakerSpell clients (Desktop, Web, Mobile) fetch the profile, validate its SHA-256 and JSON schema, and activate it without restarting the app.
3. **Sandboxed Security:** The JSON driver contains pure data definitions and cannot execute arbitrary operating system scripts or make unauthorized network calls.

---

## 2. Slices of a Driver Profile

| Block | Role |
| :--- | :--- |
| **`identity`** | Friendly printer name, supported models, and verification status (`community` or `communityVerified`). |
| **`permissions`** | Requested access rights (`statusRead`, `fileUpload`, `deviceControl`, `cameraRead`, etc.). |
| **`discovery`** | mDNS service types (`_creality._tcp.local`), port list, and identity probe requests. |
| **`channels`** | Network communication endpoints (`http`, `websocket`, ports, timeouts). |
| **`operations`** | HTTP/WebSocket operations (`status`, `uploadFile`, `startPrint`, `pausePrint`, `setTemp`, etc.). |
| **`actions`** | UI button bindings routing interface events to underlying operations with parameter clamping. |
| **`state`** | JSONPath telemetry mapping transforming raw printer payloads into standard MakerSpell telemetry. |
| **`ui`** | Dashboard grid layout and card ordering across 2-column desktop and mobile views. |
| **`media`** | Live camera stream endpoints and onboard web interface URLs. |

---

## 3. Official References

- [Full profile-v2 Specification Guide](profile-v2-specification.md)
- [Official JSON Schema File (`profile-v2.schema.json`)](profile-v2.schema.json)
