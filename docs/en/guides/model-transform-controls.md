# Model Transform Controls Guide (Move, Rotate, Scale)

Precise placement, orientation, and scaling of 3D models on the build plate are essential steps when preparing a print. MakerSpell features streamlined, professional transform tool panels designed for fast, accurate adjustments without visual clutter.

---

## 🎛️ Activating Transform Modes

When a model is selected on the virtual build plate, the top editor toolbar provides direct access to the three primary spatial manipulation tools:

1. **Move (Translate)**: Adjusts the model's physical position along the X, Y, and Z axes.
2. **Rotate**: Rotates the model around any axis in degrees.
3. **Scale**: Resizes the model proportionally or per-axis using scale percentages or target millimeter dimensions.

Clicking any of these tools opens a compact control panel anchored at the top-left of the viewport. Each panel can be dismissed at any time by clicking the **Close (✕)** button in the top-right corner or pressing `Esc`.

---

## 📍 Move (Position Control)

The Move panel displays the model's world coordinates relative to the build plate:

- **Position Inputs (X, Y, Z)**: Enter exact coordinates in millimeters.
  - **X Axis (Red badge)**: Controls left-to-right positioning across the width of the build plate.
  - **Y Axis (Green badge)**: Controls front-to-back positioning along the depth of the build plate.
  - **Z Axis (Blue badge)**: Displays and controls the vertical elevation. By default, the model's base is automatically snapped flush to the build plate (`Z = 0`).
- **Center Button**: Instantly centers the model at the exact midpoint of the build plate and re-snaps its base to the print surface.

---

## 🔄 Rotate (Angular Control)

The Rotate panel provides fine-grained angular control:

- **Rotation Inputs (X, Y, Z)**: Enter angles in degrees (`°`) to rotate around the chosen axis.
  - **X Axis (Red badge)**: Pitch (tilting front-to-back).
  - **Y Axis (Green badge)**: Roll (tilting side-to-side).
  - **Z Axis (Blue badge)**: Yaw (spinning horizontally on the bed).
- **Reset Button**: Restores the model's rotation back to its original orientation (`0.0°, 0.0°, 0.0°`).

---

## 📐 Scale (Dimensions & Percentage)

The Scale panel gives you dual-control over both relative scale and absolute physical dimensions:

- **Scale (% Row)**: Enter a target percentage for each axis (default `100.0%`).
- **Size (mm Row)**: Enter target dimensions in millimeters for X, Y, and Z. Adjusting the millimeter size automatically updates the percentage fields, and vice versa.
- **Uniform Scale Checkbox**: When checked, resizing any single axis proportionally rescales the other two axes to preserve the model's aspect ratio. Uncheck it for freeform stretching along individual axes.
- **Reset Button**: Restores the model to its original 1:1 scale (`100.0%`).

---

## 💡 Keyboard Shortcuts & Quick Tips

- **Direct Shortcuts**: Press `M` to activate Move, `R` for Rotate, and `S` for Scale.
- **Gizmo Interaction**: You can drag the 3D handles directly on the canvas or type exact values into the panel inputs. The panel inputs reflect gizmo movements in real time.
- **Arrow Keys**: With an input field focused, you can quickly adjust values using your keyboard.
