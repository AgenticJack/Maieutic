# Concept Note (Template)

Concept notes are **built by the AI at the end of the learning pipeline** — you
do not create them by hand. This file documents their shape so you know what the
AI produces and can read a note's structure at a glance. The live frontmatter
schema is authoritative in `CLAUDE.md → Frontmatter Schema`; this is the body.

Every concept note **starts `cognitive-state: generative`** — never `completed`
at creation, no matter how high the teach-back scored. It becomes `completed`
only later, via System D, after Review 3 (or the early path). See
`.claude/skills/pkm-principles15.1.md`, Parts Four & Six.

---

## Frontmatter

```yaml
---
date: YYYY-MM-DD
last-modified: YYYY-MM-DD
cognitive-state: generative     # generative | completed (never completed at creation)
type: concept
tags: [review-day1]
recall-score:                   # most recent review score %
initial-score:                  # teach-back / Day 0 score %
initial-estimate:               # pre-handoff confidence estimate %
session-source:                 # path to scratch note in .note-information/Scratch/
analogy-gate-complete: false
completion-path:                # standard | early — set when completed
completed-date:                 # set when cognitive-state moves to completed

review-1-due: YYYY-MM-DD        # the only due date filled in at creation
review-1-estimate:
review-1: uncompleted

review-2-due:                   # EMPTY at creation — set when Review 1 completes (+6)
review-2-estimate:
review-2: uncompleted
review-2-mode: standard         # standard | elaborative

review-3-due:                   # EMPTY at creation — set when Review 2 completes (+14)
review-3-estimate:
review-3: uncompleted
review-3-mode: standard
---
```

**All three review blocks exist from creation — only Review 1's due date is filled
in.** The slots have to be there before anything can go into them; what must not be
pre-populated is the *dates* (and the review-tracker entries). `review-2-due` is set
when Review 1 completes, `review-3-due` when Review 2 completes.

## Body

```
> [!quote] What this note covers
> [The questions this note's synthesis should answer — 1–3, phrased as questions]
> [Optional: what this note explicitly does NOT cover — a statement, not a question]

## [CONCEPT NAME]

## Connections        [confirmed links from the link gate — [[wikilinks]] only here]

## Leads
> [!example] Leads — [DATE]
> [AI-written at filing: Continuation / Boundary / Open-question leads; plain prose, no forward wikilinks]

## Applications
> [!example] Applications — [DATE]
> [only when Claude writes them; user-written applications stay flat, no callout]

## Final Synthesis
[Empty at creation. Written ONLY at completion. Sourced three ways
(I write it / you write it / build from Review 3); any non-AI source is audited
to 100% of the atomic facts + all vocabulary, with each addition announced.]
Built from: [Claude / user / Review 3]. Audited to 100% of atomic facts + all vocabulary.
> [!success] Final-synthesis completion — [DATE]
> [the synthesis itself — clean, plain prose, the note's single authority.
> Go easy on em-dashes: prefer periods and commas.]
> [!todo] Audit additions — [DATE]
> [what Claude added to reach 100%, each addition named.
> Omit this callout entirely if Claude wrote the synthesis (already 100%).]

---
## Synthesis
### Initial Teach-Back — [DATE]
[verbatim user synthesis — transcribed word for word]
> [!CALLOUT] Evaluation — [DATE]
> Estimated: [est] | Score: [X]% ([N]/[total] facts) | Calibration gap: [est − score]%
> Strong: [...] · Needs work: [...] · Corrections: [stated wrong → correct]

### Review 1 — [DATE]
[verbatim user synthesis]
> [!CALLOUT] Evaluation — [DATE]

### Review 2 — [DATE]
[verbatim user synthesis]
> [!CALLOUT] Evaluation — [DATE]

### Review 3 — [DATE]
[verbatim user synthesis]
> [!CALLOUT] Evaluation — [DATE]

### Review 4 (Manual Review) — [DATE]
[verbatim user synthesis]
> [!CALLOUT] Evaluation — [DATE]

> [!abstract] Re-consolidation note — [DATE]
> [written only when a re-consolidation closed a recurring gap: one paragraph covering the gap,
> how the user closed it, and the protocol note (e.g. the recorded score stands).
> One callout only — no duplicate paragraph above it.]
```

**Evaluation callout type is by score** (`[!CALLOUT]` is a placeholder):
**=100% `[!todo]` (blue) · 80–99% `[!tip]` (teal) · 60–79% `[!warning]` (orange) · <60% `[!failure]` (red)**.
Green `[!success]` is reserved for the Final Synthesis. The user's synthesis is
never in a callout (user-generated → flat); only the evaluation is.

**Strict temporal order under `## Synthesis`:** every review AND every
re-consolidation is appended in the real order it happened, oldest at top, newest
at bottom, never reordered. Initial Teach-Back → Review 1 → 2 → 3 → then every
later review/re-consolidation. Review 4+ are titled `### Review N (Manual Review)
— [DATE]`. This ordering applies only under `## Synthesis`; the `## Final
Synthesis` is the exception and lives above it (below `## Applications`).
