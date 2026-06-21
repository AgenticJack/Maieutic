# Note Facts Template

The live file is `.note-information/note-facts.md` (the AI creates and maintains it).
One entry per active note. The per-fact outcome marks are a backend record for
pattern-weakness detection — never shown to the user.

```
# Note Facts
Last updated: [DATE]

---[NOTE TITLE]---
File: [path to the note]
Generated: [date]
Total facts: [N]

Facts:
1. [atomic fact] — TB:✓ · R1:✗ · R2:✓
2. [atomic fact] — TB:✓ · R1:✓
[Keyword] [weight:1] [term] — TB:✗ · R1:✓
```

Marks: `✓` present · `✗` missing · `!` incorrect. `[Keyword]` rows track vocabulary
terms scored separately from the conceptual atomic facts.
