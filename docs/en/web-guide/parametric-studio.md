# Parametric 3D Model Studio & Generator

MakerSpell Studio (`/studio/parametric`) provides an interactive 3D modeling and customization environment directly in your browser. Whether you are generating personalized lithophane nightlights from photos or tailoring functional organizers to exact millimetric dimensions, the studio compiles real 3D geometries and lets you download print-ready STL files with zero slicing friction.

## 1. Built-in Procedural Generators

The studio comes equipped with ready-to-use parametric templates across several categories:

| Generator | Best For | Key Parameters |
| --- | --- | --- |
| **Lithophane Photo & Lamp** | Personalized photo panels, curved lamps, nightlights | Image upload, shape (curved, flat, cylinder, nightlight), width, min/max layer thickness, curve angle |
| **Parametric Box & Lid** | Millimetric hardware organizers, parts trays, boxes | Width, length, height, corner radius, wall thickness, lid style (sliding, snap-fit, open), internal dividers |
| **Gridfinity Standard Bin** | Modular workshop and drawer organization systems | Grid units (42mm multiples in X and Y), height units (7mm multiples), scoop lip, label shelf, magnet holes |
| **3D Embossed Keychain** | Name tags, two-color keychains, custom badges | Text content, font size, text relief height, base thickness, keyring hole toggle |
| **OpenSCAD Code Playground** | Custom algorithmic designs and experiments | Direct code editor with automatic parameter extraction (sliders, toggles, dropdowns) |

> [!TIP]
> Each preset automatically exposes sliders and controls configured with safe minimum and maximum printing limits, ensuring your model remains structurally sound on any FDM or resin 3D printer.

## 2. Using the 3D Interactive Viewport

The interactive viewport renders real 3D geometry with realistic lighting, true-to-life bed leveling, and physical dimensions:

- **Build Plate Leveling**: All models automatically align upright with their base resting directly on top of the print grid ($Y = 0$), matching physical 3D printer slicing coordinates.
- **Distraction-Free Full Viewport**: Entering the studio automatically minimizes the main navigation sidebar to maximize the interactive 3D canvas.
- **Rotate (Orbit)**: Click and drag with your left mouse button (or swipe with one finger on mobile/touch screens).
- **Zoom**: Scroll your mouse wheel (or pinch with two fingers on mobile devices).
- **Wireframe Mode**: Click **Wireframe** in the top toolbar to inspect polygon density, mesh triangulation, and internal walls.
- **Backlight Preview**: For lithophanes, toggle **Light On / Light Off** to simulate how light shines through the translucent filament layers.
- **HUD Telemetry**: The bottom HUD displays live polygon counts (triangles), calculated bounding box dimensions in millimeters ($X \times Y \times Z$), and compilation time.

## 3. Customizing External Models & 3D Typography (Thingiverse, GitHub)

You are not limited to built-in presets. When browsing models on MakerSpell with the **Editable (Parametric)** filter:

1. Click **Customize in 3D Studio** on any supported model page.
2. The studio loads a dedicated **External Model Card** showing the source repository or platform badge, full model title, and a link to the original design.
3. Form controls appear in the sidebar for every detected dimension, wall thickness, custom text field, and toggle.
4. **Embossed 3D Typography**: Full support for legacy and modern font engines (including HarlanDMii `Write.scad` and DXF typography) ensures customized curved text, embossed pet names on food bowls, and label tags render accurately in 3D.
5. If you wish to test procedural templates, click **Built-in Presets** to switch between templates and return to your external model at any time.

## 4. Accelerated In-Browser Engine & Draft Mode

MakerSpell Studio features a hybrid computing architecture:

- **Hardware-Accelerated Client Engine**: Models are compiled directly inside your browser via WebAssembly (WASM). Initial assets are compressed to under 3 MB and permanently cached offline via Service Worker, resulting in zero network delays on subsequent visits.
- **Real-Time Draft Mode**: As you drag sliders, the studio evaluates geometries in high-speed draft mode (`Draft`), providing immediate visual feedback in under 200 milliseconds. When you release the slider, the model compiles into full high-resolution precision.
- **Automatic Cloud Fallback**: On low-memory devices or older browsers, the studio seamlessly switches to cloud computing without interrupting your design flow.

## 5. Exporting & Slicing for 3D Printing

When you are satisfied with your customized model:

1. **Download STL**: Click **Download STL** to save a binary mesh file directly to your disk.
2. **Slice in App**: Click **Slice in App** to automatically launch MakerSync or OrcaSlicer via deep-link integration. Your customized file is prepped and ready for slicing without manual drag-and-drop steps.
3. Open the file in your preferred slicer (MakerSync, Bambu Studio, OrcaSlicer, PrusaSlicer, or Creality Print) to start printing.

> [!IMPORTANT]
> The exported STL files use standard binary encoding with optimized surface normals, making them compatible with every desktop slicer and 3D printer without requiring mesh repair or repair tools.
