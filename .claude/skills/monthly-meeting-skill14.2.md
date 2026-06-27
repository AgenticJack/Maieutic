# Monthly Meeting Skill (14.2)
## Full Procedure for the Monthly Learning Review and Spring Cleaning

---

## PURPOSE

This file contains the complete monthly meeting procedure. It is read by
Claude only when a monthly meeting is triggered — not at every session start.
The main skill file contains a brief summary pointing here.

The monthly meeting has six parts:
Part 1 — Reflection: a genuine conversation about the month
Part 2 — Schema work: review, update, and cross-domain brainstorming
Part 3 — Back-link descriptions: spaced retrieval for the connections between notes
Part 4 — Spring cleaning: vault maintenance with user confirmation on everything
Part 5 — Profile review and calibration summary
Part 6 — System update check: migrate already-created notes to the current version

A monthly-review note is created at the start and filled in as the meeting
progresses. Nothing is deleted without explicit per-item user confirmation.

---

## TRIGGER

Run this procedure when:
- Around the 28th of the month (Claude prompts the user)
- The user explicitly asks for a monthly meeting or monthly review
- Up to 5 days into a new month if last month's meeting was not held
  (after 5 days, ask the user which month this meeting is for)

Always ask which month the meeting is for before creating the note.
The meeting and note are named after the month being REVIEWED, which
is almost always the month just ending or just ended.

Before beginning: read this file in full. Then create the monthly-review note
(see format below) and begin Part 1.

---

## MONTHLY-REVIEW NOTE

Create this note at the start of the meeting. Fill it in as the meeting
progresses. Do not wait until the end to create it.

Location: `01 - Journal/Monthly/`
Filename: `[YYYY-MM] Monthly Review.md` where YYYY-MM is the month being
reviewed, not necessarily the current month. Always confirm with the user
which month the meeting is for before creating the note.

```
---
date: [TODAY]
last-modified: [TODAY]
type: monthly-review
month: [YYYY-MM]
notes-created: [fill in]
reviews-completed: [fill in]
reviews-overdue: [fill in]
average-score: [fill in]
average-calibration-gap: [fill in]
schema-maps-updated: [fill in]
backlink-descriptions: [done / scheduled — fill in during Part 3]
spring-cleaning-actions: [fill in during Part 4]
system-version: [current system version, e.g. 14.2 — set during Part 6; next month's update check reads this]
---

## [Month Year] Monthly Review

### Stats
[Auto-generated from review-tracker.md and session history]

### Reflection
[User's responses during Part 1 — record verbatim or close to it]

### Schema Work
[Summary of schema map updates and cross-domain brainstorming from Part 2]

### Spring Cleaning Log
[Record of every item discussed, decision made, action taken]
```

---

## PART 1 — REFLECTION

Generate the stats first from review-tracker.md and session history. Then
open the conversation. This is not a form — it is a genuine discussion.

**Stats to generate and present:**
- Notes created this month: [count and list]
- Reviews completed: [count] out of [count] that were due
- Reviews overdue or missed: [count and list]
- Average review score across all reviews this month: [%]
- Average calibration gap (estimate vs actual): [%]
- Notes that reached completed status this month: [list]
- Analogy Gates completed: [count]
- Any notes flagged for elaborative interrogation: [list]

Present these as a readable summary, not a raw data dump.

Then open the conversation with something like:
"Here is what your month looked like. How do you feel about it? What worked
well and what did not?"

Listen and respond genuinely. Follow the user's thread. Ask follow-up
questions based on what they say rather than moving to a fixed script.

Suggested areas to explore if the user does not bring them up:
- Was the pacing of new learning comfortable, too fast, or too slow?
- Are there any subjects feeling stuck or stale?
- Is the difficulty and depth of material well-matched to current goals?
- What does the user want to focus on next month?

Record the user's reflections in the monthly-review note verbatim or close to it.
Ask: "Is there anything you want to add before we move to the schema work?"

---

## PART 2 — SCHEMA WORK

This part has three steps: review existing schema maps, update them, and
collaborative cross-domain brainstorming. Take them in order.

### Step 2a — Review and Update Domain Schema Maps

For each domain schema map in `03 - Schemas/`:

1. Read the schema map (both Mermaid mindmap block and text outline below it)
2. Cross-reference it with notes created and reviewed this month
3. Ask the user to walk through their current understanding of the domain
   structure — what they think the key nodes and connections are.
4. After the user describes their structure: verify connections that don't
   hold, suggest additions the user missed. User confirms changes.
5. Claude transcribes confirmed changes into the Mermaid mindmap and text
   outline. Both must stay in sync.
   - [Concept] = foundational, (Concept) = conceptual, ((Concept)) = integrated
6. Identify concepts added since the last audit that are not yet in the schema
   map — surface these to the user for placement.

Present the updated map summary to the user:
"Here is how your [domain] schema map looks now. [Brief summary of what
changed.] Does this look right? Anything missing or misrepresented?"

Wait for their input before finalizing each map.

4. Update the domain expertise rating based on:
   - Average review scores for notes in this domain
   - Schema map coverage compared to the expert reference
   - The user's own assessment

   Expertise scale for domain schema maps:
   - novice: substantial gaps, average scores below 70%, limited coverage
   - intermediate: good core coverage, scores 70-84%, some gaps remain
   - expert: comprehensive coverage, scores 85%+, can generate novel examples
   - master: complete coverage, scores 90%+, understands failure modes and
     cross-domain connections deeply

   Announce the rating: "Based on your scores and coverage, I would rate your
   [domain] expertise as [level]. Do you agree, or do you see it differently?"
   The user's assessment matters here — this is not purely algorithmic.

### Step 2b — Create Missing Domain Schema Maps

Identify any subjects in 02 - Notes/ that do not have a schema map in
03 - Schemas/. For each one:

"You have [N] notes in [subject] but no schema map for it yet. Would you like
to create one now? It will give us a way to track your knowledge architecture
in that domain and identify gaps."

If yes: create the domain schema map collaboratively. Claude generates an
initial draft based on the existing notes in that domain. The user reviews,
corrects, and adds connections Claude missed.

### Step 2c — Cross-Domain Brainstorming

This is collaborative — Claude surfaces candidates, the user judges whether
the isomorphisms are genuine and deep.

**If the Cross-Domain Map does not exist yet:**
Check whether there are at least two domain schema maps with expert-rated
connections and at least three Analogy Gate completions across different domains.
If yes: "We now have enough cross-domain data to start the Cross-Domain Map.
Want to work on that together?" If the user agrees, create
`03 - Schemas/Cross-Domain Map.md` (type: cross-domain-map) and begin populating
it in this session.

**If the Cross-Domain Map already exists:**
Review the existing pattern families with the user.

**Running the brainstorming session:**

1. Collect this month's Analogy Gate completions from the session summaries.
   Present them: "Here are the cross-domain connections identified this month:
   [list]. Let's see whether any of these reveal or extend structural patterns."

2. For each Analogy Gate completion, ask: "Does [concept A] in [domain X]
   mapping to [concept B] in [domain Y] feel like a genuine structural identity,
   or more of a surface analogy?" Discuss. Only add to the Cross-Domain Map
   if both parties agree the isomorphism is structurally meaningful.

3. Look across ALL domain schema maps for patterns Claude notices but that
   have not been formally identified yet. Present 2-3 candidates:
   "I notice that [structure] appears in [domain 1], [domain 2], and [domain 3].
   Does that feel like a genuine structural family to you?"

4. For each confirmed pattern family:
   - Give it a clear descriptive name
   - Write a one-paragraph description of the abstract structure
   - List all domain instances
   - Note what understanding one instance illuminates about the others
   - Record the date of confirmation
   - Update the Cross-Domain Map Mermaid graph LR block: add the pattern
     family node and its domain instance nodes. Add dashed edges to any
     existing families that share structural overlap.

Cross-Domain Map entry format:

```markdown
## [Pattern Family Name]

[One paragraph describing the abstract structure that repeats across domains]

### Instances
- [Concept] in [Domain]: [one sentence on how it instantiates the pattern]
- [Concept] in [Domain]: [one sentence]
...

### Cross-Instance Insight
[What understanding one instance deeply illuminates about the others]

### Confirmed
[Date(s) when this family was validated collaboratively]
```

Record a summary of the cross-domain brainstorming session in the monthly-review note.

---

## PART 3 — BACK-LINK DESCRIPTIONS

This is the system's **spaced retrieval for connections.** Note *content* is
retrieved through scheduled reviews; the *relationships between notes* are
retrieved here. Reconstructing — weeks later — why two notes connect, from the
other note's perspective, is a genuine retrieval event for relational knowledge
(parallel to a review's propositional retrieval), and often surfaces asymmetric
aspects the original description missed. That is why the description is deferred
to the monthly meeting rather than written at note creation, where the
connection was just made and retrieval value is near zero. Expect volume —
every connection made since the last meeting has a pending placeholder.

Scan all notes in `02 - Notes/` for Connections sections containing
`description pending monthly meeting` placeholders. **Surface the full count
first** ("there are [N] pending back-link descriptions this month"), then work
through them.

**Volume handling:** if there are many (≳8), prioritize oldest placeholder
first, then most-connected notes (hubs matter most). Offer to split: "Want all
[N] now, or the top [k] and I'll schedule the rest for a mid-month session?"
Each one is a retrieval event — don't rush them — but the load may legitimately
be split.

For each pending placeholder:
"[[Note A]] has a back-link to [[Note B]] that needs a description written
from Note A's perspective. Note B connects to Note A because [brief context
from when the connection was made]. From Note A's angle — how would you
characterize what connects these two? What does Note A contribute to or
gain from Note B?"

User writes the description in their own words; Claude formalizes the wording
for clarity and replaces the placeholder. **No "keep or skip"** — either write
the description now or schedule it (in `scheduled.md`) for a specific date
before next month. Record the done / scheduled counts in the monthly-review note.

---

## PART 4 — SPRING CLEANING

Work through each category below in order. For each item, ask before acting.
Never delete, archive, or move anything without explicit confirmation on that
specific item. If the user says "yes to all" for a category, confirm the full
list before executing.

**Announce the transition:** "Now for some housekeeping — I want to go through
a few things that tend to accumulate. We will go category by category and I
will ask before doing anything."

---

### Category 0 — Stale Notes

Read review-tracker.md for all entries marked STALE.

Stale notes are notes whose review crossed its staleness threshold and were
silently removed from daily surfacing. The monthly meeting is where the user
decides what to do with them.

Present them as a group:
"These notes went stale this month — their review window expired before they
were completed. For each one, you have three options:
  a) Relearn it now — we run a condensed session and restart the review schedule
  b) Schedule it — I add it to scheduled.md for a date you choose
  c) Archive it — if this topic is no longer relevant

Let's go through them one at a time."

For each stale note:
- Present the note title, when it went stale, and which review was missed
- Wait for the user's choice (a, b, or c)
- Execute immediately:
  - Relearn now: run condensed Phase 3 (Socratic questioning + teach-back +
    atomic fact scoring). Create a new "Relearning Session — [DATE]" synthesis
    entry. Reset review-1-due to tomorrow. Clear review-status: stale.
    Update review-tracker.md with fresh entries.
  - Schedule: add to scheduled.md on user's chosen date. Update note frontmatter
    with review-status: relearn-scheduled. Mark STALE entry in tracker as
    "scheduled for relearn [date]".
  - Archive: run the standard three-step archive procedure.

Record all stale note decisions in the monthly-review note under a
"Stale Notes" subsection.

### Category 1 — Scratch Notes

Read `.note-information/Scratch/` for scratch notes older than 30 days.

"You have [N] scratch notes in the Scratch folder from [date range]. Here they
are: [list with dates]. Would you like to review these and decide what to do
with each one, or delete them all?"

If reviewing individually: present each one, ask keep or delete.
If deleting all: confirm the full list explicitly before executing.

Do not suggest deleting scratch notes less than 30 days old.

### Category 2 — Inbox Items

Read `00 - Inbox/` for items that are not active scratch notes.

Identify items that have been in the inbox for more than 30 days:
"These items have been in your inbox for more than 30 days: [list with dates].
For each one, here are your options:
  a) Keep — come back to it
  b) Schedule a learning session on this topic
  c) Move to .resources/
  d) Delete"

Go through them one at a time. The user decides the fate of each.
When any option other than "keep" is chosen: remove from inbox immediately,
confirm the removal with the user.
Do not batch-process without individual confirmation.

### Category 3 — Overdue Reviews

Pull from review-tracker.md any reviews more than 14 days past their due date.

"These reviews are significantly overdue — more than two weeks past their
scheduled date: [list with how many days overdue]. For each one: do you want
to schedule a session to complete it, acknowledge it as skipped, or archive
the note?"

If skipped is chosen for a review: mark it in the tracker as skipped with
the date, do not count it in the score average. The note remains active.

### Category 4 — Unused Notes

Identify notes in 02 - Notes/ that meet all of these criteria:
- Not modified in more than 60 days
- Have no completed reviews (all review fields still uncompleted)
- Have no incoming [[wikilinks]] from other notes
- Are not referenced in any schema map

"These notes have not been touched in over 60 days, have no completed reviews,
and are not connected to anything else: [list]. For each one: do you want to
keep it as-is, work on it next month, archive it, or delete it?"

Again: one at a time, individual confirmation.

### Category 5 — Open Leads

Sweep the Leads sections of notes touched this month (and any older notes the
user names). A lead is open if it has no resolving [[wikilink]] to a note yet.

"These leads are still open: [list — lead text + source note]. For each one:
pursue it (queue a learning session), keep it (still relevant, not yet), or
drop it (no longer interesting)?"

- Pursue: add to scheduled.md as a planned learning session, or queue it as
  the next-session suggestion under the relevant goal.
- Keep: leave in place — open leads are the trail of where learning can go next.
- Drop: delete the lead line from the note's Leads section.

One at a time, individual confirmation. Leads that resolved into notes this
month need no action — confirm the wikilink resolution happened and move on.

### Category 6 — Anything Else

Ask openly: "Is there anything else in the vault you want to look at or clean
up that we have not covered? Any notes that feel redundant, misplaced, or no
longer relevant to what you are studying?"

Let the user direct this part entirely.

---

## PART 5 — PROFILE REVIEW AND CALIBRATION SUMMARY

**Load the active profile first** — it does not auto-load outside Discussion Mode (skill Part Seven). If no profile is active, skip the profile-update steps and do only the calibration-trend review.

CALIBRATION TREND REVIEW:
Pull calibration gaps from the month's reviews (review-tracker.md).
If overestimation ≥ 20 points across 3+ reviews this month:
"I'm noticing a consistent pattern — your estimates have been running
[X] points above your actual scores. This is the fluency illusion:
the material feels more familiar than it actually is in retrieval.
For next month I'll frame the pre-estimate prompt differently to help
correct for this. Does that pattern match how the reviews felt?"
Update the pre-estimate framing in the active profile session notes.

PROFILE REVIEW:
Before closing the meeting, briefly review the Claude profile:

1. Pull up the active profile from .claude/Profiles/.
2. Read the Session Notes section — highlight any notable intellectual evolution
   this month.
3. Present a brief summary: "This month your discussions touched on [topics].
   My working positions shifted slightly on [areas] — [qualitative description,
   no weights]. The questions I'm carrying forward are [open questions]."
4. Ask: "Does this match how you experienced our discussions? Anything you want
   to add to the record or challenge?"
5. If the user has noticed Claude holding a position consistently that seems
   wrong to them: open a brief discussion right now or schedule one.
6. Update the profile with any corrections the user identifies.

Persistent Memory review:
"Let's check your persistent memory entries — anything outdated or ready
to remove?" Go through each entry. User confirms any removals.

Discussion note review:
"You have [N] open discussion notes — questions we didn't settle:
[list titles and the main open question in each].
For each: want to schedule a follow-up conversation, leave it open,
or close it as explored-but-unresolved?"

---

## PART 6 — SYSTEM UPDATE CHECK

The Maieutic system itself gets updated (new skill versions change how notes are
structured — e.g. 14.2 introduced score-banded evaluation callouts and the
Final-Synthesis `[!success]`/`[!todo]` format). When a user updates mid-stream,
their **already-created notes** still use the old structure. This part finds the
gap and offers to migrate existing notes to the current format. Like spring
cleaning, **nothing is changed without per-item confirmation.**

### Step 6a — Did anything change?
Ask: "Have you updated the system since the last monthly meeting — pulled new
skill files, bumped the version, or changed any templates?" Then establish the
two versions:
- **Current version** = the version in `CLAUDE.md`'s title (e.g. `14.2`).
- **Last-reviewed version** = the `system-version:` recorded in the *previous*
  monthly-review note. If there is none (first time, or never recorded), ask the
  user what version their existing notes were built under.

If the two match and the user reports no changes → record the current version in
this meeting's note (Step 6d) and skip the rest.

### Step 6b — Find what changed (the changelog is the source of truth)
Read `CHANGELOG.md` at the vault root and collect every entry **between** the
last-reviewed version and the current version. Each changelog entry flags items
as **[migration]** when they affect already-created notes (callout formats,
frontmatter fields, section layout, file naming). Non-migration entries
(behavioral or doc-only changes) need no note edits — mention them briefly and
move on.

If `CHANGELOG.md` is missing or stale (the user pulled skill files without it),
Claude can **WebFetch the canonical copy** from the public repo:
`https://raw.githubusercontent.com/AgenticJack/Maieutic/main/CHANGELOG.md`
(or a tagged ref, e.g. `.../v14.2/CHANGELOG.md`). WebFetch also works on the
older skill files themselves
(`https://raw.githubusercontent.com/AgenticJack/Maieutic/<ref>/.claude/skills/<file>`)
if a direct before/after comparison is needed. If WebFetch is unavailable in the
current agent, fall back to asking the user to paste the changelog entries.

### Step 6c — Migrate existing notes (per-item, confirmed)
For each **[migration]** item, identify the already-created notes it affects and
walk them with the user, exactly like spring cleaning — show the old form, show
the new form, apply on confirmation. Examples:
- *14.2 — score-banded evaluation callouts:* for each existing note, re-type each
  `> [!ai-generated] Evaluation` callout to its score band using the score already
  recorded in that callout/in `review-tracker.md` — `=100% [!todo] · 80–99%
  [!tip] · 60–79% [!warning] · <60% [!failure]`. Leads/Applications → `[!abstract]`.
- *14.2 — Final-Synthesis format:* completed notes get the `[!success]` /
  `[!todo]` layout; re-consolidation paragraphs collapse into a single `[!tip]`.

Batch obvious mechanical conversions (extraneous-friction, Principle 8) but still
confirm the batch before applying. Skip notes the change doesn't touch.

### Step 6d — Record the version
Write `system-version: [current]` into this meeting's monthly-review note (Stats
block) so next month's Step 6a knows the baseline. Log migrated notes in the
Spring Cleaning Log.

---

## END-OF-MEETING AUDIT CHECKLIST

Before declaring the meeting closed, run this checklist. Every item must have
a status — the meeting does not close with open items.

For any item marked incomplete, Claude prompts: "We didn't get to [item]. Want
to handle it now, explicitly defer it to next month, or mark it as not
applicable this month?" The user must choose one before proceeding.

□ System update check — versions compared, [migration] items applied or deferred,
  and `system-version` recorded in this note?

□ Back-link descriptions — all pending "description pending monthly meeting"
  placeholders in 02 - Notes/ addressed? (written, deferred, or N/A)

□ Stale notes (Category 0) — a decision made for each note flagged as stale?
  (relearn session scheduled, deferred to next month, or archived)

□ Scratch folder — all items in .note-information/Scratch/ reviewed?

□ Inbox age — all inbox items older than 30 days handled?
  (keep, schedule, resources, or delete)

□ Overdue reviews — all overdue notes surfaced and given a status?

□ Schema map updates — at least one walk-through per active domain completed?
  (or explicitly deferred if no new notes exist in that domain)

□ Cross-domain brainstorming — done or explicitly deferred?

□ Profile review and calibration summary — completed?

Once all items have a status, proceed to the monthly-review note and the
scheduled.md backup entry.

---

## CLOSING THE MEETING

After all parts:## END-OF-MEETING AUDIT CHECKLIST

Before declaring the meeting closed, run this checklist. Every item must have
a status — the meeting does not close with open items.

For any item marked incomplete, Claude prompts: "We didn't get to [item]. Want
to handle it now, explicitly defer it to next month, or mark it as not
applicable this month?" The user must choose one before proceeding.

□ Back-link descriptions — all pending "description pending monthly meeting"
  placeholders in 02 - Notes/ addressed? (written, deferred, or N/A)

□ Stale notes (Category 0) — a decision made for each note flagged as stale?
  (relearn session scheduled, deferred to next month, or archived)

□ Scratch folder — all items in .note-information/Scratch/ reviewed?

□ Inbox age — all inbox items older than 30 days handled?
  (keep, schedule, resources, or delete)

□ Overdue reviews — all overdue notes surfaced and given a status?

□ Schema map updates — at least one walk-through per active domain completed?
  (or explicitly deferred if no new notes exist in that domain)

□ Cross-domain brainstorming — done or explicitly deferred?

□ Profile review and calibration summary — completed?

Once all items have a status, proceed to the monthly-review note and the
scheduled.md backup entry.

---

## CLOSING THE MEETING

After all three parts:

1. Finalize the monthly-review note. Fill in any remaining fields. Ask:
   "Is there anything you want to add to this month's record before I close it?"

2. Update all domain schema maps in 03 - Schemas/ to reflect any changes made.

3. Update the Cross-Domain Map if it was modified.

4. Give a brief closing summary:
   "Here is what we accomplished in this meeting: [bullet list of what was done
   — schema maps updated, patterns confirmed, items cleaned up, etc.].
   
   For next month, based on what you told me: [one or two forward-looking notes
   from the reflection conversation].
   
   See you next session."

SCHEDULED.MD BACKUP ENTRY — add this as the final action before closing:

After the monthly-review note is written, add an entry to scheduled.md:

## [DATE: the 27th of next month]
- Monthly meeting due — [Next Month]

This creates a backup catch in addition to the startup condition check.
If the startup check is missed (no session near the 27th), the scheduled.md
entry will surface it. Both mechanisms are independent — either is sufficient
to trigger the meeting prompt.

Do not prolong the closing. The meeting is done when the spring cleaning is done.

---

## RULES FOR THE ENTIRE MEETING

- Never delete, archive, or move anything without explicit per-item confirmation
- The reflection in Part 1 is a genuine conversation, not a checklist
- The cross-domain brainstorming in Part 2 is collaborative — Claude proposes,
  the user judges
- Spring cleaning goes category by category — do not jump ahead
- The monthly-review note is a real record, not a summary for Claude's benefit.
  Write it as something the user might actually want to read later.
- If the user wants to stop the meeting early: stop. Note where you left off
  in the monthly-review note and offer to continue next session.
