# Batch input drop folders

Cowork (or anyone) drops a list of emails into `queued/`. The scheduled
runner (`scripts/run-queued-batches.mjs`, fired daily at 5pm ET) processes
each file in oldest-first order:

1. Validates the file is a `.txt` (one email per line) or `.json` (array of
   strings).
2. Skips lines that aren't a valid `local@domain.tld` shape, with a count
   logged to `logs/cron.log`.
3. Runs `scripts/batch-submit.mjs` on the cleaned list. That does, in order:
   - Detects the lead-capture form on each customer's website
   - Submits a probe email through the form
   - Captures the welcome email when one arrives (Inbox Check button)
   - Runs role inference (LinkedIn profile / Google snippet / Brave / website bio)
   - Streams results to the Google Sheet
   - Persists results to `batches/lead-form-submission/<runId>.{tsv,json}`
   - Registers the run in `batches/index.json` so the recap page picks it up
4. On success, the input file is moved into `processed/`. On failure, into
   `failed/` so it can be retried.

## File formats accepted

`.txt` — one email per line, blank lines and `#`-comments ignored:

```
# 2026-05-09 daily list
info@cambiatuseuros.com
matt@mngeek.com
```

`.json` — array of strings:

```json
[
  "info@cambiatuseuros.com",
  "matt@mngeek.com"
]
```

The filename becomes part of the run id, so name them descriptively
(e.g. `2026-05-09_daily.txt`).

## Layout

```
batches/inputs/
  queued/      ← drop new files here
  processed/   ← runner moves successfully-processed files here
  failed/      ← runner moves files that errored out
```
