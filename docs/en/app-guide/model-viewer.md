# 3D Model Viewer, Plate Layout & Color Painting

The MakerSpell desktop and mobile client features a high-performance 3D canvas supporting STL, 3MF, and OBJ files.

---

## 1. Navigation & Camera Controls

- **Orbit (Rotate):** Left-click and drag (or one-finger drag on mobile) to inspect your model from any angle.
- **Pan:** Right-click and drag to move the model across the virtual build plate.
- **Zoom:** Mouse scroll wheel or two-finger pinch to zoom in on intricate overhangs.
- **Build Plate Grid:** Visual millimeter grid matching your printer's physical dimensions.

---

## 2. Transforming & Plate Placement

- **Auto-Center:** Quickly centers the model on the build volume.
- **Precision Move & Rotate:** Use the responsive transform toolbar to translate (X, Y) and rotate (X, Y, Z). Input fields feature OrcaSlicer and CAD-standard color-coded axis badges (Red = X, Green = Y, Blue = Z) and auto-adapt to mobile, tablet, and desktop screens without horizontal clipping.
- **Scaling:** Scale uniformly with the lock toggle or enter exact millimeter dimensions for X, Y, or Z independently.
- **Lay Flat:** Click any planar surface of your model to immediately snap it flat against the print bed for optimal bed adhesion.

---

## 3. Multi-Color Painting Tool

For multi-material setups:
- Select the **"Paint"** brush from the top toolbar.
- Choose a target color matching your loaded filament slots.
- Use **Sphere Brush**, **Triangle Fill**, or **Angle Detection** to paint distinct features.
- Color designations are automatically preserved when slicing into multi-tool G-code.
