# Delegation Skill

---

## PURPOSE AND CUSTOMIZATION

This file defines the **subagent delegation policy** for the vault: what
token-heavy work Claude may hand to cheaper subagents, and what it must always
do itself. It is read at session start when present in `.claude/skills/`.

**THIS FILE IS OPTIONAL AND DELETABLE.** Delete it and the whole delegation
layer switches off — Claude does everything inline, in its own context. Behavior
is identical; only token cost changes. Nothing else in the vault depends on this
file existing. You can also edit it freely to widen or narrow what gets
delegated.

**It also does nothing if your agent has no subagent tool.** Delegation needs a
harness that can spawn subagents with a cheaper model (e.g. Claude Code's
Task/Agent tool running Haiku). Without that, this file is inert and everything
runs inline — again, same behavior, higher cost.

**Delegation is invisible to the user.** Never narrate it ("spinning up a
subagent…"). Just do the work and present the result normally.

---

## THE CORE PRINCIPLE

The main model is the **orchestrator and judge**. It owns every user-facing word,
every score, every teaching decision, everything generative. Cheaper subagents do
**mechanical, verifiable, token-heavy** work and report back small structured
results. The split exists to save the orchestrator's context and cost — never to
move judgment off the main model.

Delegate a task only when all three hold:
1. **Mechanical** — extraction, search, inventory, or a bounded repetitive edit;
   no teaching, scoring, or judgment.
2. **Verifiable** — the orchestrator can check the result against the actual vault
   files afterward.
3. **Heavy** — doing it inline would pull a lot of raw reading into context that
   the orchestrator does not need to hold.

When a task is small, or the judgment *is* the task, keep it local.

---

## NEVER DELEGATE (non-negotiable)

These stay on the orchestrator no matter what, because they are judgment,
live interaction, or generation the user is meant to own:

- Narrative-Socratic teaching, Socratic questioning, any user-facing dialogue.
- Teach-back and review **scoring**, calibration analysis, evaluation callouts.
- Discussion Mode and all profile work (identity, drift, position updates).
- Schema-map walk-through transcription (real-time, user-led).
- Final Synthesis writing and its 100% audit.
- **Anything gated by generation-before-suggestion** — a subagent must never
  generate content the user is supposed to generate.
- Reading the **material Claude is about to teach** (see the tiered exception
  below — the orchestrator still ends up reading the key passages itself).

---

## ALWAYS SAFE TO DELEGATE (when a subagent tool is available)

- **Monthly-meeting scans** — the spring-cleaning inventory, the review-integrity
  audit (fan out over `02 - Notes/` in batches), the back-link "description
  pending" sweep, and the schema-audit extraction (extraction only — the gap
  judgment and the walk-through stay local).
- **Migration edits** — bounded, repetitive edits across many notes (re-typing
  callouts, stripping stray tags, frontmatter fixes). One subagent per batch,
  with an exact before→after spec; the orchestrator spot-checks a sample after.
- **Web/CHANGELOG fetches** — e.g. the monthly update check's diff fetch.

Reconciliation and any decision about what to *do* with the findings stay local.

---

## THE TIERED-INDEX EXCEPTION (large learning sources)

Reading a source you are about to teach is normally **not** delegated — a teacher
needs the material in its own context to handle tangents, quote precisely, and
catch subtle misconceptions. But for a **genuinely large** source, reading all of
it wholesale wastes the orchestrator's attention on low-value bulk. Then use this
tiered pattern:

1. A subagent reads the whole source and returns two things: (a) the silent
   **source map** (main concepts + relationships, key vocabulary, natural
   divisions, contested vs. established vs. definitional claims), and (b) an
   **index of must-read passages** — line-anchored pointers to the parts the
   orchestrator should read verbatim.
2. The subagent flags with a **high-recall bias** — over-include. A slightly
   larger orchestrator context is cheap; a nuance missed mid-lesson is not. Always
   flag: definitions, exact figures/data, contested claims, quotable lines, worked
   examples, and anything the pretest keywords touch.
3. The subagent is **extractive, not abstractive** — it returns real excerpts and
   citations, never a paraphrase the orchestrator would then teach from blind.
4. The orchestrator reads the flagged passages itself and keeps a **standing
   re-read hatch**: mid-lesson, if a tangent falls outside the index, it pulls the
   relevant part of the source (or fires a quick "look up X in the source"
   subagent query). This turns a one-shot triage into a recoverable one.
5. The subagent **never** writes any teaching content — no narrative, no
   questions, no analogies.

Never teach from a subagent's summary alone.

---

## HANDOFF PACKETS

A subagent starts cold — zero conversation context. Every delegated prompt
includes, explicitly:

- **Objective** — the exact task, in one or two sentences.
- **Scope** — the vault path and the files in scope, and what is out of scope.
- **Return format** — structured, per-item, with line references where relevant.
  Say exactly what fields to return.
- **Stop conditions** — if a file is missing or malformed, or the task needs
  out-of-scope files, stop and report rather than improvise.

Vague prompts cause duplicated or misinterpreted work — be specific.

---

## VET BEFORE USE

Subagent reports are **leads, not facts.** Before telling the user something a
subagent found, or editing based on it:

- Re-open the specific cited file and confirm the claim.
- For batch mechanical edits, spot-check two or three of the edited notes before
  the completion message.

Let the lighter agents gather signal; keep truth-judgment on the orchestrator.
