# Review Tracker Template

The live file is `.note-information/review-tracker.md` (the AI creates and maintains it).
Date-keyed; under each date, one line per review due that day.

```
# Review Tracker
Last updated: [DATE]

## YYYY-MM-DD
- [Note Title] (Review 1) — uncompleted
- [Note Title] (Review 2) ✓ 84%
- [Note Title] (Review 1) — STALE (2026-06-01)
```

Rules:
- On completion: `✓ [score]%`. Stale: `— STALE (date)`. Skipped: `— skipped (date)`.
- Only Review 1 is added at note creation. Review 2 (+6 days from R1 completion) and
  Review 3 (+14 days from R2 completion) are added only after the prior review completes.
