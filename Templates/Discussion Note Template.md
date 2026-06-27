# Discussion Note Template

Created at the end of a Discussion Mode session (after the SYNTHESIS state). Lives in
`02 - Notes/Discussions/` (`type: discussion`). Unlike concept notes: no atomic facts,
no review schedule, no teach-back — it can stay `generative` indefinitely.

**Frontmatter is YAML — keep it to clean, queryable scalars.** Do NOT put free prose
(colons, quotes, parentheses, brackets, `#`, em-dashes, semicolons) into frontmatter
fields, and never into inline `[...]` lists — that is what makes a third of these notes
render all-red in Obsidian. The rich content (topic framing, positions, open questions,
resolution) lives in the **body**, where prose is safe. See "Frontmatter safety" below.

```
---
date: [DATE]
last-modified: [DATE]
type: discussion
cognitive-state: generative
discussion-mode: [open-inquiry | steelman | productive-disagreement | speculative]
trigger: [situation-a | situation-b | situation-c]
topic: [SHORT plain-text label — a few words, NO colons/quotes/brackets/dashes; the full framing goes in ## The Question]
resolution: [resolved | partial | open]
continues:
  - "[[Prior Note Title]]"
related:
  - "[[Related Note Title]]"
session-source: "path/to/scratch.md"
---
## [TOPIC] — [DATE]
## The Question              [the full framing, with all its nuance — prose lives here, not in frontmatter]
## Positions and Reasoning   [positions taken and why — this replaces the old positions-held field]
## Considerations Map        [the strongest considerations on each side]
## What Shifted              [any positions updated during the session, and what changed them]
## What Remains Open         [the open questions — this replaces the old open-questions field]
## Resolution                [what was settled, if anything — the prose the old resolution field tried to hold]
## Next Moves

> [!ai-generated] AI — [DATE]
> [Honest assessment of where the strongest arguments lie — marked as AI perspective.]
```

## Frontmatter safety (why this template changed)

YAML frontmatter is parsed strictly. These break it:
- **Inline lists `[ ... ]`** containing prose. `[a: b, "x" is y, (z)]` is invalid YAML.
  The `"` opens a quoted scalar; the `:` reads as a mapping; `[` `]` nest. One stray
  character turns the whole block red. **Don't use inline lists for prose.**
- **Unquoted wikilinks.** `related: [[Note]]` is a nested flow sequence and errors.
  Always quote them and use block style:
  ```
  related:
    - "[[Note A]]"
    - "[[Note B]]"
  ```
- **Bare values with `:` , `#`, or leading `[`/`{`/`"`/`*`/`&`.** If a scalar must hold
  one of these, wrap the whole value in double quotes — but prefer moving prose to the body.

Rule of thumb: frontmatter = short scalars and enums you might query (`type`,
`discussion-mode`, `trigger`, `resolution` status) plus quoted wikilink lists.
Everything a human would read as a sentence goes in the note body.
