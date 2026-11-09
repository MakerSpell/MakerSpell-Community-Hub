# 🎨 Multi-Color Printing & Material Management (CFS / AMS)

MakerSpell delivers first-class support for multi-color, multi-material extrusion systems including Creality CFS and Snapmaker AMS.

---

## 📌 1. Filament Slot Visualization

The device dashboard and print dialog display every loaded spool:
- **Color Swatches:** Accurate hex color representations for each loaded spool.
- **Material Classification:** Automatically identifies PLA, PETG, ABS, TPU, PA-CF, etc.
- **Empty Slot Detection:** Unloaded bays are greyed out to prevent accidental extrusion commands.

---

## 📌 2. Sliced Model to Physical Slot Mapping

When preparing a multi-material print:
1. The G-code sender analyzes the model's required filaments.
2. It automatically matches each model color to the closest slot on your printer.
3. If a required color is missing from the machine, a visual mapping picker prompts you to remap that color to an existing spool.
4. Once verified, the job initiates with correct toolchange macros.

---

## 📌 3. External Spool Mode

For single-material prints using a generic side-mounted spool holder:
- The system automatically transitions to **"External Spool"** mode.
- Prints proceed without multi-slot checks or unnecessary purge tower overhead.
