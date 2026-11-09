# 🚀 G-code Transfer & Slicing Integration

Sending sliced 3D models to your hardware in MakerSpell is fast, wireless, and protected by physical safety checks.

---

## 📌 1. Sending Print Jobs Step-by-Step

1. Prepare your 3D model on the virtual build plate and click **"Slice"**.
2. Once slicing finishes, the **"Send G-code"** modal opens automatically.
3. Review your print statistics:
   - File name and estimated print time.
   - Material weight (grams) and filament length (meters).
   - Target nozzle and heated bed temperatures.
4. Select your target printer from the **"Select Printer"** dropdown.
5. If the printer has a multi-color system (CFS/AMS), verify the filament slot mappings.
6. Choose your delivery mode:
   - **"Upload Only":** Sends the G-code directly to printer storage without initiating heating.
   - **"Upload & Print":** Transfers the file and starts the print sequence immediately.

---

## 📌 2. The Safe-Mode Hardware Shield

If the selected printer is an unverified community model (e.g. third-party Klipper boards, Bambu LAN mode, or custom DIY rigs):

- The **"Upload & Print"** button is automatically locked.
- Only **"Upload Only"** is enabled.
- Sliced files are stored safely on the machine. You must inspect the physical build surface, check adhesion, and start the job from the machine's onboard touchscreen. This prevents fire hazards and collision damage.
