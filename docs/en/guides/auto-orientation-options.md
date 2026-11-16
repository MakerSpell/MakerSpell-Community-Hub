# Auto Orientation Options Guide

When preparing complex 3D models for printing, finding the optimal angle and orientation on the build plate can drastically reduce print time, minimize wasted support material, and improve surface quality.

MakerSpell features an intelligent Auto Orientation system accessible directly from the top editor toolbar.

---

## 🧭 Opening the Options Menu

1. Select a model on the virtual build plate.
2. In the top toolbar, click the **Auto Orient** icon (or press its assigned shortcut).
3. A floating card titled **Auto orientation options** appears right beneath the button.

---

## ⚙️ Orientation Modes

The popover provides three specialized orientation strategies:

| Mode | Strategy & Best Use Case |
|---|---|
| **Default** | **Balanced contact and overhangs.** Finds the optimal balance between a solid bed contact area for maximum adhesion and gentle overhang angles. Recommended for general 3D models and figurines. |
| **Minimize support volume** | **Stricter overhang penalty.** Prioritizes angles that require the least amount of support structures. Ideal for organic shapes, detailed miniatures, and models with intricate overhangs where post-processing and support removal are tedious. |
| **Minimize print time** | **Lower Z-height profile.** Penalizes tall vertical profiles to minimize the total layer count. Ideal for functional parts, flat mechanical plates, and brackets where fast turnaround and layer strength in the horizontal plane are desired. |

---

## 🚀 Actions

- **Orient**: Evaluates the model's geometry using the selected strategy, calculates the optimal rotational angles, and smoothly orients the model onto the build plate with automatic Z-bed snapping.
- **Reset**: Restores the model's original rotation to `(0°, 0°, 0°)` while keeping the model safely resting on the build plate.

---

## 💡 Tips & Best Practices

- **Bed Adhesion**: After running Auto Orientation, verify that the bottom surface contact area is sufficient. If the contact area is narrow, consider enabling a Brim or Mouse Ears under Print Settings.
- **Multiple Models**: Auto Orientation works per selected model. You can optimize each model on your plate independently according to its geometry.
