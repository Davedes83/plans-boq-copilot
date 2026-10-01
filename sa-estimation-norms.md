# SA Estimation Norms — Bill of Quantities (Materials) Reference

**Version** 2.0 · **As at** 2026-10-01 · **Currency** ZAR · **Owner** AI Agent - Plans_BOQ

> **Single source of truth.** No other copy of this file is maintained. The former
> `sa-estimation-norms.txt` has been removed; do not recreate it.

**Purpose.** The complete set of factors, rates and rules the Plans/BOQ agent is allowed to use
for **material** quantities on a South African residential building. Anything not derivable
here is an assumption, and must be reported as one.

**Basis of measurement.** Metric (mm / m / m² / m³ / No). Net measure. Dimensions rounded per
SANS 1200-A to the nearest 10 mm. Wastage added once, at the stated percentage.

**Scope limit — materials only.** This document yields *material take-offs*. Labour, plant,
contractor's margin, VAT and provisional sums are **out of scope** (§22). Output from this
agent is therefore **not** a priced BOQ.

---

## 0. Basis, sources and global tables

### 0.1 Source register

| Standard | Title / part | Edition | Governs |
|---|---|---|---|
| SANS 590 | Burnt clay facing bricks | edition to confirm | §1 brick unit, dimensional tolerance |
| SANS 1584 / 1594 | Concrete masonry units | edition to confirm | §1 blocks |
| SANS 670 | Mortar for masonry | edition to confirm | §1 mortar mixes |
| SANS 10160-1 / -3 | Structural use of concrete: spans / foundations | edition to confirm | §2 mix selection |
| SANS 10400-A | Structural design: loads | edition to confirm | §2, §9 |
| SANS 10400-B | Structural design: masonry | edition to confirm | §1 |
| SANS 10400-C | Structural design: structural steel | edition to confirm | §3, §20 |
| SANS 10400-D | Structural design: concrete | edition to confirm | §2, §3 |
| SANS 10400-E | Foundations | edition to confirm | §9 |
| SANS 10400-H | Roofs | edition to confirm | §4, §15 |
| SANS 10400-J | Floors, walls, ceilings | edition to confirm | §5, §6, §18 |
| SANS 10400-N | Screeding, tiling, paving | edition to confirm | §6, §7, §21 |
| SANS 10400-P | Painting | edition to confirm | §11 |
| SANS 10400-FA…FH | Services (water, drainage, electrical) | edition to confirm | §16, §17 |
| SANS 10400-X / -XA | Thermal energy efficiency | edition to confirm | §19 |
| SANS 1200-A | Measuring: general | June 2008 | measurement rules, rounding |
| SANS 1200-C | Measuring: formwork | June 2008 | §14 |
| SANS 1200-D | Measuring: masonry | June 2008 | §1 |
| SANS 1200-E | Measuring: plastering | June 2008 | §5 |
| SANS 1200-F | Measuring: floors | June 2008 | §6, §7 |
| SANS 1200-H | Measuring: roofing | June 2008 | §4, §15 |
| SANS 1200-J | Measuring: joinery | June 2008 | §10, §20 |
| SANS 1200-P | Measuring: plumbing | June 2008 | §16 |
| SANS 1200-Q | Measuring: drainage | June 2008 | §16 |
| SANS 121 | Floor screeds | edition to confirm | §6 |
| SANS 1544 | Installation of ceramic tiles | edition to confirm | §7 |

> **Citation gate.** A rate with no confirmed edition above is tagged `assumed` and must appear
> in the Verify block. Non-SANS references (Concrete Society of SA, AfriSam, Clay Brick
> Association, PPC, Macsteel, IBR, RMCS) are supplier/industry data and are labelled as such.

### 0.2 Global lookup tables

**Roof pitch factor** = 1 / cos(pitch). Slope area = plan area × factor.

| Pitch | 5° | 10° | 15° | 20° | 25° | 30° | 35° | 40° |
|---|---|---|---|---|---|---|---|---|
| Factor | 1.004 | 1.015 | 1.035 | 1.064 | 1.103 | 1.155 | 1.221 | 1.305 |

Use the **lowest pitch** present on each roof plane.

**Wastage defaults**

| Material | Default | Range | Higher when |
|---|---|---|---|
| Concrete | 10 % | 5–15 % | pumped, confined access, >20 m³/day |
| Brickwork | 10 % | 5–15 % | complex elevation, curved work, heavy cutting |
| Blockwork | 10 % | 5–12 % | — |
| Mortar / plaster / screed | 10 % | 5–15 % | hand-mixed on site |
| Reinforcing (cut & bend on site) | **7 %** | 5–10 % | intricate shapes, no bar schedule supplied |
| Mesh | 10 % | 8–12 % | laps tied rather than lapped |
| Sheeting / roofing | 10 % | 5–15 % | complex roof, many cuts |
| Timber (framing, formwork) | 10 % | 5–15 % | treated spans, trussed roof |
| Tiles | 10 % | 10–15 % | diagonal or pattern laying |
| Sand blinding / topping | 10 % | 5–10 % | — |

**Rounding.** Counts (bricks, blocks, bags, sheets, bars, tiles, No.) **up** to whole units.
Volumes and areas to **2 decimals**. Round **once**, at the end — never round an intermediate.

**Minimum order quantities.** Cement and stone by whole tonnes (20 bags); sand by ½ m³; mesh by
whole sheets; reinforcing by whole 6 m / 12 m bars; tiles by whole boxes.

**Bulking rule.** Mix ratios (1:4, 1:6) are by **loose-bagged volume**. Cement is *already* a
loose volume — **never apply a bulking factor to cement**. Sand is measured damp-bulked. The
1.33 wet→dry factor is applied **once**, to the whole mortar volume, and never again.

### 0.3 Conversions

| Conversion | Value |
|---|---|
| 1 × 50 kg cement bag | 50 kg = 0.033 m³ loose |
| 1 m³ cement, loose | ≈ 29 bags = 1 440 kg |
| 1 tonne cement | 20 bags |
| 1 wheelbarrow | ≈ 0.06 m³ ≈ 2 bags of cement |
| 1 m³ | 1 000 litres |
| Plasterboard sheet 1200 × 2400 | 2.88 m² |
| Welded mesh sheet 6 × 2.4 m | 14.4 m² |
| Mortar wet → dry | × 1.33 |
| Reinforcing bar mass | d² / 162 kg/m |
| Brick mortar (1000 standard bricks) | 0.45 m³ (§1) |

---

## 1. Bricks & blocks

| Unit | Rate | Notes |
|---|---|---|
| Standard facing brick | 222 × 106 × 73 mm work size | 10 mm joints; coordinating size 232 × 116 × 83 mm |
| Single-skin (110 mm) wall | **52 bricks/m²** | stretcher bond (industry 50–53) |
| Double-skin (220 mm) wall | **104 bricks/m²** | two leaves of 52 |
| Maxi / cement brick 290 × 140 × 90 | ≈ 29 bricks/m² | confirm brick type before use |
| Hollow concrete block 390 × 190 × 140 | ≈ 12.5 blocks/m² | 14 MPa nominal |
| Brickwork wastage | **10 %** | 5 % experienced layer; 15 % complex/curved |
| Mortar mix — general work | **1:6** cement : building sand | standard |
| Mortar mix — load-bearing, below DPC, exposed | **1:4** | richer, less sand |

### 1.1 Mortar volume — derived (supersedes the legacy 0.37 m³ figure)

Bed joint 222 × 116 × 10 mm = 0.000258 m³. Two head joints per stretcher
2 × (73 × 116 × 10) mm = 0.000169 m³. Total **0.00043 m³ per brick**; with frog infill and site
tolerance **adopt 0.45 m³ per 1 000 standard bricks**.

> **Superseded.** The previously published 0.37 m³ / 1 000 bricks omits the head joints and
> reads ~35 % low. Any estimate using it under-ordered mortar by roughly one third.

### 1.2 Cement & sand per 1 000 standard bricks

Dry mortar = 0.45 × 1.33 = **0.60 m³**. cement = dry ÷ (1 + r); sand = dry × r ÷ (1 + r);
bags = cement m³ ÷ 0.033.

| Mix | Cement | Sand |
|---|---|---|
| 1:6 | 0.60 ÷ 7 = 0.086 m³ = **3 × 50 kg bags** | 0.60 × 6/7 = **0.51 m³** |
| 1:4 | 0.60 ÷ 5 = 0.120 m³ = **4 × 50 kg bags** | 0.60 × 4/5 = **0.48 m³** |

**Cross-check** (Concrete Society SA / AfriSam published): 1:6 → 3 bags + 0.55–0.60 m³ sand;
1:4 → 4 bags + 0.50–0.55 m³ sand. Agrees within mixing tolerance — **use this table.**
The previously published "4–5 bags" for 1:4 is **superseded**: 5 bags double-counts board and
sieve loss, which is already carried by the 10 % wastage.

**Worked example — 100 m² single-skin wall:** 5 200 bricks; mortar 5 200 ÷ 1 000 × 0.45 =
2.34 m³ wet, 3.11 m³ dry; cement 3.11 ÷ 7 = 0.44 m³ = 13.5 bags → **14 bags**;
sand 3.11 × 6/7 = **2.67 m³**. With +10 % wastage: 5 720 bricks, mortar 2.57 m³,
15 bags, **2.93 m³** sand.

### 1.3 Deduction rule — differs from plaster

Brickwork is measured **net of all openings, deducted in full, with no minimum threshold**.
Deduct doors, windows, cills, steps and service penetrations; openings below 0.1 m² need not be
deducted. *(§5 uses a different, threshold-based rule — do not mix the two.)*

Provide **one extra lintel course** (112 mm) over every precast lintel or steel angle lintel.
Measure cills, steps and copings in lin. m of the unit.

---

## 2. Concrete mixes (SANS 10400) — quantities per 1 m³ compacted

Mix assumes damp-bulked sand + 50 kg OPC bags.

| Strength | Use | Cement (50 kg) | Sand (m³) | Stone (13/19 mm, m³) |
|---|---|---|---|---|
| 10 MPa (lean/blinding) | blinding, baling | 4 bags | 0.80 | 0.80 |
| **15 MPa** | unreinforced footings, boundary/retaining walls | **5.5 bags** | **0.75** | **0.75** |
| **25 MPa** | reinforced foundations, house slabs, driveways, garages | **7 bags** | **0.70** | **0.70** |
| **30 MPa** | beams, suspended/precast floors, heavy duty | **10 bags** | **0.65** | **0.65** |

- Default wastage: **+10 %** (§0.2 table).
- Water: ≈ 25 L per 50 kg bag of cement (medium workability).
- **Cube vs cylinder.** SANS 10160 and SANS 10400-D specify **cube** strengths; a spec reading
  "25 MPa" is a cube characteristic. Where a supplier quotes a cylinder value it is ~25 % lower
  for the same mix. Do not convert between them — use the strength as specified.
- **Mix selection** must follow the strength noted on the drawings. Where none is noted, use
  15 MPa for unreinforced footings and 25 MPa for any reinforced element — and record the
  substitution in the Verify block.
- **Itemize per element** — blinding, strip footings, pad footings, ground slab, suspended slab,
  columns, beams, lintel topping, screed, kerb — do not lump. Each is its own BOQ row.

---

## 3. Reinforcing steel & mesh

SA high-tensile (Y, 450 MPa) and mild (R, 250 MPa). Mass = d²/162 kg/m:

| Bar | kg/m |
|---|---|
| R6 | 0.222 |
| R8 | 0.395 |
| Y10 | 0.617 |
| Y12 | 0.888 |
| Y16 | 1.578 |
| Y20 | 2.466 |
| Y25 | 3.854 |

- Stock lengths: **6 m and 12 m**. Order whole bars: sum cut lengths *including laps and
  wastage*, divide by stock length, round up.
- **Lap splice** ≈ 40 × bar Ø for Y bars (e.g. Y12 → 480 mm), tensioned at nominal yield.
- **Nominal cover to reinforcement** (SANS 10400-D):

| Element | Cover |
|---|---|
| Footing / slab to earth or fill | **50 mm** |
| Internal face (plastered) | **20–25 mm** |
| External / exposed face | **30–40 mm** |

- Typical reinforcement mass per m³ concrete (**sanity check only**): strip/pad footings
  20–40 kg/m³; slabs 60–110 kg/m³; beams/columns 80–150 kg/m³.
- Domestic single-layer slab: **6–10 kg per m² of slab**.
- **Welded mesh (SA designations):** A142 (6 mm @ 200), A193 (7 mm @ 200), A252 (8 mm @ 200),
  A393 (10 mm @ 200). Sheet 6 × 2.4 m = 14.4 m². Sheets = net area × 1.1 ÷ 14.4, round up.
- **Cover spacers / chairs:** ≈ 1 per m² of slab, 1 per 2 m of footing run — measure in No.
- **Membrane under a slab-on-ground:** see §8 — do not double-count with mesh cover.

---

## 4. Roof sheeting (SA profiles)

| Profile | Effective cover | Notes |
|---|---|---|
| **IBR** (inverted box rib) | **686 mm** | industry standard; 0.3–0.8 mm gauge |
| Corrugated 10.5/76 | 762 mm | 8.5/76 = 610 mm |
| Widespan | 762 mm | |
| Big Six | 1016 mm | industrial |
| Grecca | 1100 mm | |

- End laps: **≥ 150 mm** (pitch > 15°) / **≥ 250 mm** (pitch ≤ 15°); side lap: one full
  corrugation.
- **Slope area = plan area × pitch factor** (exact table, §0.2): 1.004 at 5° up to 1.305 at 40°.
  Use the **lowest pitch** on each plane. The previous banded approximation (1.00 / 1.05 / 1.15)
  is **superseded** — it under-reads by 6 % at 35°.
- Add **+10 %** for laps and offcuts.
- **Fasteners:** 3 per sheet per purlin. Tek 65 mm into steel, Tek 90 mm into timber, each with
  a 25 mm bonded washer. Purlin spacing for IBR on steel spans: 1 200 mm maximum.
- **Insulation** is measured in m² of **plan** area, not slope area (§19).

### 4.1 Measured separately from sheeting (SANS 1200-H)

| Item | Unit | Rule |
|---|---|---|
| Ridge capping | lin. m | ridge length + 10 % laps |
| Hip / valley capping | lin. m | measured along the capping |
| Flashings (wall, chimney, vent) | lin. m | girth developed; parapets = 2 × length |
| Gutters | lin. m | see §17 |
| Downpipes | lin. m | see §17 |
| Fascia / barge boards | lin. m | length + 10 % |
| Insulation | m² | plan area (§19) |
| Sheeting | m² or No. sheets | slope area × 1.10 ÷ effective cover |

**Worked example — 100 m² plan area, IBR at 25°, one plane:** slope area = 100 × 1.103 =
110.3 m²; + 10 % = 121.3 m²; sheets = 121.3 ÷ 0.686 = **177 sheets** (6 m lengths assumed;
confirm the sheet length from the supplier before ordering).

---

## 5. Wall plaster (SA)

**Mixes** (SANS 10400-D, SANS 670): exterior / exposed 1:3–1:4 (All Purpose or masonry cement);
interior 1:4–1:6.

**Thickness:** internal 10–12 mm; external 15–20 mm. Maximum **15 mm per coat** — specify
**2 coats** wherever the total exceeds 15 mm.

### 5.1 Cement & sand — derived (supersedes the legacy 14 bags / 2.25 m³ sand figure)

wet mortar = area × thickness · dry = wet × **1.33** · cement = dry ÷ (1 + r) ·
sand = dry × r ÷ (1 + r) · bags = cement m³ ÷ 0.033.

| Mix | Thickness | Per m² | Per 100 m² |
|---|---|---|---|
| 1:3 | 10 mm | 0.101 bag + 0.010 m³ sand | 11 bags + 1.00 m³ sand |
| 1:3 | 15 mm | 0.151 bag + 0.015 m³ sand | **16 bags (800 kg) + 1.50 m³ sand** |
| 1:4 | 15 mm | 0.121 bag + 0.016 m³ sand | **13 bags + 1.60 m³ sand** |

> Per-100 m² figures are the per-m² rate × 100, rounded **up** to whole bags (§13 rule 4).
> Do not round the per-m² rate and then multiply — that loses up to a bag per 100 m².

> **Superseded.** The previously published “100 m² @ 15 mm = 14 bags + 2.25 m³ sand” mixes
> ratios: 1.65 m³ of dry mortar at 1:3 gives 0.41 m³ cement (12.5 bags) and only 1.24 m³ sand;
> 2.25 m³ of sand would require a mix of about 1:4.5. The sand quantity above is the correct one.

**Cross-check — bagged product.** AfriSam Mix A (2 × 50 kg bags + 4.5 wheelbarrows sand ≈ 0.25 m³
yield) covers 24 m² @ 10 mm, 16 m² @ 15 mm, 12 m² @ 20 mm. This is a **pack-size** check on
batch planning only — do not mix it into the rate derivation.

**Bulking warning.** The 1:r ratio is by **loose-bagged** volume. Cement is already a loose
volume — **never apply a bulking factor to cement**. The 1.33 factor is applied once, to the
whole wet mortar volume, and never again.

- **Wastage: +10 %** (§0.2).
- **Deduct openings > 1 m²** each from the plaster area. *(This threshold rule is specific to
  plaster — brickwork uses the full-deduction rule in §1.3. Do not mix them.)*
- **Wet plaster on the back of new brickwork:** SA practice is to wet the substrate and skip a
  DPC-backed area only where specified — state which areas received a skim coat in the Verify list.
- Measure each face separately; state whether an area is *gross face* or *net face*.

---

## 6. Floor screed (SA)

**Thickness** (SANS 121): bonded min 25–30 mm · unbonded over DPM **50 mm** · floating 65–75 mm.

**Mix:** 1:3–1:4 sharp/coarse building sand. Volume = area × thickness · dry = wet × 1.33 ·
cement = dry ÷ (1 + r) · sand = dry × r ÷ (1 + r) · bags = cement m³ ÷ 0.033.

### 6.1 Site mix — derived (per 1 m³ of compacted screed)

| Mix | Cement | Sand |
|---|---|---|
| 1:3 | 1.33 ÷ 4 = 0.333 m³ = **10 bags** | 1.33 × 3/4 = **1.00 m³** |
| 1:4 | 1.33 ÷ 5 = 0.266 m³ = **8 bags** | 1.33 × 4/5 = **1.06 m³** |

**Cross-check — supplier figure.** The previously published “1:4 → 8 bags + 0.8–1.0 m³ sand”
reconciles with the derivation (8 bags + 1.06 m³ sand), confirming it is a **site-mix** figure
and not a bagged-product figure. Use it; the derivation above is the authority for other ratios.

**Worked example — 40 m² floor, 30 mm bonded 1:4 screed:** wet = 40 × 0.030 = 1.20 m³;
dry = 1.60 m³; cement = 0.32 m³ = **10 bags**; sand = 1.28 m³; + 10 % → **11 bags + 1.41 m³**.

- **Wastage: +10 %** (§0.2). Round bags **up** to whole units; sand to ½ m³ (minimum order).
- Screed **under** a finish (tiles, screed tiles) is measured as its own item; do not absorb it
  into the tiling item.

---

## 7. Tiles (floor/wall)

Pieces/m² = 1 ÷ (L m × W m) — **work size, joints ignored**. Add the joint-aware column when
the joint width is specified on the drawings (SANS 1544: 2 mm ceramic, 3 mm porcelain).

| Tile (mm) | Work size /m² | @ 3 mm joint | Notes |
|---|---|---|---|
| 300 × 300 | 11.11 | 10.91 | |
| 400 × 400 | 6.25 | 6.10 | |
| 450 × 450 | 4.94 | 4.83 | |
| 300 × 600 | 5.56 | 5.46 | |
| 600 × 600 | 2.78 | 2.73 | |
| 800 × 800 | 1.56 | 1.53 | |
| 600 × 1200 | 1.39 | 1.37 | large format; 3–4 kg/m² adhesive |

- Cut wastage: **+10 %** straight-bond; **+15 %** diagonal or pattern laying.
- Bagged adhesive ≈ **4 kg/m²** for floor tile at 10–12 mm bed; **3 kg/m²** for wall tile at 6–8 mm.
  Large format or 20 mm bed: **6 kg/m²**.
- Grout ≈ **0.8 kg/m²** default; 2–3 kg/m² for 20 mm grout joints or heavy duty.
- **Skirtings / tile trims / movement joints:** measure in lin. m; movement joints every ≈ 8 m in
  large areas — add as a separate No. item.
- **Deduct** openings > 1 m², consistent with §5.

---

## 8. DPC / DPM / waterproofing

| Item | Unit | Rule | Grade / product |
|---|---|---|---|
| DPM under slab | m² | slab area + 10 % laps, on a 50 mm sand blinding | 0.15–0.25 mm LDPE, or 3 mm bitumenous |
| DPC strip | m² or lin. m | 300 mm wide, full wall length, at ≈ 150 mm above finished ground | 0.15 mm LDPE / 110 mm bitumenous |
| DPC to openings | lin. m | jambs and head of every opening | pre-formed DPC tray or strip |
| Cavity tray | No. | 1 per opening | pressed tray, 225 mm cavity |
| Damp-proof course to slab edges | lin. m | 100 mm upstand, full perimeter | 0.25 mm LDPE |
| Waterproofing (tanking) | m² | walls below natural ground level, 0.5 % fall to drainage | 3–4 mm self-adhered / PU system |

- **Sand blinding under a DPM** (50 mm, compacted) is a **separate** BOQ item — do not absorb it
  into the DPM item (§9 covers filling under the slab).
- **Vertical DPC must continue under and behind** wall sills per SANS 10400-E; state the height
  assumed in the Verify block.
- Below-DPC brickwork uses a richer 1:4 mortar mix (§1) — note this when ordering mortar.
- Any waterproofing whose extent depends on soil class or water table not shown on the drawings
  is an **assumption** — flag it, do not guess.

---

## 9. Excavation & founding (SANS 1200-A, SANS 10400-E)

| Item | Unit | Rule |
|---|---|---|
| Strip footing excavation | m³ | continuous length × width × depth |
| Strip footing width | mm | ≈ 2 × wall width; typically 450–600 mm |
| Depth to founding | mm | typically 600–1 000 mm; **never assumed** — take from the foundation notes or a stated assumption |
| Pad footing excavation | m³ | each pad L × B × D, summed |
| Bulk / platform excavation | m³ | plan area × depth, less strip/pad volumes already taken |
| Backfill & compact | m³ | excavated volume − built concrete volume |
| Filling under slab (sand or stone) | m³ | plan area × 100–150 mm, compacted in layers |
| Carting away | m³ | only where surplus spoil is noted on the drawings |

- **State your deduction convention once and apply it everywhere.** Default: excavate to the
  formation level shown; backfill = excavation less footing concrete. Where the drawings show a
  battered or stepped excavation, measure the actual profile.
- **Measure as separate BOQ items** — excavate / dispose of surplus / backfill and compact —
  each with its own unit. Do not net them into a single figure.
- **Unbalanced sites** (fill required, no excavation shown) are an assumption — flag it.
- Depth of founding is driven by bearing capacity. Where no foundation note exists, the depth is
  a **question for the engineer**, not an estimate. Put it in the Verify block.

---

## 10. Doors / windows / lintels

- **Count from the plan's window and door schedules**, one BOQ row per schedule line, with the
  size and type carried through from the schedule. Never take a quantity off the plan geometry.
- **Precast concrete lintels** (standard SA stock lengths): 900 / 1200 / 1500 / 1800 / 2100 /
  2400 mm. Required length = **clear opening + 150 mm each side**; order the next stock length up.
- **Steel NST angle lintels** for wide openings — measure in No., by size.
- Standard SA internal door leaf sizes: **762 × 2032**, **813 × 2032**, **915 × 2032** mm.
  External and sliding doors per the schedule.
- **Frames:** measure in lin. m of frame — perimeter of the opening + 2 × 60 mm (lining) per
  reveal, or in No. per schedule line. State which.
- **Lintels are not counted as brickwork** — the lintel course is brickwork (§1.3) and the lintel
  itself is a separate item. Do not double-count.
- **Arches / pre-cast surrounds / sills:** per the schedule; note if not scheduled.

---

## 11. Painting (schedule / finish note driven)

Finish-driven: include **only** where the plan or a finish schedule calls for it.

| Item | Coverage | Notes |
|---|---|---|
| Interior emulsion | ≈ 1 L per 8 m² per coat | 2 coats unless specified otherwise |
| Exterior masonry | ≈ 1 L per 5 m² per coat | masonry, 2 coats |
| Ceiling paint | ≈ 1 L per 8 m² per coat | on skimmed or board ceiling |
| Painted trim / frames | lin. m of perimeter | 2 coats, brush |

- **Water-based vs solvent-based** changes coverage by ≈ 20 % — state the type used.
- Undercoat on new plaster: 1 coat primer + 2 finish coats (SANS 10400-P) — state if primed.
- **Measure on the plastered area** (§5), not the structural area.

---

## 12. Plumbing & electrical — schedule-driven

**Not measurable from an architectural plan alone.** Itemize as `by-schedule` with quantities
only where an MEP or drainage sheet is provided. This is the governing rule for all sanitary
ware, fittings, valves, electrical outlets, switches and lighting.

**Carve-out — trenching is measurable.** Below-ground pipework may be *located* on a plan
(servicing layout), so the following **are** measurable even without an MEP sheet: trench
excavation, trench backfill, pipe lengths, fittings, inspection chambers and septic/soak-away
volumes — see §16.

Mark every unquantified MEP item `by-schedule`, never omit it, and never invent a count.

---

## 13. Standard rules the agent must apply

1. **Show the working.** Every row states gross → deduction → net → wastage → order quantity,
   with the formula and the source. A quantity without a visible derivation is not acceptable.
2. **Never fill a missing dimension.** If a dimension is unreadable, absent, or ambiguous at the
   drawing's scale, write `?` and raise a Verify row. Fewer guesses = better.
3. **Deduct openings using the section's own rule.** Brickwork = full deduction, no threshold
   (§1.3). Plaster, tiling, painting, sheeting = openings > 1 m² only (§5, §7, §11).
4. **Round once, at the end.** Counts (bricks, blocks, bags, sheets, bars, tiles, No.) **up** to
   whole units; volumes and areas to 2 decimals. Never round an intermediate value.
5. **Apply wastage once only**, at the stated percentage for that material (§0.2). Never stack
   a material wastage on top of a product wastage.
6. **State the area basis** for every rate: *plan*, *slope*, *gross face*, *net face*, or
   *developed girth*. This is the most common mis-use in the set.
7. **Cite a source and an edition** for every rate (§0.1). A rate with no confirmed citation is
   tagged `assumed` and must appear in the Verify block.
8. **Give every row a status.** No blanks. Allowed values are listed in §23.
9. **Itemize, never lump.** Each measured element is its own row — each footing type, each slab,
   each mix strength, each door size. Lumping is what makes a BOQ untenderable.
10. **Itemize concrete per element**, and itemize mortar separately from masonry (§1.2) and
    screed separately from tiling (§6).
11. **Do not apply a bulking factor to cement** — the mix ratio is already loose-bagged volume
    (§0.2, §5.1). This is the single largest source of over-ordering.
12. **Cap the estimate at the drawing's scale.** On a 1:100 plan, any area below 0.1 m² rounds to
    0.1 m² and is flagged rather than measured.
13. **End every output with three blocks**, in this order: **Verify before ordering** (anything
    assumed, unreadable or unresolved) · **Assumed norms used** (which §-numbers were leaned on,
    and where a default was substituted for a specified value) · **Items excluded from scope**
    (§22).
14. **The Verify block is not optional.** An output with no Verify block is treated as failed.

### 13.1 Self-check — run before returning the take-off

Reconcile these automatically. If two figures disagree by more than the stated tolerance, stop
and report the discrepancy rather than choosing one.

| Check | Rule | Tolerance |
|---|---|---|
| Bricks → mortar → cement | bricks ÷ 1000 × 0.45 = wet mortar; §1.2 gives cement | ±5 % |
| Plaster cement vs. bag count | derived bags (§5.1) vs. whole bags ordered | ±2 bags per 100 m² |
| Concrete ↔ formwork ↔ rebar | formwork m² and rebar kg within §2, §3, §14 bands for the element type | ±20 % |
| Sheeting ↔ purlin length | purlin lin. m ≈ 0.83 per m² of slope area at 1.2 m c/c (§15) | ±10 % |
| Sheeting ↔ plan area | slope area ÷ plan area must equal the pitch factor (§0.2) | ±2 % |
| Gutter ↔ downpipe ↔ roof area | downpipe lin. m ≈ roof plan area ÷ 50 (§17) | ±15 % |
| Mesh ↔ area | sheets × 14.4 m² ÷ 1.1 must cover the slab area | ±5 % |
| Cement total ↔ bags ↔ tonnes | total bags × 50 kg, rounded up to the order increment | exact |
| Volume chain | footing volume = excavation less backfill ± formwork voids | ±3 % |

### 13.2 Common errors to avoid

- Applying the mortar figure to **brickwork + plaster** in one step — plaster is a separate item (§5).
- Using **slope** area where **plan** area is required (insulation §19, purlin runs §15) or the reverse.
- Adding **+10 % wastage to a `by-schedule` or `by-client-spec` item** — those quantities are given.
- Rounding cement to whole tonnes **before** adding wastage.
- Reading a **cube** strength as a cylinder strength (§2).
- Deducting openings twice — once in the gross wall and again in the plaster.
- Measuring a **lintel course in both** brickwork and the lintel item (§10).
- Reporting a total without a status, or without the Verify block.

---

## 14. Formwork / shuttering (SANS 1200-C)

Measured in **m² of contact area** — the area of concrete touching formwork. Itemize per
element type; do not lump.

| Element | Contact area | Formula |
|---|---|---|
| Strip footing, both sides | m² | trench width × depth (× 2 faces) |
| Strip footing, top | m² | trench width × length — only if not fully blinded |
| Pad footing sides | m² | perimeter × depth |
| Ground slab edge | m² | slab perimeter × slab depth |
| Beam soffit + 2 sides | m² | **2 × L × (h + b)** |
| Column faces | m² | perimeter × height |
| Stairs | m² | soffit + 2 × raking face |

**Worked example — beam 5.0 m long, 300 wide × 450 deep:** 2 × 5.0 × (0.45 + 0.30) =
**7.50 m²**. A 300 × 300 column 2.7 m high: 4 × 0.30 × 2.7 = **3.24 m²**.

- **Wastage / consumables: +10 %** for timber, props, walers, wedges, formoil and tie wire.
- **Sanity band:** formwork timber **0.05–0.08 m³ per m³ of concrete** (0.06 typical). For a
  domestic house this band, not a rate, is often the fastest check on a take-off.
- **Props / falsework** for suspended slabs: count per bay from the structural drawing — not
  derivable from an architectural plan. Flag as an assumption.
- **Permanent formwork** (e.g. a slab edge used as an upstand) is still measured as formwork;
  note it in the description.
- Do **not** deduct openings from formwork areas.

## 15. Roof carpentry / structure (SANS 10400-H, SANS 1200-H)

Members are selected structurally — size and spacing come from the drawings or the engineer.
Where absent, the values below are **assumptions** and must be flagged.

| Member | Typical SA section | Spacing | Unit |
|---|---|---|---|
| Rafters | 38 × 114 or 38 × 165 timber | 600 mm c/c | lin. m |
| Purlins | 76 × 76 or 100 × 50 timber, or light steel | 1 200 mm max | lin. m |
| Ridge board | 38 × 200 | continuous | lin. m |
| Hip / valley boards | 38 × 200 | continuous | lin. m |
| Fascia / barge boards | 25 × 150 or 38 × 200 | — | lin. m |
| Ceiling joists | 38 × 114 | 600 mm c/c | lin. m |
| Trusses | per truss schedule | per plan | **No.** |

**Rules.**
- Rafter lin. m = slope length × number, where number = span ÷ spacing + 1. Measure the rafter
  **slope length**, not the plan run.
- Purlin lin. m ≈ **0.83 per m² of slope area** at 1 200 mm c/c (1 run per 1.2 m across the slope).
  Cross-check against the sheeting area (§13.1).
- Members are bought in **stock lengths** — round total lin. m up to the next 3.6 / 5.4 / 6.0 m
  length and add the offcut wastage.
- **Treated timber** for all roof and ceiling members within reach of the roof sheet; state the
  treatment grade (e.g. LOSP/CCA) as an assumption if not specified.
- **Trusses:** count from the plan, never from roof area. Give each truss design a separate row
  and reference the truss schedule. Trusses at 600 mm c/c → No. = span ÷ 0.6 + 1.
- Timber wastage **+10 %** (§0.2).
- **Bracing, straps, anchor bolts, hurricane straps:** in No. or kg — state the basis; these are
  usually `by-schedule` from the structural drawings.

## 16. Below-ground services — trenching & drainage (SANS 1200-P, SANS 1200-Q)

The measurable carve-out from §12.

| Item | Unit | Rule |
|---|---|---|
| Water pipe trench | m³ | length × (**pipe dia. + 300 mm**) × depth |
| Soil / waste trench | m³ | length × (**pipe dia. + 300 mm**) × depth |
| Trench depth | mm | invert to invert + **150 mm cover** |
| Pipe length | m | centreline run, + 5 % for fittings and joints |
| Rodding eye | No. | 1 per stack; 1 per 15 m on a run |
| Inspection chamber | No. | per the drainage plan; **never** assumed |
| Septic tank | m³ | × **1:25** as a minimum working capacity ratio (SANS 10400-FA) |
| Soak-away / french drain | m³ | per the drainage plan or the stated percolation rate |

**Standard SA pipe sizes:** soil **110 mm** · waste **50 mm** · sink/kitchen **40 mm** · bath
**40 mm** · water supply CPVC **25 / 32 mm**.

- **Separate BOQ items** for excavate / pipe / backfill / bed, each with its own unit.
- **Bedding** 75 mm compacted sand (or 100 mm) under all pipes — a separate m³ item.
- Trench depth depends on the service position shown. Where it is not shown, **do not assume** —
  raise a Verify row.
- Inspection chambers and septic volumes come from the **drainage plan**; without one, these
  rows are `by-schedule`, not zero.

## 17. Rainwater goods (SANS 10400-H, SANS 1200-H)

| Item | Unit | Rule | SA stock |
|---|---|---|---|
| Gutter | lin. m | plan eave length + 10 % for corners and joints | 100 mm half-round or 100 × 100 square PVC |
| Downpipe | lin. m | **roof plan area ÷ 50** | 50 mm round (75 × 75 square alt.) |
| Gutter brackets / straps | No. | gutter lin. m ÷ 0.9 | galvanised or PVC |
| Downpipe brackets | No. | downpipe lin. m ÷ 1.8 | PVC, single clip |
| Hopper head | No. | 1 per downpipe | 100 × 100 moulded |
| Shoe / bend at bottom | No. | 1 per downpipe | — |
| Splash block | No. | 1 per downpipe | concrete / rubber |

- One downpipe per ≈ **50 m²** of roof plan area as the default; where the plan shows fewer,
  **follow the plan** and record the divergence in the Verify block.
- Downpipe lin. m is a **vertical drop** — measure from gutter outlet to splash block, not the
  roof slope.
- Gutters are measured **separately from** the roof sheeting (§4.1); never fold them into it.
- Fixings, sealants and screws: `assumed` unless specified.

## 18. Ceilings & drywall (SANS 10400-J, SANS 1200-J)

| Item | Unit | Rule |
|---|---|---|
| Plasterboard 12.5 mm | sheets | plan area ÷ 2.88, **+10 %** for cuts, round up |
| Brand-name board equivalents | sheets | same area basis; state the product (e.g. 12.5 mm × 1.2 m wide) |
| Battens 63 mm | lin. m | ≈ **2.2 lin. m per m²** at 450 mm c/c |
| Brand-name framing | lin. m | ≈ 2.8 lin. m per m² at 600 mm c/c, 25 mm wide |
| Suspended ceiling tees | lin. m | grid spacing per system, ≈ 2.7 lin. m/m² at 600 mm |
| Cornices | lin. m | wall perimeter + 1 per internal corner |
| Cornice fillers / brackets | No. | 2 per lin. m |
| Isulating board over ceiling | m² | plan area, plan basis, at the stated grade (§19) |

- Board is measured on **plan** area, at the **ceiling level** — not on the room floor area plus
  a wall multiplier. No wastage is added for a rectangular room with 4 cuts; **+10 %** applies to
  a cut-heavy layout.
- Ceiling area = room plan area. Wall-to-ceiling junction plaster is a *separate* item (§5).
- Board orientation and sheet jointing to be in long sheets where possible — note any restricted
  sheet sizes as an assumption.

## 19. Insulation & DPC products (SANS 10400-X / -XA)

| Item | Unit | Rule |
|---|---|---|
| Roof insulation | m² | **plan** area of the roof, at the stated thickness grade |
| Wall insulation | m² | **gross face** area, before openings |
| Floor / ceiling insulation | m² | plan area |
| DPM, DPC | see §8 | see §8 |
| Waterproofing | see §8 | see §8 |

**SA product grades (state the grade — it changes the quantity):**

| Material | Grades / thicknesses |
|---|---|
| Polyester wool | 30 / 50 / 75 mm |
| Polypropylene (white Waffle) | 40 / 50 mm |
| Expanded polystyrene | 20 / 25 / 30 / 40 / 50 mm |
| Polyiso board | 30 / 40 / 50 mm |
| Aluminium foil bubble | 4 / 8 / 12 mm |
| XPS | 30 / 40 / 50 / 65 mm |

- **Required thickness is a compliance calculation, not a take-off figure.** SANS 10400-XA sets a
  minimum R-value per climate zone; where the drawings do not state the insulation, the quantity
  is **`by-client-spec`**, not `assumed`.
- Insulation is ordered in **packs or rolls** — state the pack size and round up to it. Supply
  the **R-value** alongside the thickness in the description.
- Never measure roof insulation on slope area (§13.2).

## 20. Joinery & ironmongery (SANS 1200-J)

| Item | Unit | Rule |
|---|---|---|
| Door frames | lin. m or No. | opening perimeter + 2 × 60 mm lining per reveal — state which (§10) |
| Window frames | No. | per the window schedule, with sizes |
| Architraves / surrounds | lin. m | 2 × opening height + 1 × opening width, per opening |
| Skirting boards | lin. m | wall perimeter less door openings, at **100 mm** high |
| Cupboard tops | No. | per the joinery drawing / schedule |
| Worktops | m² | plan area, **+10 %** for joints and cut-outs |
| Hardware / ironmongery sets | No. | **1 set per door leaf**, 2–3 per leaf is typical; state the basis |
| Glass | m² | per the window schedule — state single/double and thickness (3 / 4 / 6 mm) |
| Burglar bars / security screens | m² | opening area, per the schedule |
| Paint / seal to frames | lin. m | 2 coats, per §11 |

- **Ironmongery** must state what a "set" comprises (lever set, hinges, latch, strike) — a vague
  `No.` is untenderable.
- **Skirting**: SA standard internal is 100 mm; state the profile and whether it is mitered at
  corners (adds lin. m).
- **Hardware is normally a client-spec item** — `by-client-spec` where a schedule exists, otherwise
  `by-schedule`.

## 21. Siteworks

Normally measured on a **separate siteworks BOQ**; flagged here because the same rate logic
applies. None of it is measurable without a siteworks or landscape plan.

| Item | Unit | Rule |
|---|---|---|
| Paving | m² | plan area + 10 %; **confirm** whether supply or install is the scope |
| Kerbing | lin. m | edge length, per profile |
| Fencing — palisade | lin. m + No. | posts at **1.8 m c/c** → No. = lin. m ÷ 1.8 + 1 |
| Fencing — wire / mesh | m² | plan area of the boundary |
| Walls (boundary / retaining) | m² / m³ | per §1 or §2, whichever the construction is |
| Topsoil | m³ | area × 50–100 mm stripping depth |
| Irrigation | lin. m / No. | per the layout — `by-schedule` |
| Grassing | m² | plan area + 10 % |

- Siteworks is where quantities most often get **guessed**. If no siteworks plan is supplied,
  every row here is `by-schedule` with a zero or a stated assumption — never an invented figure.

## 22. Exclusions from scope

This agent produces a **materials take-off only**. The following are **excluded** and must not be
implied by any output:

1. Labour and setting-out.
2. Plant, scaffolding and access equipment.
3. Contractor's margin, preliminaries and overheads.
4. VAT and any tax.
5. Provisional sums, prime cost items and allowances.
6. Loading, carting away and disposal of surplus spoil or debris.
7. Protection of the works, cleaning and making good.
8. Survey, geotechnical investigation and soil classification.
9. Structural engineering design and shoring design.
10. Building regulations / NHBRC submission fees.
11. Escalation, price fluctuations and currency movements.
12. Any item marked `by-schedule` or `by-client-spec` without a schedule supplied.

State the applicable exclusions in the output header as well as here — the reader of the BOQ
must not mistake a materials take-off for a priced bill.

## 23. Output contract

The workbook layout is `Summary | BOQ | Take-off | Assumptions & Verify | Norms`
(`boq-template.csv`). The norms file is the authority; this section mirrors it so the two
cannot drift. **If this section and `boq-template.csv` disagree, raise it — do not silently pick one.**

**BOQ sheet columns** (one row per measured element, every row filled):

`Item No` · `Description` · `Unit` · `Quantity` · `Wastage %` · `Total Qty` · `Formula/Source` · `Status`

**Take-off sheet columns:**

`Element` · `Length m` · `Width m` · `Height/Depth m` · `Factor` · `Rates (from norms)` ·
`Gross` · `Deductions` · `Net` · `Unit` · `Formula`

**Assumptions & Verify sheet columns:** `Item` · `Assumption/Question` · `Verified/To verify`

**Norms sheet:** the norm row used, including the section number and SANS citation.

**Status vocabulary — use exactly these six values, never blank:**

| Status | Meaning | Must appear in Verify? |
|---|---|---|
| `verified` | Read directly from a dimensioned drawing | No |
| `derived` | Computed from verified inputs by a stated formula | No |
| `assumed` | A norm or default substituted for an absent specification | **Yes** |
| `by-schedule` | Quantity given by a schedule that was not supplied | **Yes** |
| `by-client-spec` | Product or performance specified by the client | **Yes** |
| `excluded` | Deliberately outside this scope (§22) | Optional |

**Rules:** `assumed`, `by-schedule` and `by-client-spec` rows must each appear as a row in the
Assumptions & Verify sheet. A missing Verify entry for one of those statuses is a failed output.

---

## 24. Revision log

| Version | Date | Change |
|---|---|---|
| 1.0 | — | Original reference set |
| 2.0 | 2026-10-01 | Reconciled mortar (§1) and plaster (§5) arithmetic; added source register with editions (§0.1), pitch-factor / wastage / rounding lookup tables (§0.2), conversion table (§0.3); replaced banded pitch factors with exact 1/cos; corrected the 1:4 screed figure to a derived site mix (§6); joint-aware tile table (§7); added §14–§22 (formwork, roof carpentry, below-ground services, rainwater goods, ceilings, insulation, joinery, siteworks, exclusions); added self-checks and common-errors lists (§13.1, §13.2); added the output contract and Status vocabulary (§23); removed the duplicate `.txt` |