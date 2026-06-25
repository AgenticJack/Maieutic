<%*
// Templater script — runs when you create an inbox capture from this template.
// This is the FAST-CAPTURE template for 00 - Inbox/, not a concept note.
// Concept notes are built by the AI through the learning pipeline — see
// "Concept Note Template.md" for their shape.
const title = await tp.system.prompt("Note title:");
tR += `---
date: ${tp.date.now("YYYY-MM-DD")}
last-modified: ${tp.date.now("YYYY-MM-DD")}
type: inbox
tags: []
---

## ${title}

[Write your capture here — a thought, a link, something to learn later.
The AI processes inbox items at session start or during the monthly meeting:
keep, schedule a learning session, move to resources/, or delete.]

`;
%>
