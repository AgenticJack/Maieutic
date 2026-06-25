# Concept Note (Template)

Concept notes are **built by the AI at the end of the learning pipeline** — you
do not create them by hand. This file documents their shape so you know what the
AI produces and can read a note's structure at a glance. The live frontmatter
schema is authoritative in `CLAUDE.md → Frontmatter Schema`; this is the body.

Every concept note **starts `cognitive-state: generative`** — never `completed`
at creation, no matter how high the teach-back scored. It becomes `completed`
only later, via System D, after Review 3 (or the early path). See
`.claude/skills/pkm-principles14.0.md`, Parts Four & Six.

---

## Frontmatter

```yaml
---
date: YYYY-MM-DD
last-modified: YYYY-MM-DD
cognitive-state: generative     # generative | completed (never completed at creation)
depth: foundational             # foundational | conceptual | integrated
type: concept
tags: [review-day1]
recall-score:                   # most recent review score %
initial-score:                  # teach-back / Day 0 score %
initial-estimate:               # pre-handoff confidence estimate %
session-source:                 # path to scratch note in .note-information/Scratch/
analogy-gate-complete: false
completion-path:                # standard | early — set when completed
completed-date:                 # set when cognitive-state moves to completed

review-1-due: YYYY-MM-DD
review-1-estimate:
review-1: uncompleted
# Review 2 / Review 3 fields are added only as each prior review completes —
# never pre-populated at creation.
---
```

## Body

```
> [!description] What this note covers
> [1–2 sentences: core claim/mechanism — a scope identifier, not a summary]
> [Optional: what this note explicitly does NOT cover]

## [CONCEPT NAME]
## Connections        [confirmed links from the link gate — [[wikilinks]] only here]
## Leads              [AI-written at filing: Continuation / Deepening / Bridge leads,
                       inside an [!ai-generated] callout; plain prose, no forward wikilinks]
## Applications

## Final Synthesis
[Empty at creation. Written ONLY at completion — the note's single authority:
100% of the atomic facts + all vocabulary, in clean prose. Sourced three ways
(AI writes it / you write it / built from Review 3); any non-AI source is audited
to 100% with each addition announced.]

---
## Synthesis
### Initial Teach-Back — [DATE]
[verbatim user synthesis — transcribed word for word]
> [!ai-generated] Evaluation — [DATE]
> Estimated: [est] | Score: [X]% ([N]/[total] facts) | Calibration gap: [est − score]%
> Strong: [...] · Needs work: [...] · Corrections: [stated wrong → correct]

### Review 1 — [DATE]
[verbatim user synthesis]
> [!ai-generated] Evaluation — [DATE]

### Review 2 — [DATE]
[verbatim user synthesis]
> [!ai-generated] Evaluation — [DATE]

### Review 3 — [DATE]
[verbatim user synthesis]
> [!ai-generated] Evaluation — [DATE]
```

The Synthesis layers fill **in strict order** as reviews complete (Initial
Teach-Back → Review 1 → 2 → 3 — chronological, newest at the bottom). The
`## Final Synthesis` above is the current authority once written. A scheduled
Review 4+ appends below as `### Review 4 — [DATE]`.
