# 📐 profile-v2 Full Driver Specification

MakerSpell’s declarative printer driver specification `profile-v2` complies with the JSON Schema Draft 2020-12 standard. This document defines all schema keys, data types, and runtime validation rules.

---

## 📌 1. Root Fields

| Field | Type | Required? | Description |
| :--- | :--- | :--- | :--- |
| **`schemaVersion`** | `integer` | **Yes** | Constant value `2`. |
| **`id`** | `string` | **Yes** | Unique driver identifier (e.g. `community.creality-local-v2.experimental`). |
| **`version`** | `string` | **Yes** | Semantic version string (e.g. `2.0.1`). |
| **`channels`** | `object` | **Yes** | Network communication channels. |
| **`operations`** | `object` | **Yes** | Network operations (HTTP/WS requests). |
| **`state`** | `object` | **Yes** | Telemetry state mappings (JSONPath). |
| **`identity`** | `object` | No | Model compatibility and delegation flags. |
| **`permissions`** | `array` | No | Sandboxed permission rights. |
| **`discovery`** | `object` | No | mDNS and network probing specifications. |
| **`actions`** | `object` | No | UI button bindings to operations. |
| **`ui`** | `object` | No | Dashboard grid layout and column ordering. |

---

## 📌 2. `permissions` Array

Limits driver capabilities at runtime. Unlisted actions are strictly rejected:

```json
"permissions": [
  "statusRead",       // Telemetry and state reading
  "fileListRead",     // Reading onboard G-code file list
  "fileUpload",       // Transferring sliced files
  "printStart",       // Initiating prints (Excluded in Safe-Mode!)
  "printControl",     // Pause, resume, abort
  "deviceControl",    // Thermal, fan, and axis adjustments
  "cameraRead"        // Live video feed streaming
]
```

---

## 📌 3. `discovery` Block

Defines how the driver discovers and probes matching hardware:

```json
"discovery": {
  "serviceTypes": ["_creality._tcp.local", "_cxswbox._tcp.local"],
  "ports": [80, 9999],
  "probes": [
    { "operation": "probeInfo", "weight": 3, "required": true },
    { "operation": "status", "weight": 2, "required": false }
  ]
}
```

---

## 📌 4. `channels` & `operations` Blocks

Declares network communication endpoints and message payloads:

```json
"channels": {
  "web": {
    "kind": "http",
    "scheme": "http",
    "port": 80,
    "timeoutMs": 3000
  },
  "control": {
    "kind": "websocket",
    "scheme": "ws",
    "port": 9999,
    "path": "/",
    "lifecycle": "perOperation"
  }
}
```

### Operation Example (Upload):
```json
"uploadFile": {
  "channel": "web",
  "method": "POST",
  "path": "/upload",
  "contentType": "multipart/form-data",
  "body": {
    "fileField": "file",
    "fileName": "{{fileName}}",
    "extraFields": { "print": "{{autoStart}}" }
  }
}
```

---

## 📌 5. `state` Telemetry Block

Maps raw manufacturer payloads into standard MakerSpell telemetry using JSONPath:

```json
"state": {
  "temperature": {
    "hotendActual": "$.nozzleTemp",
    "hotendTarget": "$.nozzleTargetTemp",
    "bedActual": "$.bedTemp",
    "bedTarget": "$.bedTargetTemp"
  },
  "job": {
    "fileName": "$.curGcodeFile",
    "progress": { "path": "$.printProgress", "scale": 0.01 },
    "timeRemainingSeconds": "$.remainingTime"
  }
}
```
