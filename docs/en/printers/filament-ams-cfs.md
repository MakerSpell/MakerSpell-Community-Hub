# Multi-Color Systems Integration (Creality CFS, Snapmaker AMS)

Modern 3D printers incorporate multi-color and multi-material handling systems. MakerSpell normalizes slot states, material tags, and color values into a unified UI experience.

---

## 1. Filament Slot Attributes

In the user interface, each loaded filament spool displays:
- **Slot Identifier:** `Slot 1`, `Slot 2`, `Slot 3`, `Slot 4`.
- **Material Type:** PLA, PETG, ABS, TPU, PA-CF, etc.
- **Color Swatch:** Visual color swatch matching the real-world spool.
- **Occupancy State:** Real-time detection of spool loaded vs. empty bay.
- **Estimated Weight:** Remaining filament weight (grams) where telemetry permits.
- **Custom Bay Label:** "CFS Slot 1", "External Spool", or user-assigned labels.

---

## 2. Sliced Model Matching & Error Handling

- **Automatic Matching:** When preparing a multi-color print, MakerSpell automatically cross-checks sliced tool requirements with loaded printer slots.
- **Fault Isolation:** If a printer’s CFS/AMS module is offline or disconnected, the main printer telemetry continues seamlessly; an isolated *"Could not read CFS slots"* warning appears with an inline Retry button.
- **External Spool Fallback:** Printers without multi-material units automatically default to single-spool mode.
