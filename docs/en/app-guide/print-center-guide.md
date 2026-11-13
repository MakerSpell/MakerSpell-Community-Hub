# Print Center & Multi-Printer Monitoring

The **Print Center** is designed for makers, print farm operators, and workshops managing multiple 3D printers simultaneously.

### Print Center on Every Screen

The same live fleet dashboard rearranges itself for your device. The screenshots show the **Production Farm** tab, where quantity-based production orders are queued; the other tabs (Active, Ready, History, Care Farm, Progress) share the layout.

<div class="device-viewer">
<input class="dv-input" type="radio" name="dv-printcenter" id="dv-printcenter-desktop" checked>
<input class="dv-input" type="radio" name="dv-printcenter" id="dv-printcenter-tablet">
<input class="dv-input" type="radio" name="dv-printcenter" id="dv-printcenter-mobile">
<div class="dv-tabs">
<label for="dv-printcenter-desktop"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8"/><path d="M12 17v4"/></svg><span class="dv-label">Desktop</span><span class="dv-size">1280 px</span></label>
<label for="dv-printcenter-tablet"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="4" y="2" width="16" height="20" rx="2"/><path d="M12 18h.01"/></svg><span class="dv-label">Tablet</span><span class="dv-size">768 px</span></label>
<label for="dv-printcenter-mobile"><svg width="16" height="16" aria-hidden="true" focusable="false" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="7" y="2" width="10" height="20" rx="2.5"/><path d="M11 18h2"/></svg><span class="dv-label">Mobile</span><span class="dv-size">412 px</span></label>
</div>
<div class="dv-panels">
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-print-center-desktop.png" alt="Print Center — Desktop" loading="lazy">
<figcaption><strong>Desktop</strong> — Panels sit side by side in a wide grid, ideal for a workstation.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-print-center-tablet.png" alt="Print Center — Tablet" loading="lazy">
<figcaption><strong>Tablet</strong> — Panels reflow into a comfortable, touch-friendly grid.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-print-center-mobile.png" alt="Print Center — Mobile" loading="lazy">
<figcaption><strong>Mobile</strong> — The dashboard becomes a single scrolling column that fits in one hand.</figcaption>
</figure>
</div>
<div class="dv-hint">Layouts captured at 1280 px, 768 px and 412 px width.</div>
</div>

---

## 1. Metric Badges

At the top of the Print Center, live badges summarize your fleet status:
- **Active Jobs:** The number of printers currently preheating, calibrating, or laying down plastic.
- **Ready Files:** Sliced G-code files queued up for printing.
- **Online Printers:** Connected, responding machines across your network.

---

## 2. Real-Time Printer Cards

Each printer card provides instant telemetry:

- **State Indicators:**
  - 🟢 **Green (Idle):** Standby, bed clear, ready for the next job.
  - 🔵 **Blue (Printing):** Actively extruding; includes live percentage and progress bar.
  - 🟡 **Yellow (Paused):** Paused for filament swap or manual inspection.
  - 🔴 **Red (Offline):** Machine powered off or network dropped.
- **Job Progress:** Current file name, model thumbnail, completion percentage (`65%`), and time remaining (`14m 20s`).
- **Temperatures:** Real-time hotend and heatbed readings versus targets (`220°C / 60°C`).
- **Quick Controls:**
  - **Pause / Resume:** Temporarily halt printing in emergencies.
  - **Cancel Print:** Abort the current job with confirmation dialog.
  - **Open Dashboard:** Tap to enter the full two-column control cockpit.
