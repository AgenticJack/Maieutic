# **Maieutic** PKM: An AI-Run Personal Knowledge Management System

> ***Maieutic*** *(/meɪˈjuːtɪk/, may-YOO-tik)*: the Socratic art of drawing knowledge out of a learner rather than pouring it in; "midwifery of ideas." It's the method this system runs on.

*A vault manager and learning partner that lives in your Obsidian vault. It teaches through narrative-Socratic dialogue, enforces retrieval practice and spaced review, and helps you build a connected, durable knowledge graph. All grounded in learning science.*

---

## What this is

This repository is an **Obsidian vault** plus a set of **skill files**. Point an AI coding agent (Claude Code, or any capable agent. See `AGENTS.md`) at the vault and it becomes a disciplined learning partner:

- It **teaches new concepts** by building a problem, voicing a historical thinker, and stopping at the cliffhanger so *you* attempt the leap (narrative-Socratic method).
- It **refuses to let you fool yourself**: you retrieve before you reveal, you teach-back from memory, and it scores you against atomic facts using objective signals.
- It **schedules spaced reviews** automatically (+1, +6, +14 days from completion) and tracks calibration (the gap between how much you *think* you know and how much you actually retrieve).
- It helps you **connect ideas** into a knowledge graph and, once a month, runs a maintenance meeting (schema audits, back-link descriptions, spring cleaning).

It is **not** a note-taking app or a chatbot. It's an accountability layer that makes the effortful parts of learning unavoidable.

## Why it works (the foundations)

The behavior is built on established learning science (full syntheses in `.claude/Foundations/`, with an accessible source library in `resources/Learning Science/`):

- **Retrieval practice & the testing effect**: recalling beats rereading.
- **Spaced repetition**: intervals computed from when you *actually* complete a review.
- **The generation effect & desirable difficulties**: you generate before the vault stores; productive struggle is the mechanism, not the cost.
- **Metacognitive calibration**: the fluency illusion is detected with objective signals, never self-report.
- **Narrative-Socratic teaching**: narrative builds the problem space; Socratic questions drive the generation; the two are interwoven, never segmented.
- **Schema-building & transfer**: concepts connect into maps; an Analogy Gate pushes cross-domain transfer.

## How it works (modes)

| Mode | What happens |
|---|---|
| **Learning Pipeline** | Prepare (narrative + pretest) → Attempt → Consolidate (Socratic through a character) → a natural stopping point → optional Note Creation (scope → teach-back → score → file). |
| **Note Creation** | A standalone, user-triggered procedure: scope conversation, plain-language scoring, and a `Leads` section that points one step ahead. |
| **Spaced Review** | Surfaces what's due, asks for a confidence estimate first, scores the teach-back, and reschedules. |
| **Discussion Mode** | A peer-to-peer dynamic: the AI thinks out loud and holds real positions, shaped by the active intellectual **profile**. |
| **Monthly Meeting** | Reflection → schema work → back-link descriptions (spaced retrieval for *connections*) → spring cleaning → profile review. |

## Map

```
CLAUDE.md            # Entry point for Claude Code (full operating instructions)
AGENTS.md            # Entry point for any other AI agent
LICENSE              # MIT
.claude/
  skills/            # The behavioral spec: pkm-principles, monthly-meeting, tutorial-mode, Schema-Mapping
  Foundations/       # 5 research syntheses + an index (read per-mode)
  Transcripts/       # Exemplar teaching transcripts (read on demand) + index
  Profiles/          # Profile-1: the default intellectual profile for Discussion Mode
  Characters/        # Historical characters (created as you learn)
  GOALS.md           # Your learning goals (off by default)
resources/
  Learning Science/  # A starter source library; add your own
00 - Inbox/ · 01 - Journal/ · 02 - Notes/ · 03 - Schemas/   # Your vault
.note-information/   # Review tracker, atomic facts, schedule (AI-maintained)
Templates/
```

## Quickstart

1. **Clone** this repo and open the folder as a vault in [Obsidian](https://obsidian.md).
2. **Choose your agent.** For Claude Code, just run it in the vault: it reads `CLAUDE.md` automatically. For another agent, point it at `AGENTS.md`.
3. **Start a session.** The agent confirms the date, reads the system files, and runs the morning ritual. Say *"I want to learn X"* to start the pipeline, or *"let's discuss X"* for Discussion Mode.
4. **(Optional) Set goals.** Edit `.claude/GOALS.md` and set `enabled: true`.
5. **(Optional) Add source libraries** to `resources/` in the format shown in `resources/Learning Science/`.
6.  **(Optional) Optimal setup** I run the system in VS code with Claude Code chatting open on half my screen and Obsidian with my notes open on the other.

A guided in-product walkthrough is available: keep `tutorial-mode14.0.md` in `.claude/skills/` (delete it to turn tutorial narration off).

## Customization

- **Profiles** (`.claude/Profiles/`): the shipped `Profile-1` is a neutral, learning-science-grounded default. Create your own (`Profile-2`, …) and `load` / `activate` them; they shape Discussion Mode.
- **Schema notation** (`.claude/skills/Schema-Mapping.md`): a swappable, deletable module: swap it for your own mapping system, or delete it to map notationlessly (relationships described in plain language).
- **Libraries** (`resources/`): free-form, but every source carries `[CLAUDE]` / `[MARKDOWN]` / `[NOTEBOOKLM]` accessibility labels.

## Notes

- The Foundations files are AI-assisted research syntheses; a few sources in the library are marked for verification.
- **AI disclosure:** this system and its research materials were built with AI-assisted tools.

## License

MIT: see [`LICENSE`](LICENSE).
