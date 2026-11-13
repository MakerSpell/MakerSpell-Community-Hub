# Device Control Panel (Camera, Temperatures & Motion)

Opening a printer from the fleet list reveals the **Two-Column Desktop Dashboard**, optimized for 1100px+ displays (and responsive single-column on mobile).

### Device Control Panel on Every Screen

The same control cockpit rearranges itself for your device. Pick a form factor to compare:

<div class="device-viewer">
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-desktop" checked>
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-tablet">
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-mobile">
<div class="dv-tabs">
<label for="dv-controls-desktop"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8"/><path d="M12 17v4"/></svg><span class="dv-label">Desktop</span><span class="dv-size">1280 px</span></label>
<label for="dv-controls-tablet"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="4" y="2" width="16" height="20" rx="2"/><path d="M12 18h.01"/></svg><span class="dv-label">Tablet</span><span class="dv-size">768 px</span></label>
<label for="dv-controls-mobile"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="7" y="2" width="10" height="20" rx="2.5"/><path d="M11 18h2"/></svg><span class="dv-label">Mobile</span><span class="dv-size">412 px</span></label>
</div>
<div class="dv-panels">
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-desktop.png" alt="Device Control Panel — Desktop" loading="lazy">
<figcaption><strong>Desktop</strong> — The live camera and the motion pad sit side by side on a wide monitor.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-tablet.png" alt="Device Control Panel — Tablet" loading="lazy">
<figcaption><strong>Tablet</strong> — Both halves stay visible but stack into a taller, touch-first arrangement.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-mobile.png" alt="Device Control Panel — Mobile" loading="lazy">
<figcaption><strong>Mobile</strong> — The panels become a single column you can scroll with one thumb.</figcaption>
</figure>
</div>
<div class="dv-hint">Layouts captured at 1280 px, 768 px and 412 px width.</div>
</div>

---

## 1. Left Column: Telemetry & Visual Monitoring

- **Live Camera Stream:**
  Low-latency video preview from onboard cameras (CrealityOS MJPEG / WebRTC / Moonraker). Inspect the critical first layer without walking across your workshop.
- **Active Job Card:**
  Displays current layer (`120 / 450`), remaining print time, progress bar, and model thumbnail.
- **Filament Slot Matrix:**
  Visual palette indicating every filament bay in your CFS or AMS unit, including color swatches and material types.

---

## 2. Right Column: Manual Overrides & Hardware Commands

- **Thermal Controls:**
  - **Hotend:** Quick presets (PLA 200°C, PETG 240°C, ABS 260°C) or custom target input.
  - **Heated Bed:** Bed preheating and cool-down toggles.
  - **Chamber Light:** On/off toggle for onboard LED bars.
- **Cooling Fans:**
  - Fine-tune Model Fan, Auxiliary Fan, and Rear Exhaust Fan speeds (0–100%).
- **XYZ Jog & Homing:**
  - Circular jog wheel for X/Y movements and vertical Z buttons.
  - Step distance selectors: `0.1 mm`, `1 mm`, `10 mm`, and `100 mm`.
  - Center **Home All** or axis-specific homing commands.
  - *Safety Lock:* Motion controls are automatically disabled while printing to avoid toolhead collisions.
- **Local Storage Browser:**
  - View stored G-code files on the printer eMMC/SD card, delete old prints, or start reprints.
