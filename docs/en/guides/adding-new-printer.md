# 🛠️ How to Add a New 3D Printer Profile

This guide provides step-by-step instructions for community developers adding a new 3D printer driver using the open `profile-v2` JSON format.

---

## 📌 1. Prerequisites

1. **Printer Network Details:** Local IP, open service ports (80, 7125, 9999, etc.), and mDNS discovery type.
2. **JSON Schema Compliance:** Verify that your profile complies with the [profile-v2 Schema](file:///d:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/schemas/profile-v2.schema.json).

---

## 📌 2. Step-by-Step Profile Creation

### Step 1: Create the Driver File
Create a new file under `community-hub/docs/examples/` or within the app profiles directory:
e.g., `mybrand-modelx-v2.json`.

### Step 2: Declare Identity and Permissions
```json
{
  "$schema": "../schemas/profile-v2.schema.json",
  "schemaVersion": 2,
  "id": "community.mybrand-modelx.v2",
  "version": "1.0.0",
  "identity": {
    "name": "MyBrand Model X",
    "models": ["Model X", "Model X Pro"],
    "status": "community"
  },
  "permissions": [
    "statusRead",
    "fileListRead",
    "fileUpload",
    "cameraRead"
    // Note: Omit "printStart" for community profiles to enforce Safe-Mode!
  ]
}
```

### Step 3: Configure Channels & Operations
Define HTTP or WebSocket channels and endpoints following the [Creality K1 Example](file:///d:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/creality-k1-v2.json) or [Snapmaker U1 Example](file:///d:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/snapmaker-u1-v2.json).

### Step 4: Map Telemetry (state)
Map temperatures and print progress using JSONPath.

---

## 📌 3. Local Verification

Run the driver verification suite to confirm your JSON is valid:

```powershell
cd makersync_app
flutter test test/community_printer_driver_v2_test.dart
```

When all tests pass green, submit a Pull Request to Community Hub!
