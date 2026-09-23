# Plans / BOQ — Copilot agent

A Microsoft 365 Copilot **declarative agent** that turns a building plan into a
complete **Bill of Quantities** of materials, in a real **.xlsx** workbook,
measured to **South African standards**.

Upload a plan (PDF preferred) → the agent does the take-off → returns a 5-sheet
Excel workbook: **Summary | BOQ | Take-off | Assumptions & Verify | Norms**.

## What it quantifies (full house BOQ)

- Excavation & founding, concrete per element (SANS 10400 mixes per m³),
  rebar & welded mesh (Y/R bar kg, SA mesh)
- Masonry — bricks (SANS 227) + mortar cement/sand, net of openings
- Lintels, DPC/DPM & waterproofing
- Plaster & finishes, screeds & tiling (Concrete Society SA / CBA rates)
- Roof & timber — IBR/corrugated cover widths, pitch factors, laps, purlins,
  ridge/fascia/gutters/downpipes, insulation
- Doors/windows from the schedule; "by schedule" items for plumbing/electrical

## Why the numbers are trustworthy

- All rates come from the **embedded SA norms reference**
  (`norms/sa-estimation-norms.md` / `knowledge/sa-estimation-norms.txt`)
  sourced to SANS 227, SANS 10400, Clay Brick Association, Concrete Society SA,
  AfriSam, and SA steel suppliers — never from the model's memory.
- Every formula is printed in the Take-off sheet (auditable in Excel).
- The agent **never invents** dimensions: unreadable or missing values become
  "to verify" questions.
- Wastage defaults (bricks/concrete/tiles 10%, rebar 7%, sheeting 10%) are
  shown per row and changeable in chat.

## Quick start

1. Read `INSTALL.md` for prerequisites (M365 tenant + Copilot license).
2. Route A (no code): Copilot Studio → create agent → paste `instructions.md`,
   add the two knowledge files → Publish.
3. Route B: upload `plans-boq-copilot.zip`.

> Runs in **Microsoft 365 Copilot** (work), not consumer `copilot.microsoft.com`.
> Output is budget-level take-off; confirm with a QS before ordering.

## Rebuilding

See `REBUILD.md`.