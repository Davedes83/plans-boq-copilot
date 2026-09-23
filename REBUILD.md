# Rebuilding the package

`plans-boq-copilot.zip` is built by hand so you can regenerate after editing
`instructions.md` or the norms.

```bash
cd ~/plans-boq-copilot

# 1. Edit instructions.md or norms/, then refresh the embedded knowlege copies:
cp norms/sa-estimation-norms.md knowledge/sa-estimation-norms.txt

# 2. Refresh inline instructions in the manifest:
python3 - <<'EOF'
import json
p = "manifest/manifest.json"
m = json.load(open(p))
m["declarativeAgents"][0]["instructions"]["content"] = open("instructions.md").read().strip()
json.dump(m, open(p, "w"), indent=2)
print("instructions updated")
EOF

# 3. Rebuild the zip (paths must be relative — no `../`):
rm -f plans-boq-copilot.zip
mkdir -p /tmp/boq-pkg/knowledge
cp manifest/manifest.json manifest/color.png manifest/outline.png /tmp/boq-pkg/
cp knowledge/sa-estimation-norms.txt knowledge/boq-template.xlsx /tmp/boq-pkg/knowledge/
(cd /tmp/boq-pkg && zip -r ~/plans-boq-copilot/plans-boq-copilot.zip .)
rm -rf /tmp/boq-pkg
```

## Regenerate the Excel template

The template is CSV → xlsx via LibreOffice:

```bash
cd knowledge && libreoffice --headless \
  --convert-to xlsx:"Calc MS Excel 2007 XML" --outdir . boq-template.csv
```

## Change the IDs / install via Agents Toolkit

New app + agent GUIDs before first publish:

```bash
uuidgen   # -> manifest["id"]
uuidgen   # -> manifest["declarativeAgents"][0]["id"]
```

For a full Agents Toolkit project (recommended before production), create it in
VS Code, then paste the instructions and drop in the knowledge files — verify the
`FileIo` and `EmbeddedKnowledge` capability names against the current toolkit
schema. See `INSTALL.md` for upload steps.