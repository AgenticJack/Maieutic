# Changelog — Maieutic

This file is the source of truth for the monthly meeting's **System Update Check**
(Part 6). When you update the system, each entry below tells the AI what changed
and — critically — which changes affect **already-created notes**. Those are
tagged **[migration]**; the AI offers to apply them to your existing notes during
the next monthly meeting. Untagged entries are behavioral or documentation
changes that need no edits to past notes.

The AI compares the `system-version` recorded in your last monthly-review note to
the current version (the number in `CLAUDE.md`'s title) and reads every entry in
between. If this file is missing or behind, the AI can fetch the canonical copy:
`https://raw.githubusercontent.com/AgenticJack/Maieutic/main/CHANGELOG.md`

---

## 14.2

- **[migration] Strip stray wrapper tags from note bodies.** Some notes picked up
  a literal `</content>` (or similar XML/HTML-style tag) at the very bottom — a
  generation artifact, not part of any template. Obsidian renders it red as broken
  syntax. Added a guard (notes are pure Markdown; no wrapper tags) and a
  completion-checklist item. *Existing notes:* delete any trailing `</content>` /
  `<content>` / `<note>` / `<body>` tag so nothing sits after the last real line.
- **[migration] Fully native callouts (custom types retired).** The two remaining
  custom callout types are gone, so every callout renders with a real color/icon
  for anyone who clones the vault — no CSS snippet needed. `[!description]` →
  `[!quote]` (gray); `[!ai-generated]` → `[!example]` (purple), which is now the
  single default for all general AI content (leads, applications, the
  discussion-note AI block, anything unspecified). *Existing notes:* re-type any
  `[!description]` callout to `[!quote]`, and any `[!ai-generated]` callout to
  `[!example]`.
- **[migration] Discussion-note frontmatter is now YAML-safe.** The old template
  put prose into inline `[...]` list fields (`positions-held`, `open-questions`,
  `resolution`, plus unquoted wikilinks), which breaks YAML — a stray `"`, `:`,
  `(`, or `[[` makes Obsidian render the whole property block red (~⅓ of notes).
  Frontmatter now holds only clean scalars/enums (`resolution: resolved|partial|
  open`) and quoted-wikilink lists; the prose moved to body sections (`## The
  Question`, `## Positions and Reasoning`, `## What Remains Open`, `## Resolution`).
  *Existing discussion notes:* move prose out of frontmatter into the body and
  quote any wikilinks, so the properties parse.
- **[migration] Score-banded evaluation callouts.** Review evaluations no longer
  use `[!ai-generated]`. The callout type now encodes the recorded score:
  `=100% [!todo]` (blue) · `80–99% [!tip]` (teal) · `60–79% [!warning]` (orange) ·
  `<60% [!failure]` (red). *Existing notes:* re-type each `[!ai-generated]
  Evaluation` callout to its score band using the score already recorded.
- **[migration] Final Synthesis format.** Completed notes use a plain
  "Built from… / Audited to 100%" line, then `> [!success] Final-synthesis
  completion` (the synthesis), then `> [!todo] Audit additions` (omitted if the
  AI wrote it). *Existing completed notes:* convert the Final Synthesis to this
  layout.
- **[migration] Leads / Applications callouts.** AI-written `## Leads` and
  `## Applications` now use `[!example]` (purple, matching wikilinks).
  *Existing notes:* re-type.
- **[migration] Re-consolidation entries.** Collapse the old header-paragraph +
  callout-paragraph into a single `> [!abstract] Re-consolidation note` paragraph.
- **[migration] Manual-review titling.** Reviews after Review 3 are titled
  `### Review N (Manual Review) — [DATE]`, appended under `## Synthesis` in strict
  temporal order. *Existing notes:* retitle any post-R3 reviews.
- Principle 7 relaxed: callouts are still reserved for AI-generated content, but
  the callout *type* now encodes role/score (Callout System, skill Part Six).
- Completion options after Review 3 are now presented explicitly as two presets
  (complete-now with three Final-Synthesis sourcing sub-options; or Review 4 in
  ~21 days) plus an always-stated reminder that any review interval can be
  scheduled anytime, even after completion.
- Final Synthesis prose guidance: go easy on em-dashes.
- Monthly meeting gains **Part 6 — System Update Check** (this mechanism).
- Skill files renamed `…14.0.md` → `…14.2.md` (14.1 was skipped).

## 14.0

- First public release as **Maieutic** (github.com/AgenticJack/Maieutic).
- Notes always start `cognitive-state: generative`; `completed` only via System D
  after Review 3 (or the early path).
- Added the `## Final Synthesis` section and the optional Review 4 offer.
- Persistent Memory loads at startup; active profile state lives only in each
  profile's `Active:` header.
- `Schema-Mapping.md` made swappable and deletable (deletion → notationless).
- Inbox template renamed; real Concept Note template added.
