# Install: Add "Plans / BOQ" to Microsoft 365 Copilot

A custom **declarative agent** for **Microsoft 365 Copilot (work)**. Upload a
building plan (PDF preferred) and get a full SA-standards **Bill of Quantities** in
a real **.xlsx** workbook. Runs on any machine (the agent runs in the cloud, not
on your PC; you open the workbook in Excel on Windows).

---

## Prerequisites

1. **Microsoft 365 tenant** — free **Developer Program** tenant or Copilot
   Studio trial is enough to build/test.
2. **Microsoft 365 Copilot license** — needed for the agent to appear in work
   Copilot Chat (`m365.cloud.microsoft`) and to create files with the FileIo
   capability. It will **not** run in consumer `copilot.microsoft.com`.
3. **Custom app upload enabled** — dev tenants default on; business tenants need
   a M365 admin: admin center → Org settings → Services → Microsoft 365 →
   **Custom app upload enabled** + **Copilot access enabled**.
4. **Excel output**: the FileIo capability writes the workbook to your OneDrive
   (.xlsx opens in desktop Excel on Windows). If your tenant blocks FileIo, the
   agent falls back to CSV (opens directly in Excel).

---

## Route A — Copilot Studio (no code, recommended)

1. <https://copilotstudio.microsoft.com> → open your environment.
2. **Agents** → **Create blank agent** → name it `Plans / BOQ`.
3. Paste everything from **[instructions.md](instructions.md)** into the
   **Instructions** field.
4. **Knowledge** (recommended): upload the two grounding files —
   `knowledge/sa-estimation-norms.txt` and `knowledge/boq-template.xlsx` — so it
   always calculates from the researched SA norms, and optionally your company
   unit-rate sheet / a SharePoint folder of standard plans.
5. **Test**: upload a sample plan PDF and ask *"Give me the full material BOQ in
   Excel."* Confirm it returns the 5-sheet workbook.
6. **Publish** → **Channels** → enable **Microsoft 365 Copilot** (optionally
   Teams).
7. In work Copilot Chat pick the **Plans / BOQ** agent from the agent picker.

---

## Route B — Package upload (ZIP in this repo)

`plans-boq-copilot.zip` is a side-loadable declarative-agent package
(manifest + icons + embedded norms/template knowledge).

1. **Copilot Studio → Agents → Add → Upload app** and pick
   `plans-boq-copilot.zip`.
2. Or open it with VS Code + **Microsoft 365 Agents Toolkit**, press **F5** to
   debug, and side-load via Teams/M365 admin center → Apps → **Upload custom
   app**.
3. Admin approves in **admin center → Agents → Requests**.
4. Open from the agent picker in work Copilot Chat.

---

## Usage (Windows + Excel)

1. Open Copilot Chat (`m365.cloud.microsoft` or M365 app) → select **Plans / BOQ**.
2. **Add your plan file** (drag into the chat; PDF/text-based is most accurate.
   Scanned image plans work but every unreadable dimension becomes a question —
   answer them for exact quantities).
3. Say: `Give me the full material BOQ in Excel.` (or brick count / check my
   take-off).
4. The agent creates `BOQ-<Project>.xlsx` in your OneDrive — open it in Excel.
   Sheets: **Summary | BOQ | Take-off | Assumptions & Verify | Norms**. The
   Take-off sheet shows every formula; Assumptions sheet lists what to verify.

### Tips for exact quantities
- Use **text/vector PDFs** (printed from CAD/Revit) — dimensions read exactly.
- DWG/DXF: export the sheets to PDF first (agent cannot read CAD files).
- Confirm defaults once when asked: brick type, slab thickness, concrete grades,
  roof profile. These become "assumed" rows you can change.

---

## If the agent won't show up

- Both you and the publishing user need **Microsoft 365 Copilot licenses**.
- Admin approval: **admin center → Agents → Requests**.
- FileIo disabled? Use the CSV fallback (still Excel-compatible).
- After any fix, **re-publish** the agent in Copilot Studio.

---

## Files

| File | Purpose |
|------|---------|
| `instructions.md` | The agent brain. Paste into Copilot Studio (Route A). |
| `norms/sa-estimation-norms.md` | The researched SA factor tables with sources (human-readable). |
| `knowledge/sa-estimation-norms.txt` | Same factors as embedded knowledge (grounding). |
| `knowledge/boq-template.xlsx` + `.csv` | Excel workbook layout the agent fills. |
| `manifest/manifest.json` | Declarative agent manifest (FileIo + EmbeddedKnowledge). |
| `plans-boq-copilot.zip` | Packaged app for Route B / Agents Toolkit. |
| `REBUILD.md` | How to regenerate the package. |

## Honesty note

Quantities are exact **given the dimensions the plan shows** and the
South African norms wheelset embedded here. Anything not readable or not on the
plan is listed as **to verify** — the agent never invents measurements. Treat
output as budget-level take-off, to be confirmed by a QS before ordering.