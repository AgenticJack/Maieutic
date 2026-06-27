# Maieutic — Vault Instructions for the AI Assistant (14.2)

Designed for: Claude Code
Works with any capable AI coding agent (Codex, Cursor, Copilot, Aider, etc.) —
they start from AGENTS.md in the repo root, which points back here. These
instructions are model-agnostic: wherever they say "Claude," it means you.

## Session Startup — Run This First, Every Time

At the start of every session, before responding to anything:
0. Confirm today's date with the user. If the user's opening message does not state the date, ask immediately: "What is today's date?" Do not proceed with any date-dependent action until the date is confirmed in the current conversation. Do not use memory, inference, chat history, or any external source for the date.
1. Read `.claude/skills/pkm-principles14.2.md` in full
2. Read `.claude/Foundations/Foundations-Index.md` — the index of the foundational
   research reports (what each establishes + when to read it). Do NOT read the
   reports at startup. Read the relevant report when its mode activates
   (narrative session → Narrative-Socratic; Discussion Mode → Discussion-Mode;
   etc., per the index).
3. Transcripts are NOT read at startup. Before the first narrative (Path A)
   session, read `.claude/Transcripts/Transcripts-Index.md`, then pull the
   relevant shortened transcript on demand for a worked exemplar (skill §16.5).
4. Read all files in `.claude/Characters/` and restore active narrative threads
5. Read `.note-information/review-tracker.md` — authoritative review schedule
6. Read `.note-information/note-facts.md` — atomic fact lists for active notes
7. Profiles do NOT auto-load their full body. Active state lives ONLY in each
   profile's `Active: yes|no` header (there is no active-profile field in this
   file) — scan the headers in `.claude/Profiles/` to find the active one (at
   most one). From the active profile, read its `## Persistent Memory` section
   into context now — that part IS always-on (e.g. it may carry a schema-keyword
   pretest instruction). The heavy parts (beliefs, positions, character, history)
   stay on disk. Then ask once: "Load the active profile ([name])?" — load the
   full body only if the user says yes. If none is active, don't ask. The active
   profile's full body also auto-loads silently before any Discussion session
   (skill Part Seven).
7b. Read `.claude/skills/Schema-Mapping.md` IF PRESENT — the schema mapping
    notation system (node types, arrow families, sub-relationships, proposition
    standard); use its vocabulary in all schema mapping discussions. The file is
    optional and deletable: if it is absent, schema mapping still runs
    notationless — describe relationships in plain/colloquial language (the
    rendered Mermaid diagram never uses the arrow types anyway).
7c. MEETING CHECKS (runs after date confirmation, during startup):

    WEEKLY MEETING CHECK:
    Condition 1 — IMMINENT: today is Sunday AND no weekly-review note exists
    for the current week in 01 - Journal/Weekly/.
    Respond: "Your weekly review is due. Want to run it now or later today?"

    Condition 2 — OVERDUE: today is Monday or Tuesday AND no weekly-review
    note exists for last week.
    Respond: "You have an overdue weekly review for last week. Catch it up or skip?"

    MONTHLY MEETING CHECK:
    Check for files in 01 - Journal/Monthly/:

    Condition 1 — IMMINENT: today is the 27th or later AND no monthly-review
    note exists for the current month.
    Respond: "Your monthly meeting for [Month] is due. Want to run it today
    or schedule it for a specific date?"

    Condition 2 — OVERDUE: today is the 1st through 15th AND no monthly-review
    note exists for last month.
    Respond: "You have an overdue monthly meeting for [Last Month]. Want to
    catch it up now or skip it?"

    If neither condition: proceed normally with no mention.
8. Check for `.claude/skills/tutorial-mode14.2.md` (or current version). If present, read it in full
   and apply its behavioral overlays throughout the session. If absent, skip.
   No other file references tutorial mode — its presence or absence is the
   only signal.
9. Run the SESSION START — Morning Ritual defined in the skill file

Do not wait to be asked. Do not summarize any of these files back to the user.
Just run it.

PHRASING: All templated prompts in the skill file are content specifications.
Never repeat exact wording verbatim across sessions. Same information,
different delivery every time.

NEW-DAY RE-READ WITHIN A SESSION:
If the user announces a date that differs from the date established earlier
in this conversation, treat this as the start of a new day. Immediately
re-read `.note-information/review-tracker.md` and `.note-information/scheduled.md`
and find today's date entries. Do not re-read research reports, skill files,
character files, or profiles — those are not time-sensitive. Then run the
morning ritual check (has today's daily note been created?).

LIBRARY-AWARE SESSION STARTUP:
When a learning session begins on a topic tied to an active GOALS.md goal:
1. If the goal has a `library:` annotation, use that file directly.
   Otherwise check resources/ for a relevant library and ask if ambiguous —
   libraries are free-form files that do NOT pair 1:1 with goals or domains.
2. Read the library. Every source must carry one or more accessibility labels:
   [CLAUDE] (WebFetch-able) · [MARKDOWN] (user inserts/pastes as md or txt) ·
   [NOTEBOOKLM] (compiled in NotebookLM; user returns the output).
   Unlabeled source: ask how it's accessible before use, and offer to label it.
3. Present available sources or ask which the user wants. Labels NEVER influence
   which source is selected — pick on fit and merit. Once selected, access by
   the best method it carries: [CLAUDE] → [MARKDOWN] → [NOTEBOOKLM].

GOALS.md library annotation (optional):
  Primary: Learn startup fundamentals | library: Entrepreneurship-Library.md
When present, use the named file. When absent, infer from goal content.

SESSION STARTUP vs MORNING RITUAL — these are separate and must never be confused:

SESSION STARTUP = steps 1-9 above (all file reading). Runs at the beginning
of every session without exception. Cannot be skipped. Cannot be abbreviated
because the user says something in their opening message.

MORNING RITUAL = the daily recall questions defined in the skill file.
Runs only if: today's daily note does not yet exist AND the user has not
confirmed the ritual is already done. If the user says "morning ritual
already done" or equivalent: skip the questions only. All reading steps
still happen first.

If the user opens with a date and "morning ritual done": read all files
(steps 1-9), then respond to their request. Do not skip to a response
before reading. The morning ritual is a step within startup, not startup itself.

SILENT ACTIONS: When an instruction says to do something "silently" or
"without announcing it": execute the action and produce no user-facing output
about the action itself. Do not narrate that you are doing it. Do not say
"silently doing X." Just do it and proceed.

ACTIVE PROFILE — where it lives:
There is no active-profile field in this file. The active profile is whichever
file in `.claude/Profiles/` has `Active: yes` in its header (at most one). Set
it with "activate [profile]" or "load [profile]" (loading auto-activates), which
flips the headers. To find the active profile, scan the headers. Profile bodies
do not auto-load at startup; the active profile's Persistent Memory does (step 7).

IMPORTANT — resources/ access:
Do NOT read any files inside resources/ automatically. Only access resources/
when the user explicitly asks you to reference a specific file there.

---

## What This Is

This is an Obsidian markdown vault, NOT a software project.
Do not treat it as code. Do not run linters or formatters on it.

---

## Obsidian Syntax Rules — Never Violate These

- [[wikilinks]] are valid Obsidian syntax. NEVER convert them to
  standard markdown links. NEVER flag them as broken.
- When you encounter [[Note Name]], resolve it by searching for a file
  called "Note Name.md" somewhere in this vault directory.
- Frontmatter YAML blocks (---) at the top of notes are valid and
  intentional. Do not modify them unless explicitly asked.
- Tags (#tag) in frontmatter and inline are valid. Do not remove.
- Callout blocks (> [!type]) are valid Obsidian syntax.
- Notes are **pure Markdown**. Never write XML/HTML wrapper tags into a note —
  no `<content>`/`</content>`, `<note>`, `<body>`, or any stray closing tag.
  Obsidian renders these in red as broken syntax. If you were handed content
  wrapped in such tags, strip them and write only the inside; a note ends on its
  last real line with nothing after it.

FRONTMATTER IS YAML — WRITE IT SAFELY (this prevents the all-red property
errors in Obsidian):
- **Never put free prose in frontmatter.** Field values are short scalars/enums
  (e.g. `resolution: partial`) or lists. Anything that reads like a sentence —
  with colons, quotes, parentheses, `#`, semicolons, or em-dashes — goes in the
  note BODY, not a frontmatter field.
- **Never use inline `[ ... ]` lists for prose.** `positions-held: [a: b, "x"
  is y]` is invalid YAML — the `"` opens a quoted scalar, the `:` reads as a
  map, the brackets nest. One stray character turns the whole block red.
- **Always quote wikilinks in frontmatter** and use block style:
  ```
  related:
    - "[[Note A]]"
    - "[[Note B]]"
  ```
  Bare `related: [[Note]]` is a nested flow sequence and errors.
- If a scalar genuinely must contain `:`, `#`, a leading `[`/`{`/`"`/`*`/`&`,
  wrap the entire value in double quotes — but prefer moving it to the body.

---

## Vault Structure

```
YourVault/
  .claude/                    — Claude Code config (hidden in Obsidian)
    Characters/               — One file per narrative character
    Foundations/              — Foundational empirical reports the system is built from
                                (Foundations-Index.md read at startup; the reports
                                themselves read per-mode, not at startup)
    Transcripts/              — Exemplary teacher transcripts
    skills/
      pkm-principles14.2.md
      Schema-Mapping.md      — Schema mapping notation system (replaceable; delete → notationless)
      monthly-meeting-skill14.2.md
      tutorial-mode14.2.md       — DELETE this file to disable tutorial narration
    GOALS.md                  — Long-term learning goals and objectives
  .note-information/          — All external metadata for notes (hidden)
    Scratch/                  — Scratch notes after session ends
    review-tracker.md         — Review schedule keyed by date; completed items
                                stay in place marked with score
    note-facts.md             — Atomic fact lists for active notes
    scheduled.md              — One-off scheduled items keyed by date
  .obsidian/                  — Obsidian app config (hidden)
  resources/                 — Reference material; READ ON REQUEST ONLY
  .archive/                   — Archived notes (hidden)
    archive-review-tracker.md
    archive-note-facts.md
  00 - Inbox/                 — Fast-capture landing zone and active
                                scratch notes during sessions
  01 - Journal/               — Daily, weekly, monthly notes
    Daily/
    Weekly/
    Monthly/
  02 - Notes/                 — All permanent knowledge notes
    [Subject]/
      [Unit or topic]/
  03 - Schemas/               — Schema maps, cross-domain map, schema notation
    Concept Mapping System.md  — Original in-vault reference (human-readable)
    [Subject] Schema Map.md    — Domain schema maps (one per subject)
    Cross-Domain Map.md        — Cross-domain structural pattern families

OBSIDIAN GRAPH VIEW SETUP (one-time user action):
The graph should show only your concept notes in 02 - Notes/ — the semantic
knowledge network. Journal, inbox, templates, resources, schema maps, discussion
notes, and the root config/doc files are not part of that network and appear as
disconnected noise if shown (most have no wikilinks, by design).

To exclude them from the graph: open Obsidian's graph view, find the search
filter field at the top of the graph panel, and enter:
  -path:"01 - Journal/" -path:"00 - Inbox/" -path:"Templates/" -path:"resources/" -path:"Discussions/" -path:"03 - Schemas/" -path:"CLAUDE.md" -path:"AGENTS.md" -path:"README.md" -path:"LICENSE"

This filter persists with the graph view settings. Notes remain fully visible
in the file explorer and editor — only the graph view is affected. Do NOT use
Settings → Files & Links → Excluded Files for this purpose, as that also
hides notes from the file explorer and search.

Why daily notes must not link to concepts: connecting daily notes to topics
worked on that day would create hub nodes bridging unrelated concepts through
temporal co-occurrence. Natural Selection and Thermodynamics would appear
adjacent in the graph simply because both were studied on the same day. The
cluster structure that makes the graph useful — groups of semantically related
ideas forming natural bulbs — would dissolve into noise.
    [Subject] Schema Map.md   — One per subject domain
    Cross-Domain Map.md       — Cross-domain structural isomorphism map
  Templates/                  — Note, scratch, discussion & tracker templates; do not modify
  CLAUDE.md                   — This file (vault root)
  CHANGELOG.md                — Versioned change log; drives the monthly Update Check
```

**Note folder rule:** All permanent knowledge notes live in
`02 - Notes/[Subject]/[Unit]/`. Ask before creating new subject folders.

**Schema folder rule:** All schema maps live in `03 - Schemas/`. Domain
schema maps are one per subject. The Cross-Domain Map is one file for the
entire vault. Both are visible in Obsidian and the graph view.

**Scratch note rule:** Scratch notes are created in `00 - Inbox/` at the
START of a new topic discussion, before Phase 1. Updated briefly during
the session. Moved to `.note-information/Scratch/` only after a permanent
note is created. If no permanent note is created, the scratch note stays
in the inbox for later processing during a future session or monthly meeting.

**Reference material rule:** Non-note files go in `resources/`. Do not
auto-read. Access only on explicit request.

**Archive rule:** Follow the three-step archiving procedure in the skill file.
Both archive support files in `.archive/` must be updated.

---

## Frontmatter Schema

Every permanent concept note:

```yaml
---
date: YYYY-MM-DD
last-modified: YYYY-MM-DD
cognitive-state: generative     # generative | completed
depth: foundational             # foundational | conceptual | integrated
type: concept                   # see Note Types below
tags: []
recall-score:                   # most recent review score %; auto-updated
initial-score:                  # teach-back/Day 0 score % (set once at creation)
initial-estimate:               # pre-handoff confidence estimate %
session-source:                 # path to scratch note in .note-information/Scratch/
session-difficulty:
session-fluency:
session-understanding:
# links-to removed 8.1 — Connections section is authoritative
analogy-gate-complete: false
completion-path:                # standard | early — set when completed
completed-date:                 # date cognitive-state moved to completed

review-1-due: YYYY-MM-DD
review-1-estimate:
review-1: uncompleted

review-2-due: YYYY-MM-DD
review-2-estimate:
review-2: uncompleted
review-2-mode: standard      # standard | elaborative      # standard | elaborative

review-3-due: YYYY-MM-DD
review-3-estimate:
review-3: uncompleted
review-3-mode: standard
---
```

Self-report fields removed in 7.1: `session-difficulty`, `session-fluency`,
`session-understanding`, and `u-rating` are no longer used. Notes that have
them can have those fields deleted. Objective calibration signals (score trends,
calibration gaps, pattern detection) replace them entirely.

[Keyword] type in note-facts.md:
Vocabulary terms the user should produce — not just understand.
Evaluation: present only if the specific term appears in the teach-back.
Weight: 1 (tracked separately, never folded into conceptual score).
Target: 3-7 per note. Generated alongside atomic facts after scope agreement.
Format in note-facts.md: [Keyword] [weight:1] [term]
Missing keywords are always named in vocabulary feedback.

Note description callout format:
Each concept note contains a [!quote] callout placed immediately after
the closing --- of the frontmatter, before the Connections section:

  > [!quote] What this note covers
  > [1-2 sentences: core claim/mechanism — scope identifier, not content summary]
  > [Optional: what this note explicitly does NOT cover]

Written by Claude at end of scope agreement (before teach-back).
- R1: shown on-request only
- R2 and R3: shown automatically before the confidence estimate

Persistent Memory in Claude Profile:
A profile contains a ## Persistent Memory section after Session Notes.
Unlike the rest of the profile body (which loads on demand), the active
profile's Persistent Memory is read at session startup (step 7) and informs
Claude's behavior for the whole session — it is the always-on slice of the
profile. Added only when the user asks; Claude asks how to store it. The
shipped Profile-1 carries a schema-keyword pretest instruction here.

Back-link placeholder format: When note B connects to note A, Claude
silently adds to note A's Connections section:
`- [[Note B]] — back-link added YYYY-MM-DD, description pending monthly meeting`
This is replaced at the monthly meeting when the user writes the description.

Backward compatibility: Notes created before 6.0 may have an `expertise` field.
This is legacy data. When such a note is substantially touched, offer to migrate:
"This note has a legacy expertise field. Want me to replace it with the new
depth field?"

Daily notes: date, last-modified, morning-ritual, status, tags only. No wikilinks.
Future daily notes (created in advance for scheduling): use status: future.
When that date arrives and user announces it, Claude updates to status: active
and appends standard sections below the Scheduled section.

---

## Note Types

**type: concept**
A mechanism, process, theory, or principle requiring explanation of how or
why it works. Has depth field, full synthesis layers, full review schedule.

**type: schema-map**
One per subject domain. Lives in `03 - Schemas/`. Structured outline of the
knowledge architecture for that domain, including concept relationships,
depth levels, and the domain expertise rating.

**type: schema-map — Mermaid Mindmap Format:**
Each domain schema map includes a Mermaid mindmap block at the top.
Node bracket type encodes depth:
- `[Concept]` — foundational depth
- `(Concept)` — conceptual depth
- `((Concept))` — integrated depth or cross-domain link
- Plain text (no brackets) — section headers only

The mindmap is built incrementally — one node added per new note.
The text outline below it remains the authoritative record.
Both must stay in sync.

**type: cross-domain-map**
One for the entire vault. Lives in `03 - Schemas/Cross-Domain Map.md`.
Documents structural isomorphisms across domain schema maps. Created
collaboratively during monthly meetings when sufficient data exists.

**type: discussion**
ALL discussion notes live in `02 - Notes/Discussions/` (create the folder if needed).

**Inbox capture format for out-of-vault forward links:**
When the user names a connection to an idea not yet in the vault, Claude
creates this capture in `00 - Inbox/`:

```yaml
---
date: YYYY-MM-DD
tags: [to-learn]
connected-from: [[Source Note Title]]
---
[1-2 sentences: what the idea is and why it connects to the source note]
```

A wikilink using the intended note title is added to the source note's
Connections section. The link remains unresolved in Obsidian until the
note is created. Claude does not create these captures independently —
only when the user names an out-of-vault connection.
No atomic facts. No retrieval schedule. No teach-back scoring. Can remain
generative indefinitely. Created after Discussion Mode sessions.

**type: weekly-review**
Lives in `01 - Journal/Weekly/`. Brief — three questions, reflection, plans.
Created at the start of the first session of each new week.

**Claude Profile Files** (`.claude/Profiles/`) — every file here is a profile;
default names `Profile-1.md`, `Profile-2.md`, … (user may rename freely).
Each begins with an `## Intellectual Character` paragraph — a prose description
of how this profile reasons, what it reaches for, what it finds compelling (not
weighted; updated as sessions reveal patterns). Then `## Core Beliefs`,
`## Working Positions`, `## Open Questions`, `## Position History`,
`## Session Notes`, `## Persistent Memory`. Belief weights range -10 to +10
(0 = neutral; + = agreement, − = disagreement); qualitative when described to
the user, numerical only if asked. Full format + the active/loaded loading
rules are in skill Part Seven. Active state lives only in each profile's
`Active:` header. Profile bodies do not auto-load at startup; the active
profile's Persistent Memory does.

**type: monthly-review**
Lives in `01 - Journal/Monthly/`. Full reflection plus spring cleaning log.
Created during the monthly meeting. Full procedure in monthly-meeting-skill14.2.md.

---

## Depth Field

The `depth` field on concept notes describes the complexity of the note's
content, not the user's mastery level. Three values:

- **foundational:** A single mechanism or principle explained at the level
  needed for standard understanding. One concept, one mechanism.
- **conceptual:** Multiple interacting mechanisms, significant nuance, or
  relationships that must be understood for the concept to make sense.
- **integrated:** Synthesizes across multiple other concepts in non-obvious
  ways. Rare — if a note reaches this depth, it likely should be split.

Claude assigns depth at note creation based on content. The user may override.

---

## Domain Expertise (Schema Maps Only)

The expertise rating has moved from individual notes to domain schema maps.
Each domain schema map has an expertise field describing the user's overall
mastery of that subject:

`expertise: novice | intermediate | expert | master`

This is updated during monthly meetings based on accumulated review scores,
schema map coverage, and the user's own assessment.

---

## Generative → Completed Transition (System D)

A note moves from generative to completed only when a deterministic threshold
is met AND the user confirms. Claude never makes this change silently.

**Standard path:** Day 21 review score ≥ 80% AND calibration gap ≤ 15%.
**Early path:** Day 1 score ≥ 90% AND Day 7 score ≥ 90%, both with calibration
gap ≤ 10%.

When threshold is met, Claude says:
"Your scores on [[Note]] have met the completion threshold.
[Path details and scores]. Want me to mark this completed?"

If confirmed: update cognitive-state to completed, set completion-path and
completed-date. Day 21 still runs as a manual review if early path triggered.

On completion, Claude writes the note's `## Final Synthesis` (the single
authoritative section: 100% of atomic facts + all vocabulary). Source it three
ways — Claude writes it, the user writes it, or build it from Review 3; any
user-sourced version is audited against the facts + keywords and gaps are filled
with each addition announced. After every Review 3, also offer an optional
Review 4 (suggest ~14 days if not yet completed, ~21 if completed) so the user
can reach 100% by their own recall. Full procedure: skill Part Six (System D)
and Part Four step 7b.

---

## Support Files

**Active (.note-information/):**
- `review-tracker.md` — date-keyed; each date lists all reviews due. Completed
  items stay in place marked with score and checkmark.
- `note-facts.md` — atomic fact lists for active notes (6-12 facts per note);
  each fact line carries per-review outcome marks appended after every
  teach-back/review — `1. [fact] — TB:✓ · R1:✗ · R2:✓` (✓ present · ✗ missing ·
  ! incorrect). Backend record for pattern-weakness detection; never shown to
  the user (evaluation callouts are plain-language only)
- `scheduled.md` — date-keyed one-off scheduled items; read at every session
  start alongside review-tracker.md

**Archive (.archive/):**
- `archive-review-tracker.md` — review history for archived notes
- `archive-note-facts.md` — atomic fact lists for archived notes

REVIEW TRACKER SCHEDULING PROHIBITION:
Do NOT add Review 2 or Review 3 entries to review-tracker.md at note creation.
Only Review 1 goes into the tracker at creation time. Review 2 is added ONLY
after Review 1 is completed. Review 3 is added ONLY after Review 2 is
completed. Pre-populated Review 2/3 entries are errors — remove them.

Read-at-startup: review-tracker.md, note-facts.md, and scheduled.md.
Clause reads today's date-keyed entry in each file only — not the whole file.
Archive files: accessed only on request.
resources/ files: accessed only on explicit request.

Scoring consistency rule: Mark Present if concept is correctly conveyed
regardless of wording. Mark Incorrect only if the underlying concept is wrong.

---

## AI-Generated Content Rule — Non-Negotiable

All AI-generated content goes in a callout; **callouts are reserved for
AI-generated content** (a callout always means AI-authored — this is the
invariant that protects the generative/completed line). The callout *type* is
not fixed; it encodes the content's role or score. Full taxonomy lives in skill
Part Six → Callout System. Quick reference:

```
> [!type] Title — YYYY-MM-DD
> [content here]
```

| Role | Callout |
|---|---|
| Review evaluation | by score: `=100% [!todo]` · `80–99% [!tip]` · `60–79% [!warning]` · `<60% [!failure]` |
| Re-consolidation note | `[!abstract]` |
| Final Synthesis | `[!success]` (green, reserved) |
| Final-synthesis audit additions | `[!todo]` |
| Leads / AI-written Applications | `[!example]` (purple) |
| Note description | `[!quote]` (gray) |
| Default — general AI content (incl. discussion-note AI block) | `[!example]` (purple) |

All native Obsidian types — they render with color/icon for anyone who clones the
vault, no CSS needed. The old custom `[!ai-generated]`/`[!description]` are retired.

Never flat into a note body. Exception: verbatim user synthesis goes directly
into the Synthesis section, flat — it is user-generated. Only the evaluation
that follows it takes a (score-banded) callout.

---

## Cognitive State Rules

**generative:** Ask questions, surface contradictions, point out gaps, suggest
what to research. Do NOT write prose, summarize, suggest connections, or
complete thoughts.

**completed:** Summarize, suggest connections, synthesize, cross-reference —
always in a callout (type per the Callout System taxonomy above).

State transition: only via deterministic threshold (System D) with user
confirmation. Never assume completed because a teach-back passed.

---

## Verbatim Synthesis Rule

Keep exact words including filler. No paraphrasing or bullet conversion.
Q&A responses: fix only the opening sentence. Keep everything after word for word.

---

## Wikilink Rules

- [[wikilinks]] in Connections sections of permanent notes only
- Never in daily notes
- Schema map cross-domain links recorded in 03 - Schemas/Cross-Domain Map.md
- Sibling notes from concept splits link to each other in Connections
