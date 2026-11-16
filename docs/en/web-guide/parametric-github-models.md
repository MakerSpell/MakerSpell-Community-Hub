# Parametric GitHub Models (OpenSCAD)

MakerSpell also indexes **parametric 3D models** published as OpenSCAD source on GitHub. Unlike STL files, these models are *code*: the shape is generated from adjustable numbers (width, height, wall thickness, hole diameter, label text and so on). You can browse them like any other model, and later open them in the Parametric Studio to change those numbers before exporting.

> [!NOTE]
> Parametric models are shared by the community under their own repository license. Always check the license shown on the model page before printing or reselling.

## 1. Finding parametric models

1. Open **Browse** from the main navigation.
2. In the platform filter on the left, select **GitHub** — or type **GitHub** into the search box to search only that source.
3. Type what you are looking for, for example *gridfinity*, *bracket*, *label*, *enclosure* or *openscad*.

Cards coming from GitHub show a **Parametric** badge, and their preview image is taken directly from the author's repository, so what you see is what the project actually builds.

> [!TIP]
> Searching without a platform filter mixes GitHub results with all other marketplaces. If you want only rewritable models, filter to GitHub first.

## 2. Reading a model page

Click any result to open its detail page. A GitHub model page shows:

| Section | What you get |
| --- | --- |
| Gallery | Images captured from the project repository and its documentation |
| Description | The project summary plus how many OpenSCAD source files it contains |
| Author | The repository owner, with avatar and a link to the original project |
| Stats | Stars (shown as likes) and forks (shown as downloads) |
| Tags | Repository topics, which also feed search |
| License | The license declared by the repository |
| Source files | The `.scad` files you can download or open in the studio |
| Actions | Save, share, open in the Parametric Studio, or visit the original project |

If a repository has no usable screenshots, MakerSpell draws a clean blueprint placeholder instead of a broken image, so no card is ever left blank.

## 3. Customizing in the studio

From a GitHub model page choose **Customize in 3D Studio**. The studio opens with the model's source attached so its parameters become sliders and number fields. Change the values, watch the preview update, then export the result as a mesh for slicing.

> [!IMPORTANT]
> Editing a GitHub model creates your own local variant. The original repository is never modified, and you do not need the author's permission to tweak parameters for personal use — but the license still applies to anything you publish.

## 4. Keeping the catalog fresh

The GitHub index is refreshed automatically once a day, so newly published and updated projects appear without any action from you. If a project looks out of date, open it and use the link to the original repository to confirm the latest state.

## Troubleshooting

| Symptom | Fix |
| --- | --- |
| No GitHub cards appear | Clear the search box, then re-select GitHub in the platform filter |
| A card shows a blueprint placeholder | That project has no images in its repository yet; open it and check the source files |
| A model page has no images | Same reason as above — the gallery falls back to the source file list |
| The studio says the model has no parameters | The project may ship plain `.scad` files without top-level parameters; you can still download and edit them locally |
