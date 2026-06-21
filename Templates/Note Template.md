<%*
// Templater script — runs when you create a note from this template
const title = await tp.system.prompt("Note title:");
tR += `---
date: ${tp.date.now("YYYY-MM-DD")}
last-modified: ${tp.date.now("YYYY-MM-DD")}
cognitive-state: generative
expertise: novice
type: inbox
tags: []
links-to:
---

## ${title}

[Write your information here.]

`;
%>

---