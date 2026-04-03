# Altagether Roadmap Studio (Airtable CSV Companion)

This is a lightweight, phone-friendly single-page tool for doing a consultative roadmap pass on top of your Airtable export.

## What it does
- Loads your exported CSV (`Table 1-Everything.csv`) or any Airtable CSV with similar columns.
- Walks you through a 5-step "game mode" planning flow.
- Supports rapid triage per item: **Keep**, **Revise**, or **Delete**.
- Lets you add new ideas from built-in templates plus custom entries.
- Produces export files you can re-import into Airtable:
  - `roadmap_delta.csv` (contains `Action` column with `Add`, `Revise`, `Delete`, `Keep`)
  - `roadmap_full_recommended.csv` (filtered working backlog with added ideas)

## How to run
From repository root:

```bash
python -m http.server 8000
```

Open:

- `http://localhost:8000/roadmap_consultant.html`

## Airtable re-import suggestion (safe)
Because CSV exports usually do not contain Airtable record IDs, use this pattern:
1. Import `roadmap_delta.csv` into a **new staging table**.
2. Review rows by `Action` (`Delete`, `Revise`, `Add`, `Keep`).
3. Apply merges/edits into your source table after validation.

This avoids accidental overwrite/deletion of your source-of-truth table.
