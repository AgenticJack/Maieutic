# Learning Goals (Template)

The live file is `.claude/GOALS.md`. Goals are the one part of the system you write
by hand: the AI reads them but never invents them for you. The file is hidden in
Obsidian by design, so edit it directly (e.g. in VS Code).

When `enabled: true`, the AI uses it in two ways:
1. After the morning ritual, if you have no specific direction, it suggests a focus
   from your goals (preferring an open Lead in an active goal's domain, then the next
   sub-goal of your Primary goal).
2. During note work, it flags when a note connects to one of your goals.

Set `enabled: false` to switch all of that off.

---

## Format

```
---
enabled: true
---

# Learning Goals

## Current Goals

### Primary
- [Goal] | library: [resources/Subfolder/Some-Library.md]
  - Sub-goal: [a concrete piece or milestone of the goal]
  - Sub-goal: [another piece]
  - Note: [optional context: why it matters or how you want to approach it]

### Secondary
- [Goal] | library: [resources/...]
  - Sub-goal: [...]

## Abandoned
- [Goal] (optional reason / date)
```

### The pieces
- **`enabled:`** (frontmatter): `true` lets the AI read and suggest from this file; `false` keeps startup quiet.
- **Primary vs. Secondary**: Primary is your current focus and is suggested first; Secondary is lower-priority background. Keep Primary short (one or two goals).
- **Sub-goals**: indented bullets that break a goal into concrete pieces or milestones. The AI can suggest the *next* sub-goal as a specific session focus, which is usually more useful than the broad goal.
- **`| library:`**: ties a goal to a source library in `resources/`. When that goal is active, the AI checks the named library for sources before a session begins. The path is relative to `resources/`.
- **`Note:`**: optional context the AI treats as a binding instruction about how you want to approach the goal.
- **Abandoned**: dropped goals; kept as background context but never actively suggested.

### Editing
- Change any goal text directly; the AI picks it up next session.
- Add or remove sub-goals freely as you make progress.
- Move a finished or dropped goal to **Abandoned** (add a short reason if you like).
- The AI makes one suggestion per session: it won't flood you with ideas.
