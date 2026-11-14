# How to Add and Test a New Printer Profile

MakerSpell uses an open, declarative driver specification (`profile-v2`) to connect with hundreds of 3D printer models across different manufacturers. This guide walks you through importing, verifying, and testing a custom driver profile **directly from the MakerSpell Desktop or Mobile app**—with zero coding or terminal tools required.

---

## 1. Prerequisites: Driver Profile File (.json)

A printer driver profile is a standard `.json` configuration file that contains:

1. **Identity:** Manufacturer name, supported printer models, and unique profile ID (e.g., `community.mybrand-modelx.v2`).
2. **Channels:** Network connection protocol and listening port (e.g., HTTP / WebSocket port `80`, `7125`, or `9999`).
3. **Operations:** Service endpoint paths for polling status and transferring print jobs (e.g., `/api/status`, `/printer/info`).
4. **Normalized State:** Keys for reading live hotend and bed temperatures from the printer telemetry response.

> [!TIP]
> For schema details and example configurations, refer to the [profile-v2 Specification](../schemas/profile-v2-specification.md).

---

## 2. In-App Profile Import & Automatic Verification

### Step 1: Open the Driver Rules Screen
1. Launch the MakerSpell application (Desktop or Mobile).
2. Navigate to **Settings** from the sidebar navigation or window header.
3. Select **"Printer Connection & Interface Rules"** (`Community Profiles`).

### Step 2: Select Your JSON Profile File
1. Click or tap the **"Import Profile (.json)"** button (file/folder icon) in the top-right toolbar.
2. Select your prepared `.json` file from your device file manager (Windows File Explorer, macOS Finder, or Android/iOS Files).

### Step 3: Automated Validation & Safe-Mode Enforcement
Upon file selection, the built-in validation engine immediately checks the configuration:
- **Schema Validation:** Verifies syntax, required keys, channel definitions, and data types. Any discrepancies are highlighted in a clear error card.
- **Hardware Safe-Mode:** For community hardware that has not undergone physical laboratory verification, **Safe-Mode** is automatically active. This ensures file transfers proceed normally, while physical print initiation remains safely on the machine panel under operator supervision.

---

## 3. Live Device Connectivity Test

Before saving the driver to your active setup, you can test communication against your physical printer:

1. Enter your printer's local IP address into the **"Printer IP / Hostname"** field (e.g., `192.168.1.120`). If you have a discovered printer, this field is automatically pre-filled.
2. Tap the **"Test Connection"** button.
3. MakerSpell probes the specified service port and endpoint:
   - ✅ **Green Success Badge:** Confirms successful printer communication, reporting measured network latency (e.g., `42 ms`) and status.
   - ❌ **Connection Alert:** Reports socket errors, timeouts, or closed ports if the device is unreachable or configured with an incorrect port.

---

## 4. Activating or Customizing the Profile

- **Immediate Activation:** When testing passes, click **"Install & Activate"** to bind the profile to your printer. It becomes immediately available in the Print Center.
- **In-App Visual Customization:** You can also click **"Open in Editor"** to adjust dashboard cards, camera widgets, filament slot mappings, or custom action buttons using MakerSpell's built-in Form and Visual Preview editor.

---

## 5. Contributing to the Community Catalog (Optional)

Once your profile is tested and working reliably with your printer, you can share it with the broader 3D printing community:
1. Submit your JSON profile as a Pull Request to the [MakerSpell Community Hub](https://github.com/MakerSpell/MakerSpell-Community-Hub) repository.
2. Following community review, your profile is incorporated into the official catalog and made available to all global users.
