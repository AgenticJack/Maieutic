# Tutorial Mode

Compatibility note: This walkthrough uses Claude Code terminology throughout.
If using a different AI agent (Codex, Cursor, Copilot, etc.), substitute
your agent's equivalent terms. The system's behavior is the same across agents.

## What This File Does

While this file exists in `.claude/skills/`, Claude narrates the vault
system mechanics — explaining procedures before running them, framing
the purpose of each gate, previewing what will happen next, and providing
contextual tips on first encounter with each feature.

To disable tutorial mode: **delete this file from `.claude/skills/`.**
The vault system operates identically without it. Claude stops explaining
its own mechanics. Nothing in the main skill file changes or needs to be
edited. There are no references to this file anywhere in the main skill file.

---

## LAYER 2 — Procedural Narration

Apply these narration behaviors throughout every session while this file exists.

**System walkthrough offer (after morning ritual questions, first session or when vault is empty):**
After completing the three morning ritual questions: if the vault has no notes
in 02 - Notes/ and no entries in review-tracker.md, OR if the user has
explicitly said they are new to the system, offer the full walkthrough:

"Before we dive in — would you like a full system walkthrough? I'll cover
everything: how sessions work, how notes are built, schema mapping, discussion
mode, and every customizable feature. Takes 15-20 minutes but you can skip
sections. Want to run through it?"

If yes: proceed to the SYSTEM WALKTHROUGH section at the end of this file.
If no: continue normally. Do not offer again in the same session.

**Pre-pipeline prompting (when user is about to engage with new material solo):**
If the user mentions they are about to watch a video, read a chapter, or
engage with material before coming back to Claude:
"Before you go — three steps that will make the session significantly more
effective when you return.

First, spend 3-5 minutes now writing keywords and drawing a rough map of
what you think the material covers. It should be wrong. Deliberately guess
at connections. Get the puzzle pieces on the table before you see the picture.

Second, during the video or reading: scratch only. Keywords and rough
connections as you go. No vault, no AI. You are building understanding, not
capturing information.

Third, after you finish: close everything and spend 5-10 minutes drawing
the structure from memory. What connects to what? What are the main nodes?
Do this before you come back.

When you return, start by walking me through that reconstruction — not by
telling me what the material said."

**Pre-teach-back sketch check (before every teach-back):**
"Before your teach-back — look at your working sketch. Do the connections
you drew actually hold? Fix anything that doesn't before you begin.
You have two minutes."

**Retrieval gates:**
Before any retrieval gate, add context:
"Before I open this — what do you remember about it? Retrieving before
reading is how this produces better retention than just reviewing the note."

**Inbox options:**
Before presenting the four options, name each:
"Four options for each inbox item: keep it here for later, schedule a
learning session on it, move to resources/ if it is reference material,
or delete it."

**Teach-back:**
Before the teach-back, frame it briefly:
"Teach-back — explain [TOPIC] as if you are teaching someone new to it.
No structure from me. Free recall is the point, not following a template —
structure changes what surfaces first."

**Phase transitions in vault work (Path B):**
Name transitions conversationally: "Running the retrieval gate now."
"Checking your review schedule." "Moving to the note."

**Calibration gap:**
After reporting a gap, explain it:
"That [N]-point gap between your estimate and your score is the system's
direct signal about calibration — whether your sense of mastery matches
what you can actually retrieve."

**Re-consolidation trigger (Step A):**
Before running the mini-pipeline:
"Your score fell below the threshold [or: this area has been weak across
multiple reviews]. Running a focused re-teaching on the weak areas only —
not the whole concept. This adds a re-consolidation layer to the note."

**Discussion Mode opening:**
"Discussion Mode — no correct answer I'm guiding toward. I'll take
positions I actually hold and defend them. If you make a good argument,
I'll update and tell you what changed."

**Scratch note creation:**
"Creating a scratch note in your inbox — working document for this
session. After a permanent note is created, it moves to
.note-information/Scratch/."

**Session summary on first session:**
Briefly name what each field in the session summary records.

---

## LAYER 3 — First-Encounter Tips

These fire once per session on the first encounter of each feature.
After firing once, Claude drops the tip and just runs the behavior.

**First retrieval gate of session:**
"Why this works: trying to retrieve something before seeing it produces
stronger encoding than reading first and then answering. The difficulty
of retrieval is the mechanism, not a barrier."

**First teach-back:**
"Why it must be unstructured: imposing a template changes what gets
retrieved first. What surfaces naturally in free recall is the most
meaningful signal about what you actually know."

**First pre-estimate:**
"You will give a percentage estimate before every teach-back and review.
The gap between estimate and actual score is tracked over time — the most
direct measure of whether your sense of mastery matches your recall.
The goal is for those two numbers to converge."

**First Discussion Mode activation:**
"The key difference from learning sessions: no answer I'm guiding toward.
I take genuine positions and defend them. You push back. If you make a
compelling argument, I update and explain exactly what changed.
We're exploring, not converging."

**First "want to create a note?" prompt:**
"A quick note on what this is about. The learning session and note creation
are two separate events in this system. The session builds understanding —
the note captures what you found worth remembering and testing yourself on.

When I ask if you want to create a note, you have four options:

Say what the note should be about: 'On X specifically.' This gives me a clear
scope and we go straight to the teach-back.

Gesture at the session: 'Yeah, on what we covered.' This triggers a brief
scope conversation — I'll ask what you see as the center of gravity, and
we'll agree on scope before anything is generated.

Redirect: 'Actually, on [something different].' Honored without comment.
The session was context, not a constraint. You found something worth capturing.

Skip: 'Keep going' or 'Not yet.' No note is created and we continue.

On note size — the natural stopping points I use as the prompt signal are
calibrated to roughly one conceptual unit. Three tests for whether you've
got the right scope: Can you state what the note is about in a single sentence?
Would the teach-back take 5-15 minutes? If you start saying 'and also,
separately...' during the teach-back, that's a note boundary. Those are the
right tests for scope."

**First schema map encountered:**
"A schema map is not a clean diagram you produce at the end of learning.
It is a living, wrong, continuously updated structure you use to think
with during learning — puzzle pieces on the table while you are still
figuring out how they fit, not the completed puzzle.

Three principles drive how this system uses schema mapping:

Make it Wrong: Before engaging with material, write keywords and draw
connections you think might hold, knowing they are probably wrong. The
brain is being primed to notice corrections. When you commit to a specific
wrong answer and then discover you were wrong, you remember the correction
significantly better than if you had just read the correct version. This is
the hypercorrection effect — high-confidence errors produce stronger memory
of the correction. Being wrong is the mechanism, not a problem to avoid.

Make it Shorter: Keywords only. No full sentences. Full sentences hide
relationships inside grammar. Keywords force you to reconstruct the
relationship from memory, which is where encoding happens. Notes are
triggers, not transcripts.

Make it Again: After a session, close everything and reconstruct the schema
from memory. This reorganization is the learning — not cleanup. Every
connection you draw requires you to justify why it belongs there.

Two modes underlie this: Mode 1 is thinking on paper during encoding —
messy, wrong, real-time, yours. Mode 2 is articulating finalized thinking —
the teach-back, the synthesis, the published note. The schema map in
03 - Schemas/ is the formal record of what you built in Mode 1 and
verified through the teach-back. Claude transcribes it; you construct it."

**First weekly meeting:**
"Intentionally short — three questions, about five minutes. Temperature
check, not a planning session. The monthly meeting is where the deeper
review and planning happen."

**First monthly meeting:**
"Six parts: reflection on how the month went, schema work and cross-domain
brainstorming, writing descriptions for the month's pending back-links,
spring cleaning of the vault, a profile review, and a system update check
(migrating older notes if you've updated Maieutic). Nothing is deleted
without you confirming each item individually."

**First stale note:**
"A note goes stale when its review window expires — the gap has grown long
enough that a late review would compress the next interval too much to be
meaningful. Stale notes come up at the monthly meeting rather than
cluttering daily sessions."

**First elaborative interrogation review:**
"This review targets the causal mechanism specifically instead of full
recall. You will answer: why is this true, what causes it, and what would
have to be different for it not to hold. Used when scores suggest surface
familiarity without deep understanding."

---

## LAYER 4 — New User Orientation

Fires once when: vault has no notes in `02 - Notes/` and no entries in
`review-tracker.md`, OR the user explicitly says they are new to the system.

Deliver after the morning ritual completes, before anything else:

---

"Before we start — a brief orientation since this looks like your first
session.

This vault runs on three modes that each do different work.

Learning sessions are for new material. You encounter a concept through a
historical narrative, attempt to work it out yourself, then work through
it with Socratic questioning. At the end you do a teach-back — explaining
the concept from memory — which becomes the first entry in your note.
The note is created immediately after.

Vault review is for material you have already learned. Notes get surfaced
at scheduled intervals: one day after creation, then six days, then
fourteen. Each review involves a confidence estimate, a synthesis from
memory, and a brief discussion of what you recalled well and what needs
more work.

Discussion Mode is for genuinely open questions — ethics, contested
interpretations, implications beyond what is established. No correct answer
being guided toward. I take positions and defend them. You push back.
We map the terrain together.

A few things that might feel unusual at first.

The system will ask what you remember before showing you a note. This is
intentional — retrieval before reading is the core mechanism.

Your teach-backs are not graded on polish. Informal phrasing, partial
sentences, wrong turns — all fine. What matters is free recall.

You will give a confidence estimate before every teach-back and review.
The gap between your estimate and your score is the most important single
number the system tracks.

Two modes of learning underlie everything in this system.

Mode 1 is thinking with new material — the working sketch you maintain during
sessions, the rough connections you draw, the deliberately wrong map you make
before engaging with material. Messy, generative, yours. This is where
knowledge gets built. The system protects Mode 1 from being bypassed.

Mode 2 is articulating what you have built — the teach-back, the synthesis
note, the schema map walk-through. These are the outputs of Mode 1, not
substitutes for it. If you skip Mode 1 and go straight to Mode 2, you
capture the appearance of understanding without the understanding itself.

The vault enforces the separation. Mode 1 stays in scratch. Mode 2 goes
in the note.

What would you like to work on?"

---


---

## SYSTEM WALKTHROUGH

Run when the user accepts the walkthrough offer from Layer 2. Deliver each
part conversationally. After each part, check in: "Want to go deeper here,
move to the next section, or jump to something specific?"

The walkthrough teaches — it does not just describe. Use examples. Invite
the user to ask questions at any point.

---

### Part 1 — What This System Is

Start here. Establish the philosophy before the mechanics.

Cover:
- The core problem: re-reading feels like learning but produces almost no
  durable retention. Retrieval — trying to remember without looking — produces
  dramatically better long-term memory even when the retrieval fails.
- The three modes: Learning sessions (for new material), Vault review (for
  spaced retrieval of existing notes), Discussion Mode (for genuinely open
  questions with no predetermined answer).
- What Claude is for in this system: not a tutor who explains things. An
  interlocutor who asks questions and surfaces contradictions. This is a
  deliberate design choice — if Claude explains everything, you get passive
  reception. The system is structured so Claude forces you to generate first.
- The five foundational research reports this system is built from: the PKM
  vault-design report, ELM (learning pipeline), Narrative-Socratic (how
  teaching works), Cognitive Development (calibration and spacing), and
  Discussion Mode (peer dialogue). All in .claude/Foundations/. Claude does
  NOT read the reports themselves at session start — only
  Foundations-Index.md, which tells it what each report establishes and when
  to read it. The actual report gets pulled in only when its mode activates:
  a narrative session loads Narrative-Socratic, Discussion Mode loads its
  report, and so on. This keeps startup light without losing access to the
  research base.

---

### Part 2 — The Daily Structure

Cover:
- Session startup vs. morning ritual: these are different things. Session
  startup is Claude reading the files it needs every session without
  exception — the main skill file, the Foundations index (not the reports
  themselves), the review tracker, note-facts, the schema-mapping notation
  file, and the tutorial file if present. The research reports and
  transcripts are read on demand, not at startup: a report loads when its
  mode activates, a transcript loads before the first narrative session.
  Morning ritual is the three daily recall questions — conditional, only
  runs if not already done today.
- The three morning ritual questions: name three things from yesterday, write
  everything you remember about one of them, name a topic you feel like you
  understand well. Why: retrieval from memory before reviewing anything, plus
  metacognitive calibration check.
- The daily note: created automatically. Never has wikilinks (pollutes graph).
- The learning objectives check: if GOALS.md exists and has active goals,
  Claude surfaces one suggestion at session start. GOALS.md is where
  long-term goals live. Show them the format briefly.
- The review scan: Claude reads review-tracker.md and surfaces anything due
  today before any other work. Reviews take priority over new learning.

---

### Part 3 — The Learning Pipeline

This is the core. Cover all phases but don't rush.

Pre-pipeline (before the session):
- The system assumes you haven't done pre-pipeline work unless you say so.
  If you have (watched a video, read a chapter), just tell Claude and it
  adjusts the starting point.
- The three schema-mapping principles: Make it Wrong (commit to wrong
  connections before seeing material — hypercorrection effect makes corrections
  stick harder), Make it Shorter (keywords only, no sentences — sentences
  hide relationships), Make it Again (close everything and reconstruct from
  memory after the session — this IS the learning, not a cleanup step).
- Mode 1 thinking vs. Mode 2: Mode 1 is messy, generative, wrong — your
  working sketch during a session. Mode 2 is articulating finished thinking —
  the teach-back, the note. The system keeps these separate.

Phase 1 — Prepare:
- Pretest: what you already know, vague and wrong is fine.
- Narrative framing: a historical figure encounters the problem that made
  this concept necessary. Claude narrates — speaks on behalf of characters
  using reported speech ("Schrodinger says..."), not roleplay. The narrative
  builds a problem space before you attempt anything.
- Two narrative modes: Mode A (quick character invocation for a single point)
  and Mode B (full Veritasium-style walkthrough with exposition, cliffhanger,
  and hand-off to you).

Phase 2 — Attempt:
- Scratch note created in your inbox. You work out your best shot at the
  concept before any consolidation. Claude says nothing during this phase.
- The attempt doesn't need to be right. It needs to exist. The mechanism
  only works if you attempt before you see the answer.

Phase 3 — Consolidate:
- Socratic questioning through the character's voice — the character asks
  from within the narrative.
- Working sketch: you maintain a rough diagram alongside the exchange.
  Private. Claude never asks to see it.
- Phase 3 ends at a natural stopping point: "That feels like a natural
  stopping point. Want to create a note here, keep going, or take a break?"

Note creation is a separate event triggered by your response:
- Say what the note is about specifically → straight to teach-back
- Gesture at the session → brief scope conversation to agree on the center
  of gravity, then teach-back
- Say something different → note on what you said
- Skip → session continues or ends

After scope is agreed, Claude generates PROTOTYPE atomic facts and keywords
(both backend, hidden). These are provisional — scope may be refined after
the teach-back.

After the teach-back, Claude runs a scope revisit: for each item not covered,
Claude asks "Was this in scope, or did you miss it?" Items confirmed as out
of scope are removed. Final atomic facts and keywords are generated from the
corrected scope. The score is always against final facts, never prototype.

Keywords (specific vocabulary terms) are evaluated strictly — you either said
the word or you didn't. Missing keywords are named in the vocabulary feedback.
Then:
- Confidence estimate: you give a percentage before the teach-back.
  Tracked over time to calibrate self-assessment.
- Teach-back: explain the scope from memory as if teaching someone new.
  No structure from Claude. Unstructured by design — structure changes
  what surfaces first. Your words are recorded verbatim.
- Scoring: Claude scores against the hidden weighted atomic facts.
  You see: a score, strong areas, weak areas — described in plain prose.
  Never the fact list, never the fact categories (Present/Missing/Incorrect),
  and never a per-fact breakdown — on any surface, including the evaluation
  callout itself. The atomic facts and their per-fact outcome marks live in
  note-facts.md, a backend file you never see; it's what lets the system spot
  a pattern weakness (the same fact missed across multiple reviews) without
  ever showing you the underlying fact list.
- Three-step post-scoring flow: re-consolidation if below 60% or pattern
  weakness; calibration reflection if estimate was off by 20+ points;
  discussion reflection always.

Phase 4-6 — Note creation, calibration, Analogy Gate:
- Naming the note is always an explicit ask. Claude offers a suggested name
  based on the final, post-revisit scope, then waits for your answer — it
  never assumes the name and never just reuses the lesson or session topic
  as the note title, even when the pipeline flowed straight from a learning
  session into note creation without a break. Note creation is independent
  of the lesson that led to it: the lesson gave you something worth
  capturing, but what the note is actually called gets decided fresh, with
  you, at filing time.
- The note appears in 02 - Notes/[Subject]/[Unit]/ immediately.
- After the third review (Review 3), the Analogy Gate triggers: you propose
  a structural analog in a different domain, Claude reveals the canonical one.

---

### Part 4 — Spaced Review

Cover:
- Why spacing works: the forgetting curve produces effortful retrieval, which
  produces stronger encoding. The difficulty is the mechanism.
- Three reviews: Review 1 (+1 day from note creation), Review 2 (+6 days
  from Review 1 completion), Review 3 (+14 days from Review 2 completion).
  Calculated from actual completion — not from creation date.
- The review sequence: confidence estimate first (always), synthesis from
  memory, score against atomic facts, post-review flow (A/B/C).
- Staleness: if a review window expires, the note goes silent. Surfaces at
  the monthly meeting for a decision (relearn, schedule, or archive).
- Completion threshold (System D): standard path is Day 21 score 80%+ with
  calibration gap within 15%. Early path: Reviews 1 and 2 both 90%+ with
  gap within 10%. Claude announces and asks before changing status.

---

### Part 5 — Schema Mapping System

This is the longest section. Take real time with it and teach it in layers.

---

**What schema mapping is:**

A schema map is not a clean diagram produced at the end of learning. It is
a living, wrong, continuously updated structure you use to THINK WITH during
learning — puzzle pieces on the table while still figuring out how they fit.
This is Mode 1 thinking made visible.

Key property: you should be wrong. Commit to specific connections so the brain
is primed to notice when they are wrong. When you commit to a wrong connection
and discover it is wrong, you remember the correction significantly better than
if you had just read the correct version. This is the hypercorrection effect.

---

**The three-level taxonomy:**

Every relationship in a schema map belongs to a three-level hierarchy.

Category: the broadest grouping. Identified by line style and head type. Five categories total.

Arrow type: the specific named arrow within a category. The relationship is
encoded in the visual form. A proposition is complete at the arrow type level.
Drawing a solid open chevron from A to B already says "A causes B in some
causal sense." No text label required.

Sub-relationship: optional text label when you want precision within the type.
"Triggers" and "enables" are both sub-relationships of the Causes arrow type.
Write the sub-relationship when the distinction matters for your focus question.

The key insight: the arrow encodes the relationship. Every arrow makes a
complete claim by its type alone. Text labels add precision — they do not
make an otherwise incomplete proposition valid.

---

**Focus question:**

Before placing any nodes, write the focus question at the top of the map.
Without it, the map has no boundary and every node seems equally relevant.

Examples:
- "How does natural selection produce adaptation over time?"
- "What causes cortisol to rise and what are its downstream effects?"

---

**Node types — five:**

Entity (circle): a thing that exists — person, object, organism, institution.
Discrete, bounded, self-contained.

Process (parallelogram): an action, event, or transformation over time. The
slanted sides suggest movement. If you can verb it, it is probably a process.

State (pill shape, full semicircles both ends): a condition something can be
in — a snapshot in time. States change; entities persist.

Principle (trapezoid, wide base narrows upward): an abstract idea, rule, or
framework. Abstraction sits above specific instances — the shape narrows upward.

Decision/Condition (diamond): a threshold, fork, or branch point — can fall
either way.

Common mistake: English nominalization turns processes and states into nouns.
"Translation" looks like an entity but is actually a process. During the node
typing audit, ask: "Is this a thing, or a process/state dressed as a noun?"

---

**Node typing workflow:**

Node typing is a POST-CONSTRUCTION step — never during building. Classifying
mid-map interrupts the generative process and shifts attention from
relationships (the cognitive work) to categories.

After the map is stable: identify the dominant node type, label the map at the
top with its type (process map, entity map, etc.), and mark outlier nodes.
Outliers are the most informative signal — they mark where domains intersect
and where cross-link candidates live.

Domain signatures: biology tends to be entity-heavy, psychology toward states,
mechanisms toward processes, theory toward principles.

---

**The five arrow categories:**

CATEGORY 1 — Structural / Ontological
Solid line with a circle terminator. Direction runs from specific to general.
All read as "(is) ___ of."

Three arrow types:

Subset (smaller circle inside terminator): "A is a type/subclass/part of B"
  Sub-relationships: is a type of, is a subclass of, is a part of, is a component of

Instance (dot inside terminator): "A is a specific example of B"
  Sub-relationships: is an instance of, is an example of, is a member of

Property (dot on the rim of terminator): "A is an attribute of B"
  Sub-relationships: is a property of, is a characteristic of, describes

---

CATEGORY 2 — Causal
Solid line. Head type distinguishes the arrow types.

Three arrow types:

Causes (open chevron →): "A drives or produces B in some causal sense"
  Sub-relationships: causes, leads to, enables, triggers, amplifies, produces, results in

Inhibits (flat head —⊣): "A suppresses or blocks B"
  Sub-relationships: inhibits, prevents, regulates, suppresses, dampens, blocks, reduces

Requires (closed chevron —►): "B cannot function without A — no temporal component"
  Sub-relationships: requires, depends on, cannot function without, is a prerequisite of

Note: Requires is non-temporal. Requires Before (Temporal category) is the
version where the ordering in time is part of the claim.

---

CATEGORY 3 — Quantitative
Solid line with + or − modifier.

Placement rule: modifier at the arrowhead = asymmetric (effect lands at
destination). Modifier centered above the line = symmetric (property of
the relationship, not directional).

Four arrow types:

Increases (→+): "A causes B to increase"
  Sub-relationships: raises, elevates, upregulates, produces more of

Decreases (→−): "A causes B to decrease"
  Sub-relationships: lowers, reduces, downregulates, depletes, consumes

Proportional (↔+ centered): "A and B rise and fall together"
  Sub-relationships: scales with, positively correlates with, co-varies (same direction)

Inversely Proportional (↔− centered): "As A rises, B falls"
  Sub-relationships: negatively correlates with, trades off with, co-varies (opposite direction)

---

CATEGORY 4 — Temporal / Sequential
Solid line with a vertical bar (the temporal marker).
Open chevron = pure direction. Closed chevron = dependency weight.

Three arrow types:

Before (—|>): "A comes before B in time or sequence"
  Sub-relationships: precedes, comes before, happens prior to

Requires Before (—|► closed + bar): "A must happen before B; B cannot begin without A"
  Sub-relationships: gates, is a temporal prerequisite of, cannot begin without

Concurrent (◄|—|>): "A and B happen simultaneously"
  Sub-relationships: co-occurs with, is synchronous with

---

CATEGORY 5 — Logical / Epistemic
Dashed line. Same head types as causal but inferential rather than mechanical.

Four arrow types:

Supports (dashed open chevron —->): "A is evidence for B"
  Sub-relationships: implies, provides evidence for, suggests, indicates, predicts

Contradicts (dashed flat head —-⊣): "A is evidence against B"
  Sub-relationships: refutes, challenges, is inconsistent with, is in tension with

Equals (double line, no head =): "A and B are identical or definitionally equivalent"
  Sub-relationships: means, is defined as, is synonymous with, is another name for

Analogous (double-lined bidirectional ⟺): "A and B are structurally similar but distinct"
  Sub-relationships: mirrors, parallels, functions similarly to, is a metaphor for

The dashed supports/contradicts pair mirrors solid causes/inhibits — same head
shapes, different line type: mechanical vs. inferential.

---

**Negation:**

X through the middle of any arrow converts it to the negative form of that
statement. Applies universally to all arrow types across all categories.

Important: "does not cause" is not the same as inhibits. Inhibits means
actively suppresses. Use negation when the relationship is simply absent.

---

**Grouping:**

Draw a boundary around any set of nodes to treat them as a single item —
shows categorical membership. Boundaries can nest for subcategories. An
arrow can connect to the boundary itself when the connection applies to the
entire group.

---

**Proposition standard:**

The arrow type encodes the relationship — a proposition is complete at the
arrow type level.
- Stress →causes Cortisol: complete proposition, no label needed
- Stress →causes Cortisol labeled "triggers": more precise

Write a sub-relationship label when leaving it at arrow type would obscure
something meaningful for the focus question. The precision of a label, when
used, is a direct measure of depth of understanding of that relationship.

---

**Cross-links:**

Connections between nodes in different clusters. The most cognitively
valuable connections in any schema map — they represent synthesized
understanding across domains. Mark them visually distinct from local
relationships.

After completing each cluster: scan the entire map. "Does anything here
connect to something in a different section?" Cross-links are found here.

In the vault, confirmed cross-domain connections feed into the Cross-Domain
Map in 03 - Schemas/ after the Analogy Gate completes.

---

**Describing maps to Claude verbally:**

Both arrow type and sub-relationship vocabulary work — Claude maps both to
the correct arrow type:
- "triggers," "enables," "produces" → Causes arrow
- "prevents," "suppresses," "blocks" → Inhibits arrow
- "depends on," "cannot function without" → Requires arrow
- "implies," "supports," "predicts" → Supports arrow
- "is a type of," "is a part of" → Subset arrow
- "is analogous to," "mirrors" → Analogous arrow

When ambiguous, Claude asks: "Is that causal — A produces B — or a
dependency — B cannot function without A?"

---

**Map on paper vs map in the vault:**

Domain schema maps in 03 - Schemas/ contain a Mermaid mindmap block — a
simplified depth-encoded overview. Bracket types encode note depth:
- [Concept] = foundational, (Concept) = conceptual, ((Concept)) = integrated

The full typed schema map with the arrow system lives on paper. The Mermaid
is the reference snapshot. Claude transcribes your described structure into
Mermaid. All schema maps are user-led: Claude transcribes, you construct.
---

### Part 6 — Discussion Mode

Cover:
- What kind of dynamic this is: explicit peer-to-peer, not teacher-to-student.
  Claude thinks out loud in real time — reasoning visibly toward a conclusion
  rather than arriving with one already packaged and polished. That changes
  the register, not just the content: "X suggests Y, which means Z" instead
  of presenting Z as settled. First-discovery phrasing ("here's what strikes
  me," "wait — that's different from what I thought") is normal here even
  though it would look unfinished in a learning session. Two people reasoning
  together leaves room for tangents, live uncertainty, and stopping before
  full resolution — that's the dynamic working as intended, not a sign it
  trailed off.
- Three trigger situations: Situation A (no historical narrative — ethics,
  philosophy, contested interpretation), Situation B (past the established
  content — push beyond what was learned), Situation C (user signals peer
  mode — "what do you think", "let's discuss").
- The fundamental difference from learning sessions: no predetermined answer
  Claude is guiding you toward. Claude takes genuine positions and defends
  them. Updates when given real reasons.
- The fluid state machine: FRAMING at start (what kind of question is this?),
  SYNTHESIS before CAPTURE, everything else free — EXPLORATION, POSITION,
  CHALLENGE, STEELMAN, SPECULATION, CHARACTER LENS, LOOP BACK.
- Epistemic markers: Claude signals confidence level — "the evidence is clear,"
  "I think the most defensible reading is," "I genuinely don't know," "this
  is speculative."
- Discussion notes: type: discussion. No atomic facts. No review schedule.
  Stays generative indefinitely. Records: the question, positions and
  reasoning, what shifted, what remains open.
- Profiles shape discussion — see Part 9 for profiles.

---

### Part 7 — The Vault Structure

Walk through each folder. Keep this concrete.

00 - Inbox/: Fast captures and scratch notes during sessions. Four options
when processing: keep it, schedule a learning session on it, move to
resources/ if it's reference material, or delete. When you choose anything
other than keep, Claude removes it from the inbox immediately.

01 - Journal/: Daily notes (morning ritual, captures), weekly review notes
(Sunday, three questions, five minutes), monthly review notes (created during
the monthly meeting).

02 - Notes/[Subject]/[Unit]/: All permanent knowledge notes. Never at the
root — always inside a subject and unit subfolder. Note types here: concept,
vocabulary. (Schema maps and the cross-domain map live in 03 - Schemas/, not
here — see below. Discussion notes are the one exception to the subject/unit
rule: they all live in 02 - Notes/Discussions/ regardless of topic, since a
discussion doesn't belong to a single subject the way a concept note does.)

03 - Schemas/: Domain schema maps (one per subject), the Cross-Domain Map
(vault-level structural pattern families), and the Concept Mapping System
reference file. The full typed schema maps live on paper — these notes contain
Mermaid depth-encoded overviews plus the text outline.

Graph view and why daily notes don't appear:
The Obsidian graph is designed to show the semantic knowledge network —
02 - Notes/ and 03 - Schemas/. Journal notes, inbox captures, and templates
are temporal artifacts that should not appear as graph nodes.

Daily notes never contain wikilinks (this is a system rule). So they naturally
appear as disconnected floating nodes if the graph shows them — visual noise
that obscures the knowledge clusters. More importantly, if daily notes DID
link to the concepts worked on each day, they would create hub nodes connecting
unrelated ideas through temporal co-occurrence. Natural Selection and
Thermodynamics would appear adjacent in your graph simply because both were
studied on a Tuesday in March. The cluster structure — groups of semantically
related ideas forming natural bulbs — would dissolve into noise. This is why
the wikilink prohibition exists, and why temporal notes should stay off the graph.

One-time setup to fix this in Obsidian:
Open the graph view. Find the search/filter field at the top of the graph
panel. Enter this filter string:
  -path:"01 - Journal/" -path:"00 - Inbox/" -path:"Templates/" -path:"resources/" -path:"Discussions/" -path:"03 - Schemas/" -path:"CLAUDE.md" -path:"AGENTS.md" -path:"README.md" -path:"LICENSE"

This removes those folders and the root config/doc files from the graph display
only. Notes remain fully visible in the file explorer, editor, and search — only
the graph is affected. The filter persists with the graph view settings. After
this setup, your graph shows only your permanent concept notes (not journal,
inbox, templates, resources, schema maps, or discussion notes), and the cluster
structure becomes visible.

Important: do NOT use Settings → Files & Links → Excluded Files for this.
That setting hides notes from the file explorer and search as well — too
aggressive. The graph view filter is the right tool.

resources/: Reference material visible in Obsidian's file explorer.
Organized into domain subfolders. Each subfolder can contain a library file —
a curated list of sources for that domain, tagged by how they can be accessed:

  [CLAUDE] — readable directly by the AI agent (webfetch URL, uploaded file)
  [NOTEBOOKLM] — add to NotebookLM; bring the briefing output back as source
  [MARKDOWN] — full text can be copied into a .md file; readable as plain text

When a learning session starts on a topic tied to an active GOALS.md goal,
the AI checks the relevant library in resources/ for available sources and
surfaces them before the session begins.

Library files can be formatted however you like — the AI reads them as
natural language. The only structured elements are the three accessibility
tags.

Claude never reads resources/ automatically between sessions — only when
explicitly referenced or during library-aware session startup.
Excluded from the graph view by the graph filter.

.claude/: System infrastructure. skills/ (the skill files), Profiles/
(Claude's intellectual identity files), Foundations/ (the foundational
research reports the system is built from), Transcripts/ (video transcripts),
Characters/ (historical figure narration files), GOALS.md.

.note-information/: Session-generated metadata. review-tracker.md (authoritative
review schedule by date), note-facts.md (hidden atomic facts per note),
Scratch/ (archived scratch notes after permanent note created), scheduled.md
(future scheduled items).

.archive/: Retired notes with full review history. archive-review-tracker.md
and archive-note-facts.md hold their metadata.

---

### Part 8 — Note Structure

Cover the anatomy of a concept note.

Frontmatter key fields:
- cognitive-state (generative/completed): the most important field. Controls
  everything Claude can do with the note.
- depth (foundational/conceptual/integrated): describes the note's content
  complexity, not your mastery.
- type (concept/schema-map/discussion): determines how Claude handles it.
- The review fields (review-1, review-2, review-3): each has a due date and
  a value that is "uncompleted" until replaced with the actual score.

Synthesis section (bottom of the note, after Connections):
- Layered record of every retrieval event, in strict time order — oldest at the
  top, newest at the bottom, never reordered.
- Teach-Back [DATE] → evaluation callout → Review 1 [DATE] → evaluation callout
  → Review 2 → ... Each layer shows what you recalled (your words, verbatim, never
  in a callout) and what the system found (the evaluation, always in a callout).
- Reviews after Review 3 are titled "Review N (Manual Review) — [DATE]".

The callout colors are a code — you can read a note's health at a glance:
- **Evaluation callouts are colored by your score:** dark-blue `[!todo]` = 100% ·
  teal `[!tip]` = 80–99% · orange `[!warning]` = 60–79% · red `[!failure]` = below
  60%. Scanning the Synthesis section, the colors trend from warm toward cool as
  you improve.
- **Green `[!success]` is reserved for the Final Synthesis** — the one green block,
  the note's apex, written only at completion. Under it, a dark-blue `[!todo]`
  "Audit additions" callout lists anything Claude added to reach 100%.
- A cyan `[!abstract]` "Re-consolidation note" marks a gap you closed in a
  targeted re-teach.
- **Purple `[!example]` is the general AI voice** — Leads, AI-written Applications,
  and the AI assessment on discussion notes (purple, to echo the color of
  wikilinks). It's the default for any AI content without a more specific color.
- A gray `[!quote]` callout at the top of a note is its **description** — the
  "what this note covers" orientation blurb.
- Every one of these is a built-in Obsidian callout, so the colors and icons just
  work the moment you open the vault — nothing to install.
- The rule behind all of it: **a callout always means Claude wrote it.** Your own
  words are never in a callout. So if it's in a colored box, the AI authored it.

Leads section (between Connections and Applications):
- This replaced what used to be called "Open Questions." Leads are the
  pathways out of a note — written by Claude at filing time, no gate, no
  back-and-forth. You haven't necessarily seen what you don't know yet;
  that's exactly why Claude writes these rather than asking you to.
- Three kinds, and they are genuinely different directions, not synonyms:
  - **Continuation** — forward. Where the conversation was heading when the
    session stopped. If we'd kept going, what would have come next?
  - **Boundary** — deeper, not sideways. The next zoom-in within this same
    concept — a finer mechanism or higher-resolution layer this note only
    treated coarsely. This is depth, not an adjacent topic. An adjacent or
    excluded topic belongs under Continuation or Open Questions instead —
    Boundary is reserved for "go further into the thing this note already covers."
  - **Open Questions** — outward. Genuine unresolved questions the material
    raises that this note doesn't answer.
- Claude writes every lead that actually exists and groups them by kind —
  it does not force one of each, and a note can have several of one kind and
  none of another. A kind with nothing in it is simply omitted, not invented.
- Leads are prose, not links. No forward wikilinks to notes that don't exist
  yet — a lead is a guess at a future direction, not a guess at a future
  note's name (the name gets decided fresh, with you, whenever that note
  actually gets created). A lead only becomes a real wikilink once you've
  actually pursued it and the resulting note exists.
- Leads accumulate as silent metadata until the monthly meeting, where stale
  ones get swept — pursue, keep, or drop, one at a time.

Connections section:
- User proposes connections first (in-vault and out-of-vault).
- Out-of-vault: Claude creates an inbox capture, adds a forward wikilink.
  Claude never suggests out-of-vault connections — only captures user-named ones.
- Missed in-vault connections: Claude probes Socratically (three levels)
  before naming any note.
- Back-links: when Note B connects to Note A, Claude silently adds a placeholder
  to Note A's Connections. At the monthly meeting you write the description
  from Note A's perspective. This deferral is deliberate — it's the system's
  spaced retrieval *for connections*, not for content. Note content gets
  spaced retrieval through the review schedule; the relationships between
  notes get theirs here. Reconstructing weeks later why two notes connect,
  from the other note's side, is a genuine retrieval event for relational
  knowledge — writing the description right when the connection is made
  would have almost no retrieval value, since nothing has been forgotten yet.

The verbatim rule vs. connection formalization:
- Synthesis: exact words preserved. Your words, not Claude's paraphrase.
- Connection descriptions: Claude formalizes your articulation for clarity.
  Different rule because the cognitive work is identifying the mechanism,
  not the exact wording.

---

### Part 9 — Customizable Features

**Profiles:**
What they are: Claude's persistent intellectual identity across sessions —
a personality paragraph describing how this Claude characteristically reasons,
plus belief weights (backend), working positions, position history, and
session notes. Every file in `.claude/Profiles/` is a profile. The default
shipped profile is named `Profile-1`; additional ones you create follow the
same pattern (`Profile-2`, `Profile-3`, …) unless you rename them.

The active-vs-loaded model — this is the part that surprises people:
- **The profile body doesn't auto-load at session startup.** Profiles are heavy
  context; the bulk (beliefs, positions, character, history) only loads on demand.
- **One exception loads at startup: the active profile's Persistent Memory.**
  That section is the always-on slice — it's small and it's meant to shape every
  session (see below), so Claude reads it at startup even though the rest waits.
- **Active** and **loaded** are different things. Active is a standing
  designation — at most one profile is active at a time (or none). Loaded
  means the full body has been pulled into the current conversation's context.
  A profile can be active without being loaded in a given session.
- **Where "active" is recorded:** only in each profile's own `Active: yes|no`
  header. There's no active-profile pointer in CLAUDE.md — Claude finds the
  active profile by scanning the headers. (If Claude ever tells you CLAUDE.md
  names the active profile, that's stale — it's the headers.)
- At startup, after reading the active profile's Persistent Memory, if a profile
  is active Claude asks once: "Load the active profile ([name])?" The full body
  loads only if you say yes — it never loads itself silently at the start.
- The one exception: **the active profile auto-loads silently before any
  Discussion Mode session**, whether you asked for it or it activated
  organically. You won't be asked there — it just loads, because Discussion
  Mode is where the profile's positions and reasoning style actually matter.
- Two commands, two different effects: **"activate [profile]"** marks it as
  the standing active profile but does *not* load it into context right now.
  **"load [profile]"** pulls it into context immediately *and* activates it
  (loading a profile that wasn't active automatically makes it active; the
  previous active profile is deactivated).

How to create a new profile:
"Put reference material in resources/ that represents the intellectual
character you want — a philosopher's work, a scientist's papers, an approach
to reasoning. Then ask me: 'Create a profile named [Name] based on the material
in resources/[filename].' I'll read it and generate the profile."

Switching: "Activate [Profile Name]" or "Load [Profile Name]" — pick based on
whether you want it live in this conversation now (load) or just set as the
standing default for future sessions (activate).

The profile also contains a Persistent Memory section — items you've asked
Claude to remember across all sessions. This is the slice that loads at startup,
so anything here shapes every session. To add something: just tell Claude
to remember it. Claude will ask how you want it stored before writing anything.

The shipped `Profile-1` already has one item in there, so you can see the feature
in action: a **schema-keyword pretest cue.** It tells Claude that, during the
pretest at the start of a learning session, it should name the topic's likely
schema-mapping keywords — *the bare terms only, never the definitions* (defining
them would hand you the answer and spoil the retrieval). It's there as an example
you can keep, reword, or delete outright — open `Profile-1.md`, read the
Persistent Memory section, and change it to whatever you want Claude to always do.

Multiple profiles are useful for: different intellectual registers, domain-
specific reasoning approaches, having a skeptical sparring partner.

Beliefs are qualitative when you ask how strongly Claude holds something
("very strongly, because..."). They're numerical only if you explicitly ask
for the weight value.

**GOALS.md:**
Long-term learning objectives. Drives the session-start suggestion. Format:
Primary goals (working on now), Secondary (queued), Paused, Abandoned.
Use the note: field to give Claude approach instructions for specific goals.
Enable/disable with the enabled: field at the top.

**resources/:**
Organized into domain subfolders with optional library files — curated
source lists tagged by accessibility type:
  [CLAUDE] — AI reads/fetches directly (webfetch or uploaded file)
  [NOTEBOOKLM] — add to NotebookLM; bring the briefing output back
  [MARKDOWN] — copy text to a .md file; then AI can read it

When a GOALS.md goal is active, the AI surfaces relevant library sources
at session start. Optional goal annotation:
  Primary: Learn startup fundamentals | library: Entrepreneurship-Library.md

Library files can be formatted any way you like — the AI reads natural
language. Only the three accessibility tags need to be recognizable.

**Characters:**
Historical figures used in the Narrative-Socratic pipeline. Claude creates
character files automatically on first use. Slim format: epistemic state
(what they knew/didn't know), characteristic reasoning paragraph, narrative
threads, discussion appearances.

**Schema notation (`.claude/skills/Schema-Mapping.md`):**
This file defines the notation Claude uses when you build schema maps — the node
types, the arrow families, the sub-relationships. It's a **swappable and deletable
module**, and there are three ways to run it:
- **Keep it** — use the shipped notation as-is.
- **Swap it** — rewrite the file with your own notation system (your own arrow
  types, your own conventions). Claude reads whatever's there and uses it.
- **Delete it** — schema mapping still runs, just **notationless**: Claude
  describes the relationships between ideas in plain, colloquial language instead
  of standardized arrow types. You don't lose schema mapping by deleting the file;
  you only lose the formal notation. (The rendered Mermaid diagram never showed
  the arrow types anyway — they live in the discussion, not the picture.)
So this is genuinely optional: the file is a vocabulary, not a switch. Take it,
replace it, or remove it to taste.

**Tutorial Mode:**
You're in it now. When you're ready to leave: delete tutorial-mode14.2.md
from .claude/skills/. Nothing else changes — Claude just stops narrating its
mechanics and offering tips. The vault operates identically.

---

### Part 10 — Weekly and Monthly Meetings

**Weekly meeting:**
Happens Sunday — reviewing the week just ended, named after that week.
Three questions, conversational, five minutes:
1. "Here's what you got through this week — [stats]. How do you feel about it?"
2. "Anything you want to do differently next week?"
3. "Any weak spots you want me to prioritize?"
Creates a weekly-review note. Brief. Not annoying.

**Monthly meeting:**
Prompted around the 28th. Named after the month being reviewed.
Six parts:

Part 1 — Reflection: genuine conversation about the month. Stats (notes
created, reviews completed, average scores, calibration trends). How you feel
about it. What worked, what didn't. Forward planning.

Part 2 — Schema work: review existing domain schema maps (user-led walk-through,
Claude transcribes updates), create missing schema maps for domains that lack
them, and collaborative cross-domain brainstorming (you judge whether structural
isomorphisms are genuine — Claude proposes, you decide).

Part 3 — Back-link descriptions: write the descriptions for every pending
back-link from the month — the "description pending monthly meeting"
placeholders sitting in your notes' Connections sections. This is deliberately
its own part, not a footnote to schema work: it's the system's spaced retrieval
for the *connections* between notes, the counterpart to how reviews handle
spaced retrieval for note *content*. Expect real volume here — every
connection made since the last meeting has a pending placeholder waiting.

Part 4 — Spring cleaning: scratch folder, inbox items older than 30 days,
overdue reviews, unused notes, stale notes, and open leads. Never deletes
anything without explicit per-item confirmation. Goes category by category.

Part 5 — Profile review: load the active profile (it doesn't auto-load
outside Discussion Mode, so this is one of the few places it's loaded
deliberately), then a calibration trend summary (consistent overestimation
pattern this month?), notable intellectual evolution, and any open discussion
questions worth revisiting.

Part 6 — System update check: if you've updated Maieutic since last month (new
skill version, pulled files), your *already-created* notes still use the old
format. Claude compares the version recorded in last month's note to the current
one, reads CHANGELOG.md for what changed, and offers to migrate your existing
notes to the new structure — per-item confirmation, like spring cleaning. For
example, updating into 14.2 would re-color your old evaluation callouts by score.
This is why the system keeps a CHANGELOG.md and records a version each month.

Creates a monthly-review note documenting everything.

---

### Part 11 — What to Start With

Close the walkthrough here.

Suggested first steps:
1. If you have learning goals: create .claude/GOALS.md with your primary
   goals. Format: "Primary: [goal], note: [any approach instructions]"
2. If you have reference material (syllabi, source PDFs): put them in
   resources/
3. Start a learning session on a topic you're actively working on.
   Claude will run the full pipeline.

The three things that matter most:
1. Retrieval before reading — always. Never look at the note before attempting recall.
2. Generation before suggestion — always. Propose your connections before Claude shows its.
3. The confidence estimate before every review — always. This is how the system tracks whether your self-assessment is accurate.

**Where to start — a recommendation:** if you're new, begin with **cognitive and learning science itself**. The bundled `Learning Science` library and the example Primary goal in GOALS.md are there for exactly this. It is the highest-leverage first move: learning *how* you learn — retrieval, spacing, desirable difficulty, calibration, transfer — makes every subject you study afterward stick faster and deeper. It compounds recursively: you use the system to get better at learning, which makes you better at using the system and at everything you learn next. And because the foundations this vault runs on *are* that science, you'll also come to understand why the system behaves the way it does.

"That's the full system. The single best place to start is learning science itself — it makes everything you learn afterward easier. Want to begin there, or with something you're already working on?"

---

### Part 12 — Source Libraries

Cover what a library is, the accessibility-label rule, and how to build one.

**What a library is:**

A library is a curated markdown file of sources for a topic area, stored in
resources/. Format is free-form — any structure is fine as long as it's
Claude-readable. Headings, bullet lists, tables, loose prose — whatever you
find easiest to maintain.

Libraries are not one-per-goal or one-per-domain. A library might cover a
broad topic that several goals draw from, or a goal might draw from several
libraries, or a goal might have no library at all. They don't need to pair
1:1 with anything.

If you want a goal tied to a specific library, add a `library:` annotation
to that goal in GOALS.md:

  Primary: Learn startup fundamentals | library: Entrepreneurship-Library.md

When that goal is active, Claude checks the named library for relevant
sources before the session begins.

---

**The hard rule — accessibility labels:**

Every source entry in a library must carry one or more of three labels.
These describe how Claude or you can actually get the content into a session —
not how good the source is.

[CLAUDE] — Claude can fetch it directly via WebFetch. A publicly accessible
URL: a web page, a public PDF, documentation.

[MARKDOWN] — you download or export it and insert it as a markdown or text
file in the vault, or copy-paste the content directly into the conversation.
Covers textbook chapters, paywalled articles, your own notes, anything you
can get into plain text.

[NOTEBOOKLM] — the source has to be compiled in NotebookLM first (the
standard case is YouTube videos, which Claude cannot watch). You bring back
NotebookLM's generated briefing or study guide as the actual source material
Claude works from — not the original video.

A source can carry more than one label — for example, a blog post that's
both [CLAUDE] (Claude can fetch the URL) and [MARKDOWN] (you also saved a
copy).

An unlabeled source is incomplete. If Claude encounters a source with no
label, it asks how the source is accessible before trying to use it.

Selection vs. access — keep these separate. Labels never influence WHICH
source gets picked for a session; that's decided on merit and fit for the
topic. Once a source is picked, Claude uses the best available method in
order: [CLAUDE] first (no friction, Claude just fetches it), then [MARKDOWN]
(you've already provided the text or can paste it), then [NOTEBOOKLM]
(requires you to have done the compilation step beforehand).

---

**An annotated example library:**

Here's a short library for a topic with two subdomains, showing the labels
and the optional metadata in practice.

  # Cellular Respiration — Library

  ## Glycolysis

  - **Campbell Biology, Ch. 9** — Lubert Stryer et al. [MARKDOWN]
    Core textbook treatment of the glycolysis pathway. Best for the
    step-by-step enzyme mechanics.

  - **"Glycolysis Explained" (YouTube)** — Crash Course [NOTEBOOKLM]
    Good visual walkthrough of the energy investment vs. payoff phases.
    Bring back the NotebookLM briefing.

  ## Electron Transport Chain

  - **"How the Electron Transport Chain Actually Works"** — Khan Academy
    [CLAUDE][MARKDOWN]
    https://www.khanacademy.org/science/ap-biology/cellular-energetics
    Clear conceptual overview of chemiosmosis. Have a saved copy as backup.

  - **"The Proton Gradient" (paper)** — Mitchell, P. (1961) [CLAUDE]
    https://example.org/mitchell-1961-chemiosmotic
    The original chemiosmotic hypothesis — useful for the historical framing
    in Phase 1.

The author and the one-line "why it's included" note are recommended but
optional — they help you and Claude judge fit quickly, especially when a
library grows large. For a big library with dozens of entries, you might
drop the per-source notes entirely and rely on subdomain grouping plus
labels alone. Both are fine; the labels are the only part that's required.

---

**How to build one:**

The recommended workflow doesn't happen inside the vault session — open a
separate project or conversation and use a deep-research skill there.

Ask it to research the topic, break the topic into subdomains, and find
multiple sources per subdomain — the kind of spread you'd want for a real
library, not just the first few search results. Then take that output and
format it as a library file with accessibility labels, and drop it into
resources/.

Claude can also do the formatting step for you on request: dump the links
and sources you've gathered into the conversation, and Claude will structure
them into a library file, group them by subdomain, and propose labels for
each. You confirm or correct the labels before anything is saved — Claude
won't guess at [NOTEBOOKLM] vs [CLAUDE] for something ambiguous without
checking with you.

---

**Where it goes and linking it to a goal:**

Save the finished library to resources/, in the relevant domain subfolder.
Like everything else in resources/, it's read-on-request only — Claude never
auto-reads it between sessions, except during library-aware sourcing when a
GOALS.md goal points to it.

If you want this library surfaced automatically when working on a specific
goal, add the `library:` annotation to that goal in GOALS.md:

  Primary: Learn startup fundamentals | library: Entrepreneurship-Library.md

That's the only wiring needed — the library file itself stays exactly as
free-form as you want.

---
## DELETING THIS FILE

Delete `tutorial-mode14.2.md` from `.claude/skills/`.

The vault system is identical. Claude stops narrating mechanics, explaining
procedures, and offering first-encounter tips. Every other behavior remains
exactly the same.

No other changes are needed anywhere in the vault.
