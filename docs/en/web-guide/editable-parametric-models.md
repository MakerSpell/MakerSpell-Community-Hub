# Editable (Parametric) Models Across Every Platform

Most 3D models are finished shapes — you print them as they are. **Editable models** are different: their geometry is generated from numbers you can change, so one download can become a hundred sizes, labels or variants. MakerSpell lets you find them anywhere with a single filter, even though every marketplace calls the feature something else.

## 1. Turning the filter on

1. Open **Browse**.
2. Pick one platform (single mode) or several (multi mode).
3. Click **Editable (Parametric)** in the control bar above the results.

The button stays highlighted while the filter is active, and the active-filter counter at the top increases by one. Click it again to return to the normal feed.

> [!TIP]
> The filter works in both modes. In single-platform mode it is the only global filter that still applies — sorting, time range and license are governed by that platform's own controls.

## 2. What happens on each platform

You never have to remember platform-specific terminology. MakerSpell translates the one filter into whatever that marketplace actually supports:

| Platform | What MakerSpell sends | What you get |
| --- | --- | --- |
| Thingiverse | `customizable=1` | Models published with the Thingiverse Customizer |
| Printables | OpenSCAD modeling app | Models authored in OpenSCAD, the source of their parameter editor |
| MakerWorld | `custom` and `param` model tags | Customizable and parametric designs together |
| Thangs | `.scad` added to the search text | OpenSCAD projects in the Thangs index |
| GitHub | The OpenSCAD catalog | Repositories whose source is a parametric `.scad` program |

Platforms with no editable-model mechanism of their own are **skipped** while the filter is on, rather than showing you a list that quietly ignores the filter.

> [!NOTE]
> MakerWorld availability depends on their servers answering normally. If that platform returns nothing, try again later or switch to another platform — the other sources are unaffected.

## 3. From a result to a working editor

Open any result that shows the **Parametric** badge. On platforms that let anyone download a model without signing in — Thingiverse, Printables and GitHub — the primary action on the model page is **Customize in 3D Studio**:

- The studio opens on that model. When the author published the editable source as a `.scad` file, its parameters are detected automatically and appear as sliders and number fields.
- Sliders and number fields appear for width, height, wall thickness, hole diameter, text and so on.
- Export the result as a mesh when you are happy with it.

On platforms that require an account before a file can be downloaded, the primary action stays **Open in MakerSpell App** instead, because the desktop and mobile apps can hold that platform session. The studio shortcut remains available as a secondary button whenever the model is parametric.

> [!IMPORTANT]
> Editing a model produces your own local variant. The original is never modified, but the author's license still applies to anything you publish.

## 4. When nothing useful comes back

| Symptom | Fix |
| --- | --- |
| No results at all with the filter on | The selected platform may have no editable models matching your words — clear the search box, or select additional platforms |
| Results appear unrelated | Switch off the filter and confirm the model really is parametric; some authors tag ordinary models loosely |
| The studio opens but no parameters are listed | The `.scad` source may have no top-level parameters; you can still read and edit the code in the editor |
| A platform never returns anything | That source is skipped by design when it cannot honour the filter |

## Related guides

- [Parametric GitHub Models (OpenSCAD)](parametric-github-models.md)
- [26-Platform 3D Model Search & Filters](model-search.md)
