# Print Settings

The **v3 Profile** section gives recommended settings for the 2.4 mm panels in `models/dome_stl_v3/`. These have not been sliced or test-printed yet.

The **v2** sections record the settings actually used for the 4.0 mm panels. These values were read from the project settings stored inside the `.3mf` files (Bambu Studio 02.08.02.61).

## Equipment and Material

| Item | Value |
|------|-------|
| Printer | Bambu Lab P1S |
| Nozzle | 0.4 mm |
| Filament | Bambu PLA Basic (PLA, 1.75 mm, density 1.26 g/cm3) |
| Build plate | Textured PEI Plate |
| Slicer | Bambu Studio 02.08.02.61 |

## v3 Profile (2.4 mm skin) - Recommended

Use this profile for the 2.4 mm panels in `models/dome_stl_v3/`. These values are recommendations and have not been sliced or test-printed yet. Slice one panel first and record the real time and weight in the table at the end of this section.

### Orientation

Print each panel **standing on one joint edge**, the same way the v2 LCD panel was printed (673 layers at 0.2 mm, first-layer footprint 72.8 x 3.3 mm). In this orientation the outer dome surface is printed as walls, so it comes out smooth, and only the joint edges need supports.

Printing the panel flat on its joint edges is not recommended. The inner skin is never steeper than about 21 deg from horizontal, so the full underside would need support.

### Settings

| Setting | Value | Reason |
|---------|-------|--------|
| Layer height | 0.28 mm for plain panels, 0.24 mm for logo and LCD panels | About 30 % / 17 % fewer layers than 0.2 mm. Use 0.2 mm only if the small website text looks rough. |
| First layer height | 0.2 mm | Good adhesion on the narrow edge. |
| Wall generator | **Arachne** | Fills the 2.4 mm skin with about 6 lines of adjusted width. No infill or gap fill inside the skin, so less travel. |
| Wall loops | 3 | 3 loops on each side of the skin makes it fully solid. |
| Top / bottom shell layers | 4 / 3 | Standing up, these are only the narrow edges. |
| Sparse infill | 15 % gyroid | Only the 3.5 mm joint edges and LCD frame get infill. Gyroid has no crossing lines for the nozzle to hit. |
| Supports | Tree (auto), style Tree Hybrid | Supports the joint edge overhangs and the LCD frame. |
| Support threshold angle | 30 deg | |
| Support top Z distance | 0.2 mm | |
| Support interface top layers | 2 | Cleaner surface where supports touch. |
| Brim | **Outer only, 8 mm** | The panel stands about 135 mm tall on a 3.3 mm wide strip. A brim stops it from tipping or shifting. The v2 LCD print had no brim. |
| Outer wall acceleration | 5,000 mm/s2 (default stays 10,000) | Less wobble and ringing on a tall, thin part. |
| Prime tower | Off | Single colour only. Turn it back on for multi-colour logos. |
| Seam position | Aligned | |
| Speeds | Same as the speed table below | |
| Temperatures | Nozzle 220 C, bed 55 C (Textured PEI) | |
| Cooling | Part fan 100 %, off for the first layer | |

### Results

| Part | Time | Filament | Source |
|------|------|----------|--------|
| Hexagon with logo and LCD, v2 (4.0 mm, 0.2 mm layers, Classic walls) | 3 h 08 min | 87.2 g | Sliced, `models/dome_stl/logo_with_lcd_pentagon.gcode.3mf` |
| Hexagon with logo and LCD, v3 (2.4 mm, this profile) | about 2 h - 2 h 20 min | about 65 g | Estimate only, not sliced |
| Other v3 panels | not recorded | not recorded | Slice and add here |

## v2 Settings by Part

The sections below record the settings used for the v2 (4.0 mm) panels.

### v2 LCD panel as printed

Read from `models/dome_stl/logo_with_lcd_pentagon.gcode.3mf`. Profile `dome_setting`, layer height 0.2 mm, wall loops 3 (Classic), top / bottom 5 / 3, infill 15 % grid, supports tree (manual) at 30 deg with 0.2 mm top Z distance and 2 interface layers, **no brim**, prime tower enabled. 673 layers, 3 h 08 min, 87.18 g.

### v2 pentagon and hexagon with logo

Settings that differ between the two profiles are marked **bold**.

| Setting | Pentagon (`part-pentagon-v2.3mf`) | Hexagon with logo (`part-hexagon-logo-v2.3mf`) |
|---------|-----------------------------------|------------------------------------------------|
| Process profile | `dome_setting` (custom) | `0.20mm Standard @BBL X1C` |
| Layer height | 0.2 mm | 0.2 mm |
| First layer height | 0.2 mm | 0.2 mm |
| Line width (default / outer wall / infill) | 0.42 / 0.42 / 0.45 mm | 0.42 / 0.42 / 0.45 mm |
| Wall loops | **3** | **2** |
| Wall generator | Classic | Classic |
| Top shell layers | 5 | 5 |
| Bottom shell layers | 3 | 3 |
| Sparse infill density | 15 % | 15 % |
| Sparse infill pattern | Grid | Grid |
| Top surface pattern | Monotonic line | Monotonic line |
| Bottom surface pattern | Monotonic | Monotonic |
| Supports | **On - tree (auto)** | **Off** |
| Support threshold angle | **25 deg** | 30 deg (unused, supports off) |
| Supports on build plate only | No | No |
| Brim | Auto, 5 mm | Auto, 5 mm |
| Skirt loops | 0 | 0 |
| Ironing | Off | Off |
| Seam position | Aligned | Aligned |
| Print sequence | By layer | By layer |
| Prime tower | Enabled | Enabled |
| Bridge flow | 1 | 1 |
| Arc fitting | On | On |

## Temperatures

| Setting | Value |
|---------|-------|
| Nozzle, all layers | 220 C |
| Bed, Textured PEI | 55 C |
| Bed, Cool Plate (not used) | 35 C |
| Engineering plate | not set |

## Speed and Acceleration

| Setting | Value (mm/s) |
|---------|--------------|
| First layer | 50 |
| Outer wall | 200 |
| Inner wall | 300 |
| Sparse infill | 270 |
| Top surface | 200 |
| Default acceleration | 10,000 mm/s2 |

The second number stored in Bambu Studio for these speeds (350, 400, 370, 300) belongs to the second extruder profile and does not apply to this single-nozzle P1S.

## Cooling, Retraction and Flow

| Setting | Value |
|---------|-------|
| Part cooling fan | 100 % |
| Fan off for first | 1 layer |
| Retraction length | 0.8 mm |
| Z hop | 0.4 mm |
| Filament flow ratio | 0.98 |

## How to Print a New Panel (v3)

1. Open Bambu Studio and choose printer **Bambu Lab P1S 0.4 nozzle**.
2. Choose filament **Bambu PLA Basic @BBL P1S 0.4 nozzle**.
3. Import the `.stl` from `models/dome_stl_v3/`.
4. Set the plate type to **Textured PEI Plate**.
5. Turn the panel so it stands on one joint edge.
6. Apply the settings in **v3 Profile** above.
7. Slice and check the preview: supports must reach the joint edge overhangs and the LCD frame, and the brim must go all around the bottom edge.
8. Print. Remove the brim and supports after the plate cools.

## Not Recorded

Print time and filament weight are recorded only for the v2 LCD panel. Times for all v3 panels and for the other v2 panels are unknown. Slice each part once and add the numbers to the v3 Results table.
