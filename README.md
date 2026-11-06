# Dome 3D Print Project

CAD source files, print-ready models and print settings for a modular dome built from hexagon and pentagon panels.

All parts were designed in **Autodesk Fusion** and sliced in **Bambu Studio 02.08.02.61** for a **Bambu Lab P1S**.

## Repository Layout

```
dome-3d-print/
├── cad/                 Fusion (.f3d) and STEP source files - edit these to change the design
├── models/
│   ├── dome_stl/        v2 panels, 4.0 mm skin (original revision) + sliced LCD panel (.gcode.3mf)
│   ├── dome_stl_v3/     v3 panels, 2.4 mm skin (faster, lighter - use these for new prints)
│   ├── dome_Gcode/      sliced dome plates
│   └── Gcode/           sliced files for other parts (sliding gate, O-ring)
├── production_cost/     cost sheets (.xlsx, .docx, .md)
├── PRINT_SETTINGS.md
└── README.md
```

## Revisions

| Revision | Folder | Panel skin | Notes |
|----------|--------|------------|-------|
| v2 | `models/dome_stl/` | 4.0 mm | Original. Matches the Fusion source files in `cad/`. |
| v3 | `models/dome_stl_v3/` | 2.4 mm | Made from v2 by moving the inner skin surface outward 1.6 mm. Outer dome surface, outer size, 3.5 mm joint edges, bolt holes and logo engraving are unchanged, so v3 panels fit v2 panels. |

v3 is a mesh edit. The Fusion files in `cad/` still describe v2. To change the design again, edit the Fusion file and set the shell thickness to 2.4 mm there.

On the LCD panel, the area around the LCD window keeps the original 4.0 mm skin, with a smooth taper to 2.4 mm. This keeps the 1.1 mm screen seat inside the window unchanged.

## Parts

Sizes are the same for v2 and v3. Inner skin radius is 196 mm (v2) or 197.6 mm (v3). Outer radius is 200 mm.

| Part | v2 STL | v3 STL | Fusion source | Size (X x Y x Z mm) | Volume v2 / v3 (cm3) |
|------|--------|--------|---------------|---------------------|----------------------|
| Hexagon panel | `part-hexagon-v2.stl` | `part-hexagon-v3.stl` | `part-hexagon-v2.f3d` | 157.9 x 153.5 x 31.6 | 92.0 / 66.6 |
| Hexagon panel with logo | `part-hexagon-logo-v2.stl` | `part-hexagon-logo-v3.stl` | `part-hexagon-logo-v2.f3d` | 142.7 x 161.4 x 31.5 | 78.7 / 58.5 |
| Hexagon panel with logo and LCD | `part-hexagon-logo-lcd-v2.stl` | `part-hexagon-logo-lcd-v3.stl` | `part-hexagon-logo-lcd-v2.step` | 161.4 x 142.7 x 31.6 | 74.0 / 58.1 |
| Half hexagon panel | `part-half-hexagon-v2.stl` | `part-half-hexagon-v3.stl` | `part-half-hexagon-v2.f3d` | 140.2 x 131.0 x 31.6 | 49.7 / 35.8 |
| Pentagon panel | `part-pentagon-v2.stl` | `part-pentagon-v3.stl` | `part-pentagon-v2.f3d` | 130.6 x 125.4 x 27.1 | 64.0 / 47.8 |
| Full dome assembly | - | - | `dome-full-assembly.f3d` | reference only | - |

All v3 meshes are watertight and manifold.

## Quick Start - Print a New Panel

1. Install [Bambu Studio](https://bambulab.com/en/download/studio) (tested with 02.08.02.61).
2. Open the `.stl` from `models/dome_stl_v3/`.
3. Apply the **v3 profile** in [PRINT_SETTINGS.md](PRINT_SETTINGS.md). Print the panel standing on one joint edge.
4. Check the plate is **Textured PEI**, the filament is **Bambu PLA Basic** and the nozzle is **0.4 mm**.
5. Slice, check that supports reach every overhang, then print.

## Print Settings Summary

Full details are in [PRINT_SETTINGS.md](PRINT_SETTINGS.md).

| Setting | v3 panels (recommended) | v2 LCD panel (as printed) |
|---------|-------------------------|---------------------------|
| Printer | Bambu Lab P1S, 0.4 mm nozzle | Bambu Lab P1S, 0.4 mm nozzle |
| Filament | Bambu PLA Basic | Bambu PLA Basic |
| Orientation | Standing on one joint edge | Standing on one joint edge |
| Layer height | 0.28 mm plain, 0.24 mm logo / LCD | 0.2 mm |
| Wall generator / loops | Arachne / 3 | Classic / 3 |
| Infill | 15 % gyroid | 15 % grid |
| Supports | Tree (auto), Tree Hybrid, 30 deg | Tree (manual), 30 deg |
| Brim | Outer only, 8 mm | None |
| Nozzle / bed temperature | 220 C / 55 C | 220 C / 55 C |
| Print time, LCD panel | about 2 h - 2 h 20 min (estimate, not sliced) | 3 h 08 min (sliced) |
| Filament, LCD panel | about 65 g (estimate, not sliced) | 87.2 g (sliced) |

## Notes

- Dimensions come from the STL files and are in millimetres.
- Use `-v3` files for new prints. `-v2` files are kept for reference and to match the CAD source.
- The `.f3d` files need Autodesk Fusion to open.

## License

No license chosen yet. Add a `LICENSE` file before sharing publicly.
