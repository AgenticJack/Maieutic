# AGENTS.md

Operating instructions for **any** AI agent running this vault.

This is **Maieutic**, a **PKM (Personal Knowledge Management) system** — an Obsidian markdown vault run by an AI coding agent (Claude Code, Codex, Cursor, Copilot, Aider, or any capable agent with file access). It turns your AI into a learning partner that teaches through narrative-Socratic dialogue, enforces retrieval practice and spaced review, and helps you build a connected, durable knowledge graph grounded in learning science.

## Start here
Your complete operating instructions live in:
1. **`CLAUDE.md`** (repo root) — read it in full first. It defines session startup, the vault structure, file formats, and which skills to load.
2. **`.claude/skills/`** — the behavioral skill files CLAUDE.md points to (`pkm-principles14.0.md` is the core; plus `monthly-meeting-skill`, `tutorial-mode`, `Schema-Mapping`).
3. **`.claude/Foundations/Foundations-Index.md`** — the research base (read per-mode, not at startup).

Follow CLAUDE.md's **Session Startup** sequence exactly. The instructions address "Claude" / "Claude Code" — **that means you**, whichever agent you are. Everything is plain markdown; no Claude-specific APIs are required.

## Compatibility
| What the agent needs | Why |
|---|---|
| Read/write files in the vault | create & update notes, trackers, profiles |
| Follow multi-step markdown instructions | the skills are instruction files |
| Web fetch (optional) | reading `[CLAUDE]`-tagged library sources directly |
| A task/checklist tool (optional) | the completion-checklist discipline — any inline list works |

Agents without a built-in task tool: use a plain inline checklist wherever the skills say "via TodoWrite where available."

## Claude Code users
Claude Code reads `CLAUDE.md` automatically — you can ignore this file. `AGENTS.md` exists only so non-Claude agents have a standard entry point.
