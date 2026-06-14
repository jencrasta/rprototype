# Batch results

Persistent home for every batch job we run. Each subdirectory holds one
**kind** of batch; each run inside it has a stable filename so results are
never overwritten or lost in `/tmp`.

## Layout

```
batches/
  index.json                       ← machine-readable list of all runs
  role-inference/
    YYYY-MM-DD_<short-name>.tsv    ← one row per email
    YYYY-MM-DD_<short-name>.json   ← run manifest (config + summary)
  lead-form-submission/
    YYYY-MM-DD_<short-name>.tsv    ← one row per site (puppeteer batch)
    YYYY-MM-DD_<short-name>.json
  inbox-check/
    YYYY-MM-DD_<short-name>.tsv
    YYYY-MM-DD_<short-name>.json
```

## Run manifest (`*.json`) shape

```json
{
  "id":          "2026-05-08_role-inference-432",
  "kind":        "role-inference",
  "name":        "432-email mixed batch",
  "startedAt":   "2026-05-02T00:39:00Z",
  "finishedAt":  "2026-05-02T03:06:00Z",
  "durationMin": 147.7,
  "inputCount":  432,
  "resolved":    45,
  "tsvRelativePath": "role-inference/2026-05-08_role-inference-432.tsv",
  "columns":     ["email", "title", "category", "source", "..."],
  "notes":       "Batch run by ad-hoc list."
}
```

## How runs get persisted

The orchestrator scripts (e.g. `scripts/role-batch-stream.mjs`,
`scripts/batch-submit.mjs`, `scripts/nightly-batch.mjs`) write directly into
the appropriate subdir and append an entry to `index.json`. This file is
committed so the recap page (`/batch-recap` in the Vite app) can read it as
a static asset.

## What the recap page reads

The page (`src/BatchRecap.tsx`) imports `batches/index.json` at build time
and lazy-loads each batch's `.tsv` on demand. No external API.
