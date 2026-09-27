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

## 15.1

- **Re-consolidation is now standard, and is retrieved rather than told.** It runs
  after **every** teach-back and **every** review, at every score — it is no longer
  a sub-60% remediation step, and must never be framed as one. It is a hybrid of
  Discussion Mode and Socratic tutoring: the AI does not state what was missed, it
  pulls it Socratically, dropping to a simpler component and building back up where
  a gap is total. On a strong score it pushes on edges, boundaries and connections
  instead. **The score is recorded before it begins and stands** — otherwise the
  trend line would measure post-help recall. The old Steps A/B/C are replaced by a
  single canonical Post-Scoring Flow (calibration reflection if the gap is ≥20 pts
  either way → re-consolidation, always → any pending back-link descriptions).
  *Existing notes:* nothing to change. Re-consolidation entries are now written only
  when one closed a genuine recurring gap, not for routine ones.
- **[migration] Back-link descriptions ride the next review instead of a date.** The
  monthly meeting's Part 3 is deleted. When a review runs on a note that carries
  pending back-link placeholders, those descriptions are written at the end of that
  session, after scoring and re-consolidation. Never scheduled by date, never batched.
  Both dated venues had already failed in practice: the monthly batch accumulated 52
  pending descriptions across 26 notes, and a weekly-batch trial went zero-for-seven —
  the problem was never the interval, it was that a standalone chore has no natural
  home. *Existing notes:* the placeholder wording changes from `description pending
  monthly meeting` to `description pending next review`; the old wording is still
  recognized and treated identically, so retyping is optional. Existing pending
  descriptions simply follow the new rule — each gets written the next time its note
  is reviewed. A completed note with no future reviews keeps its placeholders until a
  manual review or Analogy Gate carries them; the monthly integrity audit surfaces
  those as "stranded placeholders" rather than forcing them.
- **[migration] Note descriptions are phrased as questions.** The `[!quote]` callout
  now states *the questions the synthesis should answer*, not the claim itself. The
  callout is shown automatically before the Review 2 and Review 3 confidence
  estimates, so a description that stated the claim was handing over a compressed
  answer immediately before asking for retrieval. The "does not cover" boundary line
  stays a statement. *Existing notes:* rephrase the description callout as questions
  whenever a note is next touched (harmless if left).
- **Shorter responses, more turns.** Default to short turns and many of them — one
  400-word response should have been three 120-word exchanges. Quality and rigor are
  unchanged; depth arrives across turns rather than inside one. This is now Critical
  Rule #7, with the canonical spec in skill Part Ten. Two reasons: it restores the
  conversational dynamic both Path A and Discussion Mode depend on (engage every 3–4
  sentences), and a response that takes over a minute to generate is dead time in
  which attention is lost. Full-length output remains correct for the mandatory
  scoring block, the Final Synthesis, monthly-meeting stats, and anything the user
  asks to see laid out in full.
- **Leads are never deleted.** The monthly meeting's Open Leads category loses its
  "drop" option — leads are pursued or kept, nothing else. A lead costs one line and
  records a direction the material could go; deleting it trades a map of the
  unexplored edge for tidiness. Practical effect: that category becomes a read-only
  surfacing rather than a per-item grind, and only "pursue" answers generate actions.
- **A discussion-note → concept-note route.** After CAPTURE, the AI offers to run the
  standard Note Creation Procedure on a discussion, with the discussion note as the
  session source — so an idea built and sharpened in Discussion Mode can enter spaced
  retrieval instead of sitting outside it forever. Not automatic and not every time:
  the trigger is a claim or mechanism stable enough to be taught back, as opposed to
  a live question still being worked. Both notes persist and link to each other.
- **Naming rule for pre-planned series.** A topic deliberately planned in advance as a
  multi-note series names every note `[Series] - [Specific Topic] Part N`, so the set
  sorts and reads together. Planned series only — never retrofitted onto notes that
  merely turned out to be related.
- **[migration] Frontmatter: Review 2 / Review 3 due dates are explicitly empty at
  creation.** The three review blocks have always been written at creation — the slots
  must exist before anything can go into them — but the schema showed `YYYY-MM-DD`
  placeholders on all three due dates, which reads as an instruction to fill in a date
  at exactly the moment you must not. `review-2-due` and `review-3-due` are now shown
  empty, with the rule stated in place. *Existing notes:* if a note has a date in
  `review-2-due` or `review-3-due` whose prior review has not completed, clear it.
- **Monthly meeting renumbered to five parts.** With Part 3 (back-link descriptions)
  removed: 1 Reflection · 2 Schema work · 3 Spring cleaning · 3B Review integrity audit
  · 4 Profile review · 5 System update check. Earlier changelog entries referring to
  "Part 4B" (the integrity audit) and "Part 6" (the update check) mean 3B and 5 as of
  this version. The monthly-review note drops its `backlink-descriptions` field; the
  integrity audit gains a "stranded back-link placeholders" finding class.
- **Fixes.** The monthly-meeting skill's End-of-Meeting checklist and Closing section
  were duplicated by a bad paste that also corrupted the line it landed on ("After all
  parts:" run together with a heading); the stale second copy is deleted. `CLAUDE.md`
  no longer hardcodes a list of skill filenames in the vault-structure tree — 15.0 made
  the folder itself the extension point, and the list had already drifted out of date;
  the tree also had the graph-view prose spliced inside its code fence with the schema
  entries repeated afterwards, now separated, and gains the `Discussions/` folder it
  was missing. Retired 7.1 self-report fields (`session-difficulty`, `session-fluency`,
  `session-understanding`) are gone from the frontmatter schema block that still listed
  them. `Schema-Mapping.md` had 35 escaped `\---` separators rendering as literal text.
  Monthly-meeting Step 2a numbered its steps 1–6 and then started a second "4."; one
  inbox option pointed at `.resources/` instead of `resources/`. Skill files renamed
  `…15.0.md` → `…15.1.md`.

---

## 15.0

- **[migration] The `depth` field is retired.** The foundational / conceptual /
  integrated depth classification is gone — in practice nearly every note was
  "conceptual," so it was bloat. *Existing notes:* the `depth:` frontmatter line
  can be deleted whenever a note is next touched (harmless if left). Manual-review
  intervals after Day 21 are now judged by importance, not depth.
- **[migration] Schema maps become real concept maps (hybrid).** Each domain map
  now carries TWO Mermaid blocks: a lightweight `mindmap` overview (hierarchy) and
  a `flowchart` **concept map** with typed-shape nodes and *labeled* relationship
  edges (`A -- causes --> B`), scoped to a focus question. The old single
  `mindmap` (hierarchy only, depth-bracket encoded) could not carry labeled
  relationships, which made it near-redundant with the graph view. *Existing
  maps:* rebuild via a user-led walk-through during a monthly meeting (not an
  auto-convert — maps are user-authored).
- **Subagent delegation layer (new, optional).** A new `.claude/skills/Delegation.md`
  defines when cheaper subagents may do token-heavy *mechanical* work (bulk note
  scans, batch edits, large-source indexing) while the main model keeps all
  teaching, scoring, dialogue, generation, and judgment. Deletable; inert if the
  agent can't spawn subagents. No effect on existing notes.
- **Monthly Review Integrity Audit (new — Part 4B).** Each month (or on request)
  the AI reconciles every note against the trackers in both directions, catching
  orphaned notes, ghost tracker entries, broken review chains, stalled notes,
  missing Final Syntheses, overdue pile-ups, and schedule orphans. No effect on
  existing notes beyond surfacing what already slipped.
- **Skills folder is now the extension point.** `CLAUDE.md` no longer names
  individual skill files; at startup the AI reads *every* file in `.claude/skills/`
  (except any marked read-on-demand, currently just the monthly-meeting skill).
  Drop a skill file in to add behavior; delete one to remove its feature. No
  effect on existing notes.

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
