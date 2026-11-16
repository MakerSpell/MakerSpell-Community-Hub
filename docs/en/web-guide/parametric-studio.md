# Parametric 3D Model Studio & Generator

MakerSpell Studio (`/studio/parametric`) provides an interactive 3D modeling and customization environment directly in your browser. Whether you are generating personalized lithophane nightlights from photos or tailoring functional organizers to exact millimetric dimensions, the studio compiles real 3D geometries and lets you download print-ready STL files with zero slicing friction.

## 1. Built-in Procedural Generators

The studio comes equipped with ready-to-use parametric templates across several categories:

| Generator | Best For | Key Parameters |
| --- | --- | --- |
| **Lithophane Photo & Lamp** | Personalized photo panels, curved lamps, nightlights | Image upload, shape (curved, flat, cylinder, nightlight), width, min/max layer thickness, curve angle |
| **Custom Box & Organizers** | Millimetric hardware organizers, parts trays, boxes | Inner dimensions focus, dual-axis $N \times M$ compartments, lid style (snap-fit, sliding, none), stackable interlocking foot, clearance control |
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
- **HUD Telemetry & Live Dimensions Callout**: The bottom HUD displays live polygon counts, compilation time, and a real-time dimension badge showing exact **Outside dimensions ($W \times D \times H$)**, **Inside capacity**, and calculated **Internal Volume in $cm^3$**.
- **Instant Procedural Responsiveness**: When adjusting box organizers, sliders respond with sub-millisecond 60 FPS live feedback, updating both box and lid geometries instantly without compilation waiting.
- **Support-Free Print Plate Layout**: Choosing the "Box + Lid" layout places both components side-by-side on the build grid with the lid oriented flat-top down, ready for 100% support-free 3D printing.

## 3. Customizing External Models & 3D Typography (Thingiverse, GitHub)

You are not limited to built-in presets. When browsing models on MakerSpell with the **Editable (Parametric)** filter:

1. Click **Customize in 3D Studio** on any supported model page.
2. The studio loads a dedicated **External Model Card** showing the source repository or platform badge, full model title, and a link to the original design.
3. Form controls appear in the sidebar for every detected dimension, wall thickness, custom text field, and toggle.
4. **Standard Libraries & 3D Typography**: Full out-of-the-box support for the most popular OpenSCAD libraries:
   - **MCAD**: Gears, bearings, stepper motor mounts, standard boxes, and hardware fasteners.
   - **threads.scad**: High-precision metric screw threads, bolt profiles, and jar lids.
   - **Round-Anything**: Polyround fillets, soft rounded corners, and ergonomic bevels.
   - **Write.scad & DXF Typography**: Curved embossed lettering on cylinders, food bowls, and name tags.
   - **Multi-File Imports**: Accompanying component meshes (`import("part.stl")` or vector files) are automatically recognized and mounted for multi-part assemblies.
5. If you wish to test procedural templates, click **Built-in Presets** to switch between templates and return to your external model at any time.

## 4. Accelerated Manifold In-Browser Engine & Draft Mode

MakerSpell Studio features a high-performance hybrid computing architecture:

- **Manifold CSG Engine (10x-50x Faster)**: Models are evaluated using the modern Manifold boolean engine, compiling complex geometries in tens of milliseconds directly inside your browser. If non-manifold legacy shapes are encountered, the engine seamlessly falls back to CGAL to guarantee 100% render reliability.
- **Direct Binary STL Generation**: Clean binary meshes are exported natively without browser memory bloat, providing instant updates for models with hundreds of thousands of triangles.
- **Real-Time Draft Mode**: As you drag sliders, the studio evaluates geometries in high-speed draft mode (`Draft`), providing immediate visual feedback in under 100 milliseconds. When you release the slider, the model compiles into full high-resolution precision.
- **Automatic Cloud Fallback**: On low-memory devices or older browsers, the studio seamlessly switches to cloud computing without interrupting your design flow.

## 5. Exporting & Slicing for 3D Printing

When you are satisfied with your customized model:

1. **Download STL**: Click **Download STL** to save a binary mesh file directly to your disk.
2. **Slice in App**: Click **Slice in App** to automatically launch MakerSync or OrcaSlicer via deep-link integration. Your customized file is prepped and ready for slicing without manual drag-and-drop steps.
3. Open the file in your preferred slicer (MakerSync, Bambu Studio, OrcaSlicer, PrusaSlicer, or Creality Print) to start printing.

> [!IMPORTANT]
> The exported STL files use standard binary encoding with optimized surface normals, making them compatible with every desktop slicer and 3D printer without requiring mesh repair or repair tools.
