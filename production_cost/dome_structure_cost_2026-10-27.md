# 3D-printed dome structure: preliminary production cost

Date: 2026-10-27. Currency: KRW. Scope: 20 printed structural panels plus printer electricity. Cable ties, electronics, labor, printer depreciation, and failed prints will be added later. Filament unit-price input: **₩24,200 per nominal 1 kg spool**, supplied by the user; the spool's net weight remains to be confirmed.

## Quantities and filament

The assembly chapter of `AI 스마트팜 활용하는 데이터 와 기계학습_최종버전_v3_2026.10.14.pptx` specifies 5 pentagons, 8 hexagons, 6 half hexagons, and 1 logo hexagon. The supplied STL folder contains matching models. The user confirmed that **all panels were printed with tree supports**. The logo estimate is from an existing sliced `.gcode.3mf` for the same STL geometry; other weights are fresh Bambu Studio CLI estimates with automatic tree supports. The proxy profile uses a Bambu Lab P1S, 0.4 mm nozzle, 0.2 mm layers, 15% grid infill, and PLA density 1.26 g/cm³. Pentagons use 3 walls; regular and half hexagons use 2. The 3DK Korea filament grade KPLA00-YE2402 was not independently verified for density or price. Actual support placement may differ from the automatic slicer estimate.

| Panel | Qty | PLA per part | Total PLA | Basis |
|---|---:|---:|---:|---|
| Pentagon | 5 | 83.32 g | 416.60 g | CLI slice, tree supports |
| Hexagon | 8 | 113.73 g | 909.84 g | CLI slice, tree supports |
| Half hexagon | 6 | 62.93 g | 377.58 g | CLI slice, tree supports |
| Logo/LCD hexagon | 1 | 87.18 g | 87.18 g | Existing sliced file, supports |
| **Dome total** | **20** | | **1,791.20 g (1.791 kg)** | |

The existing logo print file uses manually specified tree supports: 87.18 g, compared with 91.88 g from a new automatic tree-support slice. This 5% difference shows that the estimate for the other panels depends on support placement. Treat **about 1.7–1.8 kg** as the planning range until their original G-code or Bambu Studio print history is available. Two nominal 1 kg spools would cover the estimated print with about 209 g left, before failed prints or purge waste. Cost below is for consumed filament, not automatically the price of two whole spools.

## Time and electricity

The user's actual-time estimate is 2 h 45–50 min per full panel. Using 2 h 50 min for each of 14 full panels and 1 h 30 min for each of 6 half panels gives **48 h 40 min**, rounded to **about 49 printer-hours**. This uses observed/remembered times rather than the new slicer's time predictions, which differ with profile and supports.

Electricity planning assumption: **0.105 kW average while printing PLA** on a P1S. Estimated energy: `48.6667 h × 0.105 kW = 5.11 kWh`. A plug-in energy meter would give a more accurate result, including warm-up and idle periods.

## Busan residential electricity calculation

Assumption: residential low-voltage electricity, October 2026, on an existing household account. Busan's Gaya-dong uses the same KEPCO residential tariff as elsewhere in Korea. The applicable energy tier depends on the household's **total monthly consumption**. KEPCO's ordinary-season low-voltage usage charges are ₩120.0/kWh for the first 200 kWh, ₩214.6/kWh for 201–400 kWh, and ₩307.3/kWh above 400 kWh. Add ₩9/kWh climate/environment charge and ₩5/kWh Q4 2026 fuel adjustment, then approximately 10% VAT and the 2.7% electricity-industry fund levy. Existing monthly base charges are excluded from incremental cost unless this print pushes the account into a higher billing tier.

| Existing household usage tier | Incremental electricity calculation | Estimated electricity cost |
|---|---:|---:|
| Up to 200 kWh/month | 5.11 × (120 + 9 + 5) × 1.127 | **₩772** |
| 201–400 kWh/month | 5.11 × (214.6 + 9 + 5) × 1.127 | ₩1,317 |
| Above 400 kWh/month | 5.11 × (307.3 + 9 + 5) × 1.127 | ₩1,850 |

## Structure cost

Using the user's **₩24,200 price as the price of 1 kg of net filament**, and the first residential usage tier as the working electricity estimate:

| Item | Calculation | Example cost |
|---|---:|---:|
| Filament | 1.7912 kg × ₩24,200/kg | ₩43,347 |
| Electricity | 5.11 kWh in first tier, including VAT and levy | ₩772 |
| **Structure total** | | **₩44,119** |

The [3DK filament page](http://3dk.or.kr/prod_fila.html) could not be retrieved, so **₩24,200 comes from the user rather than a verified online listing**. Confirm that it is the price for a net 1 kg spool. If purchasing two 1 kg spools, the up-front filament purchase would be **₩48,400**, leaving about **209 g** for future prints. The total above is a production-cost estimate, not the cash purchase amount. Exact electricity cost requires the meter's contract type and monthly usage; if the additional 5.11 kWh crosses 200 or 400 kWh, the account's base charge can also increase.

## Sources and method

- Supplied presentation, slides 129–135: panel quantities.
- Supplied `PRINT_SETTINGS.md`: P1S, PLA proxy material, layer/infill/wall/support settings.
- Supplied STL models; sliced with the installed Bambu Studio CLI. Bambu's [command-line documentation](https://github.com/bambulab/BambuStudio/wiki/Command-Line-Usage) describes this workflow.
- Supplied `logo_with_lcd_pentagon.gcode.3mf`, metadata object `part-hexagon-logo-lcd-v2.stl`: 87.18 g, 3 h 8 min. The STL's SHA-256 matches the user-specified folder's logo/LCD STL.
- P1S electricity assumption: 105 W during PLA printing. This is a planning input, not a measurement of this print run; replace it with a plug-in meter reading when available.
- [Korean government residential tariff table](https://www.easylaw.go.kr/CSP/CnpClsMain.laf?ccfNo=2&cciNo=1&cnpClsNo=1&csmSeq=1008), current to September 2026.
- [KEPCO Q4 2026 fuel-adjustment notice](https://www.kepco.co.kr/home/media/newsroom/notice/boardView.do?boardMngNo=14&boardNo=2759): +₩5/kWh.
- [Korea Energy Economics Institute](https://kesis.keei.re.kr/pdfOpen.es?bid=0018&list_no=2519&seq=1): ₩9/kWh climate/environment charge maintained in 2026.
