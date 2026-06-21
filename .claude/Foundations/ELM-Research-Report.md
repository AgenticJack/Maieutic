# How to Learn Anything and Make It Stick: Evidence-Based Implementation Guide

## Table of Contents
- [Key Findings & Action Items](#key-findings--action-items)
- [1. Foundational Science](#1-foundational-science): 1.1 Illusion · 1.2 Productive Failure · 1.3 Generation Effect · 1.4 Study-Method Hierarchy
- [2. Discovery-Based Learning](#2-discovery-based-learning): 2.1 Problem-First Protocol · 2.2 Pretesting · 2.3 Invention Before Instruction · 2.4 Boundary Conditions · 2.5 Vault Template
- [3. AI as Tutor](#3-ai-as-tutor): 3.1 Effect Sizes · 3.2 Socratic vs Direct · 3.3 ICAP · 3.4 Eight Generative Strategies · 3.5 Self-Explanation/Teach-Back · 3.6 Prompt Templates
- [4. Speed-Retention Tradeoff](#4-speed-retention-tradeoff): 4.1 Soderstrom-Bjork · 4.2 Deliberate Practice · 4.3 Fast+Durable Conditions · 4.4 Ultralearning Audit · 4.5 Rawson & Dunlosky Schedule
- [5. Second-Brain Integration](#5-second-brain-integration): 5.1 Pipeline · 5.2 AI Session Template · 5.3 Handoff Protocol · 5.4 Principles 11-15 · 5.5 Daily Workflow · 5.6 Weekly Review
- [6. Evidence Gaps](#6-evidence-gaps)
- [References](#references)

---

## Key Findings & Action Items

| # | Finding | Evidence | Mechanism |
|---|---|---|---|
| 1 | In-session performance ≠ retention. Re-reading/highlighting/lecture-review feel productive but produce fluency without retention; retrieval/interleaving/spacing feel harder but build durable retention | Soderstrom & Bjork, 2015; Dunlosky et al., 2013 | Desirable difficulty forces reconstruction of retrieval pathways |
| 2 | Attempting a problem and failing *before* instruction improves transfer vs. instruction-first | Kapur, 2008/2011/2014; Kapur & Bielaczyc, 2012 | Productive failure — prepares schema with "hooks" |
| 3 | AI tutoring at Socratic level ≈ **1.0 SD** improvement over passive reading | Nye et al., 2014 (AutoTutor); VanLehn, 2011 (ITS meta-analysis, ~0.76 SD) | Generative/interactive processing |
| 4 | Interactive > Constructive > Active > Passive — every session should hit Interactive/Constructive | Chi & Wylie, 2014 (ICAP) | AI makes Interactive engagement available solo |
| 5 | Three retrievals with expanding gaps = optimal retention-to-time ratio for individual facts/concepts | Rawson & Dunlosky, 2011 | Spaced retrieval; desirable difficulty |

**Action items:**
1. Run "problem-first" sessions: attempt in writing before asking Claude to explain.
2. Configure Claude in Socratic mode (templates in §3.6) — never request direct explanation pre-attempt.
3. After every AI session, write the knowledge handoff note from memory before reviewing the chat log.
4. Schedule three spaced retrievals per new concept: **Day 1, Day 5, Day 14** (from initial learning).
5. Adopt Principles 11–15 (§5.4) as the vault's operating system for the pre-vault learning pipeline.

---

## 1. Foundational Science

### 1.1 Learning-Performance Illusion

**Core finding (Soderstrom & Bjork, 2015):** current in-session performance is a poor predictor of long-term retention. Conditions that maximize in-session performance (repetition, massed practice, re-reading) minimize long-term retention; conditions that minimize in-session performance (retrieval practice, interleaving, spacing, variation) maximize it.

**Mechanism:** desirable difficulties force the memory system to reconstruct and re-route retrieval pathways — the effort of reconstruction *is* the learning. Without that effort, you activate existing traces without building new retrieval structure.

**Vault risk:** browsing linked notes, reviewing polished summaries, and watching AI explain concepts all produce high in-session performance / low retention unless paired with active generation/retrieval.

**Diagnostic question:** "Am I generating output from memory, or am I consuming input?" Consuming → illusion territory.

### 1.2 Productive Failure

**Core finding (Kapur, 2008, 2011, 2014; Kapur & Bielaczyc, 2012):** students who attempt complex problems before instruction, and fail, learn more deeply and transfer better than students given direct instruction first.

**Mechanism — attempting without knowing the method:**
- Activates/surfaces prior knowledge (even if wrong)
- Surfaces critical problem features
- Generates solution hypotheses
- Builds awareness of knowledge gaps
- Creates a schema with "hooks" for subsequent correct instruction

**Confirming meta-analysis (Loibl, Roll & Rummel, 2017):** problem-solving-before-instruction (PS-I) outperforms instruction-before-problem-solving (I-PS) specifically on **transfer and flexible application** measures.

**Typology (Kapur, 2016):** productive quadrant = "failure on the problem, success on the learning." Unproductive failure = fail the problem AND fail to learn — occurs when no consolidating instruction follows, or the problem is outside the learner's ZPD.

**Boundary condition:** problem must be within ZPD (difficult but not alien). Zero anchoring knowledge → brief orientation (vocabulary/domain framing) required before attempting. AI's first job = minimum viable scaffolding, not full instruction.

### 1.3 Generation Effect

**Core finding (Slamecka & Graf, 1978):** self-generated material — even partial or incorrect — is retained significantly better than read material. Replicated hundreds of times.

**Pretesting extension (Richland, Kornell & Kao, 2009):** answering questions about unstudied material improves later learning of that material *even when the pretest answers are wrong* — failed retrieval activates encoding processes.

**Applied implication:** notes must be generated, not pasted. Pasting AI explanations — however well-formatted — is reading, not generating, and activates the learning-performance illusion (1.1).

### 1.4 Study-Method Hierarchy (Dunlosky et al. 2013)

Most comprehensive meta-analysis of study techniques:

| Utility | Techniques |
|---|---|
| **High** | Practice testing / retrieval practice (highest effect sizes); distributed practice (spacing) |
| **Moderate** | Elaborative interrogation ("why is this true?"); self-explanation; interleaved practice |
| **Low** | Summarization; highlighting/underlining; re-reading |

**Key takeaway:** re-reading and highlighting are the two *most-used* and *lowest-evidence* techniques for retention — they optimize feeling of learning, not learning.

---

## 2. Discovery-Based Learning

### 2.1 Problem-First Protocol

Operationalizes productive failure (1.2) for solo learners:

1. **Orientation** (2–5 min): minimum viable context — vocabulary, domain, problem type. No more.
2. **Attempt** (15–30 min): work the problem without resources; write thinking explicitly. Wrong answers count.
3. **Consolidation** (20–40 min): study material / get AI explanation / read source. Prior attempt primes schema receptivity.
4. **Contrast** (5–10 min): explicitly compare your attempt to the correct approach — deepest encoding happens here.
5. **Handoff** (10 min): write the knowledge note from memory.

Setup: scratch note tagged `#generative` for steps 1–4; `#completed` knowledge note for step 5.

### 2.2 Pretesting

Before any new topic, write (5–10 min):
- What do I already believe is true?
- What would I predict the key mechanisms/principles to be?
- What questions can't I answer?

Research basis: Richland et al. (2009) + generation effect (1.3) — predicting (even wrongly) improves subsequent retention.

**Claude usage:** state your current understanding first and ask Claude to identify what's correct/off. Do not request an upfront explanation.

### 2.3 Invention Before Instruction

**Schwartz & Martin (2004)** — "preparation for future learning": productive failure produces a prepared mind that learns faster/deeper from subsequent instruction.

**Invention task protocol:** before learning how a concept works, try to invent a solution to the problem it solves (e.g., before Bayes' theorem, try to invent a method for updating confidence given new evidence). The invention will be wrong/incomplete — that's the point; it frames *why* the real solution is designed as it is.

**Canonical example:** 3Blue1Brown videos present the problem before the solution — watch twice: once to attempt (pause and think), once for the explanation.

**Claude prompt:**
```
I'm about to learn [CONCEPT]. Before you explain anything, give me the core 
problem that [CONCEPT] was invented to solve, described at the level of the 
phenomenon only. Don't mention [CONCEPT] or its solution. I'll try to invent 
a solution first.
```

### 2.4 Boundary Conditions

Discovery learning fails when:
- **No anchoring knowledge** — no hooks for attempted generation → 5-min orientation first.
- **No consolidating instruction follows** — productive failure effect disappears without it; Claude's consolidation step (2.1 step 3) is critical.
- **Task too far outside ZPD** — must be hard but reachable.
- **Time pressure** — attempt phase needs real cognitive effort over real time; rushing cancels the benefit.

**Rule of thumb:** staring blankly with nothing written after 5 min of genuine effort → need more orientation before attempting.

### 2.5 Vault Template

```
---
tags: [generative, discovery-session]
date: {{date}}
topic: 
domain:
---

## What I Already Believe (Pretest)

## My Attempted Solution / Explanation

## Key Questions I Can't Answer

## [After Instruction] What I Got Right / What I Got Wrong

## The Contrast (What the correct version adds/changes)

## Handoff Note → [[]]
```
`#generative` tag gates AI features. Only "After Instruction" section involves Claude input.

---

## 3. AI as Tutor

### 3.1 Effect Sizes

| Source | Comparison | Effect size | Confidence |
|---|---|---|---|
| VanLehn, 2011 (ITS meta-analysis, 28 systems) | ITS vs. traditional instruction | ~0.76 SD | High |
| Nye et al., 2014 (AutoTutor, Socratic dialogue) | vs. reading text alone | ~1.0 SD | High |
| Weng & Chiu, 2023 (AI-assisted language learning meta-analysis) | interactive practice w/ feedback | Hedges' g = 0.72 | Moderate (transferred) |

**Bottom line:** Socratic-mode AI tutoring ≈ Bloom's 2-Sigma effect (Bloom, 1984 — the one-on-one human tutoring advantage), achievable solo — **but only if the AI is in tutoring mode, not answer-dispensing mode.** Claude defaults to direct-answer; must be explicitly configured (3.6).

### 3.2 Socratic vs Direct-Answer AI

| Mode | ICAP level | Retrieval triggered? | Outcome |
|---|---|---|---|
| Direct-answer | Active/Passive | No | Learning-performance illusion activates |
| Socratic | Constructive/Interactive | Yes, repeatedly | Productive failure + generation effect operate; errors surfaced in context |

### 3.3 ICAP Hierarchy

**Chi & Wylie (2014)** — Interactive > Constructive > Active > Passive:

| Level | Behavior | Outcomes |
|---|---|---|
| Interactive | Co-constructing knowledge via dialogue, challenging explanations | Highest |
| Constructive | Generating/explaining/drawing/predicting beyond given info | Strong |
| Active | Manipulating materials, note-taking from source | Modest |
| Passive | Watching/listening/reading | Lowest |

Most solo learners sit at Active/Passive. AI tutors enable Interactive at zero marginal cost.

**Design principle:** start Constructive (generate your explanation) → escalate to Interactive (dialogue challenges it). Reading Claude's output without generating a response = Passive.

### 3.4 Eight Generative Strategies

**Fiorella & Mayer (2016)**:

| Strategy | Mechanism | How Claude Enables It |
|---|---|---|
| Summarizing | Encoding by reduction | Critiques your summary, finds gaps |
| Mapping | Spatial organization | Asks "what connects to what?" — you draw first |
| Drawing | Dual coding | Describes concept; you draw, Claude responds |
| Imagining | Mental simulation | Gives scenario; you predict outcomes |
| Self-testing | Retrieval practice | Generates test questions on your material |
| Self-explaining | Deep elaboration | Asks "why" until you bottom out |
| Teaching | Retrieval + restructuring | Plays novice; you teach it |
| Enacting | Embodied processing | Gives procedures; you walk through step-by-step |

**Highest-yield combo:** self-explaining + self-testing (generate explanation, then get tested on it). Use ≥2 strategies per session.

### 3.5 Self-Explanation / Teach-Back

**Chi et al. (1994):** self-explanation during study → dramatically better learning than no self-explanation. One of the highest-utility techniques in Dunlosky et al. (2013).

**Mechanism:** forces identification of understanding gaps, generates bridging inferences, integrates new info with prior knowledge.

**Teach-back protocol with Claude:**
1. Study the concept.
2. Close source material.
3. Tell Claude: *"I'm going to explain [concept] to you as if you're a student who has never encountered it. Ask clarifying questions when my explanation is unclear, incomplete, or wrong, but don't correct me outright — just probe. After I'm done, give me a diagnostic of what I understood correctly and what I missed."*
4. Deliver explanation → 5. Answer Claude's probes → 6. Review diagnostic → 7. Write handoff note.

**King (1992):** student-generated "why"/"how" questioning produces deeper comprehension than note-taking. Prompt: *"Generate five 'why' and five 'how' questions about [concept] that I should be able to answer — but don't answer them. I'll attempt each one."*

### 3.6 Prompt Templates

**Template 1 — Socratic Mode Activation** (implements Principle 12)
```
I want to learn [TOPIC]. I'll give you my current understanding. Your job is to ask 
me one question at a time to probe, extend, and correct my thinking. Do not explain 
anything to me unprompted. If I ask you a direct question, respond with a guiding 
question instead unless I explicitly say "just tell me."

My current understanding of [TOPIC]: [YOUR ATTEMPT]

Begin with your first probing question.
```

**Template 2 — Productive Failure Setup** (implements Principle 11)
```
I want to work on [PROBLEM/CONCEPT] but I don't want any instruction yet.
Give me only: (a) the core problem that [CONCEPT] solves, described purely
as a phenomenon, without mentioning solutions or the concept itself, and
(b) two constraints or requirements any good solution would need to satisfy.
I will attempt a solution and share it with you. Do not provide any hints 
beyond what I've asked for here.
```

**Template 3 — Teach-Back Protocol** (implements Principle 13)
```
I've just studied [TOPIC]. I'm going to explain it to you as if you're learning
it for the first time. Your rules:
1. Ask clarifying or probing questions when I'm unclear or incomplete
2. Do not correct errors directly — probe them instead
3. Do not add information I haven't mentioned
4. After I say "done," give me a diagnostic: what I got right, what I missed,
   what was partially correct

Ready? Here's my explanation: [YOUR EXPLANATION]
```

**Templates 4–7 — supplementary generative-strategy prompts** (same pattern as 1–3: assign Claude a constrained role, withhold answers/explanations until you've attempted):

| # | Name | Ask Claude to... | Best for |
|---|---|---|---|
| 4 | Self-Testing Generator | Generate 10 questions (3 factual + 4 conceptual "why/how" + 3 transfer/application) on your material, no answers, then evaluate your answers | AP exam prep — run nightly before tests |
| 5 | Elaborative Interrogation | For each of 3–5 claims from your material, ask "why is this true?", drill follow-ups until you can't go deeper | Mechanism-heavy domains (neuroscience, ML, math) |
| 6 | Interleaving Generator | Generate 15 mixed practice questions across 3 topics, no two consecutive from the same topic, requiring discrimination between topics | Multi-topic review periods |
| 7 | Knowledge Gap Diagnostic | Ask 3 questions probing the limits of your understanding on a topic you think you've mastered, then report where it's solid vs. shallow | Surfacing fluency-illusion gaps (esp. marketing/conceptual domains) |

**Domain routing:** AP Bio/Physics/Chem → Templates 4 (nightly), 6. Neuroscience/ML → Templates 3, 5. 3Blue1Brown math → Template 2 first (attempt before watching), then 5 (explains *why* the structure is shaped as it is). Marketing → Template 7 (gap diagnostic surfaces unearned fluency fastest).

---

## 4. Speed-Retention Tradeoff

### 4.1 Soderstrom-Bjork Result

**Core finding:** performance during practice is a poor indicator of learning. Massed practice (cramming) → rapid initial learning + rapid forgetting. After 30 days, spaced-practice learners retain dramatically more.

Most "ultralearning" approaches optimize fast initial performance, not durable retention — except those incorporating desirable difficulty (direct application, project-based immersion, immediate feedback).

**Implication:** you can compress *volume per session*; you cannot compress *inter-session intervals* without destroying retention. Cramming for an AP exam → exam-day performance, ~zero retention 2 months later.

### 4.2 Deliberate Practice

**Ericsson, Krampe & Tesch-Römer (1993)** — four components:
1. Tasks targeting specific weaknesses (not reinforcing strengths)
2. Immediate, specific feedback
3. Repetition with feedback-based modification
4. High mental effort (not comfortable fluency-building)

**Macnamara, Hambrick & Oswald (2014) meta-analysis:** deliberate practice explains **~26% of variance** in performance across most domains — largest single controllable factor, though not the only one.

**Not deliberate practice:** effortful-but-undirected activity (e.g., attentive re-reading). Requires a targeted weakness + designed task + improvement feedback.

**Claude prompt:** *"I just attempted [task]. Here's my output. What are the specific gaps in my knowledge or reasoning that produced the errors or weaknesses you can see?"*

### 4.3 Conditions for Fast + Durable Learning

1. **High prior knowledge density** — more adjacent-domain knowledge → faster acquisition (existing schema hooks). Front-load vocabulary/conceptual skeleton first (pretesting/orientation, §2.2).
2. **Immediate application with real stakes** — Kornell & Bjork (2008) and Taylor & Rohrer (2010): interleaving problem types → slower initial learning, faster subsequent learning via discrimination (identifying problem type before solving). Favor project-based application.
3. **Feedback loops <24 hours** — faster feedback → more efficient trace correction. AI gives sub-minute feedback, but only useful *after* attempting, not as a substitute for it.

### 4.4 Ultralearning Evidence Audit

**Young (2019)** — 9 principles, audited:

| Principle | Evidence | Notes |
|---|---|---|
| Metalearning (map terrain first) | Moderate | Consistent with schema theory |
| Focus (intense, distraction-free) | Moderate | Consistent with cognitive load research |
| Directness (direct application) | **Strong** | Transfer-appropriate processing literature |
| Drill (attack weakest points) | **Strong** | = deliberate practice |
| Retrieval (testing over review) | **Strong** | Most-replicated finding in memory research |
| Feedback (immediate, accurate) | **Strong** | Core to deliberate practice |
| Retention (spaced repetition) | **Strong** | Decades of evidence |
| Intuition (deep understanding first) | Weak | Plausible, minimal support |
| Experimentation (vary approach) | Weak | Reasonable heuristic, not directly studied |

Take Directness, Drill, Retrieval, Feedback, Retention seriously; treat the rest as heuristics.

### 4.5 Rawson & Dunlosky Retrieval Schedule

**Rawson & Dunlosky (2011):** three successful retrievals with expanding gaps = best retention-to-time ratio.

| Day | Action | Outcome |
|---|---|---|
| 0 | Learn + test until retrieved correctly once | Initial encoding |
| 1 | Test without reviewing | Retrieval 1 (if correct) |
| 5 | Test | Retrieval 2 (if correct) |
| 14 | Test | Retrieval 3 — long-term retention established |

**Failed retrieval at any session → reset; review briefly and reschedule.**

For complex conceptual knowledge, retrieval task = explanation/application ("Explain the mechanism of X" / "Apply X to this novel problem"), not "What is X?"

Obsidian implementation: tag new notes `#review-day1`, `#review-day5`, `#review-day14`; Dataview query surfaces due reviews daily. This schedule applies specifically to **new acquisitions in the first two weeks** (separate from general dormant-note resurfacing).

---

## 5. Second-Brain Integration

### 5.1 Learning Pipeline

| Phase | Action | Output | Time |
|---|---|---|---|
| 1. Prepare | Pretest, activate prior knowledge, frame problem | `#generative` scratch note (beliefs + questions) | 5–10 min |
| 2. Attempt | Problem-first / invention-before-instruction | Written attempt in scratch note | 15–30 min |
| 3. Consolidate | AI tutoring (Socratic), teach-back, self-testing | Session log (not yet in vault) | 20–45 min |
| 4. Handoff | Write knowledge note from memory; then check session log for gaps | `#completed` knowledge note in vault | 10–15 min |

**Total: 50–100 min per concept** — this is the cost of durable learning, not a shortcut.

### 5.2 AI Tutoring Session Template

Save as Claude Project instruction:

```
TUTORING SESSION PROTOCOL

You are my Socratic tutor. Your operating rules:
1. Never answer a direct question unprompted — always ask a guiding question first
2. When I give you an explanation, probe it before accepting it
3. When I get something wrong, ask me a question that reveals the error; 
   don't just correct me
4. Track what I've demonstrated I understand vs. what I've glossed over
5. At the end of the session (when I say "end session"), give me:
   a) What I demonstrated solid understanding of
   b) What I revealed gaps in
   c) Three retrieval questions I should answer tomorrow
   d) One application task I should complete this week

My learning goal for today: [TOPIC]
My current understanding: [ATTEMPT]

Begin.
```

### 5.3 Knowledge Handoff Protocol

The critical transition: AI-generated insight → your knowledge.

1. **Close the Claude window.** Don't look at it.
2. **Open `#completed` note**, write: core concept (1 sentence, your words); mechanism (why it works, your words); 2–3 connecting links to existing notes (you choose); one open question; one application to attempt this week.
3. **Now open the Claude log.** Check for gaps. Anything added from the log gets a `[!ai-generated]` callout.
4. **Tag for spaced review:** `#review-day1` + creation date.

**Discipline:** what enters the vault is YOUR reconstruction, not the AI's explanation — the generation effect in practice.

### 5.4 Principles 11-15

These five govern the **pre-vault learning-session pipeline** (extending the existing 10 vault-side principles):

---

**Principle 11 — Problem-First Sequencing** [HIGH evidence]

*For any new concept/skill domain, always attempt the problem before receiving instruction.*

Session structure: Prepare → Attempt → Consolidate → Handoff. Never invert, except with zero anchoring knowledge → 5-min orientation only, then return to Attempt.

Mechanism: Productive failure (Kapur, 2008–2016, §1.2) + Generation effect (Slamecka & Graf, 1978, §1.3).

---

**Principle 12 — Socratic-First AI Interaction** [HIGH evidence — ITS literature; MODERATE — LLM-specific]

*During active learning phases, Claude must operate in Socratic mode.*

Direct-answer mode permitted only after: (a) an attempt made, (b) teach-back completed, (c) explicit release via "just tell me." Default = probing, not explaining.

Mechanism: ICAP (Chi & Wylie, 2014, §3.3); AutoTutor (Nye et al., 2014, §3.1).

---

**Principle 13 — Generation-Before-Vault** [HIGH evidence]

*Nothing enters a `#completed` note that was not first generated from memory.*

AI logs/source excerpts/external explanations may be consulted post-draft only to check gaps, not as the draft itself. Material added post-draft from external sources → `[!ai-generated]` or `[!source-copied]` callout.

Mechanism: Generation effect + self-explanation effect (Chi et al., 1994; Slamecka & Graf, 1978, §1.3/3.5).

---

**Principle 14 — Three-Retrieval Scheduling** [HIGH evidence]

*Every new concept note receives three scheduled retrieval events: Day 1, Day 5, Day 14 (from creation/initial learning).*

Retrieval tasks = explanation/application, not passive review. Missed retrieval → reset schedule. After 3 successes → transitions to standard Principle 2 spaced surfacing.

Mechanism: Rawson & Dunlosky (2011) optimal retrieval protocol (§4.5).

---

**Principle 15 — Desirable Difficulty Calibration** [HIGH evidence]

*Rate each session for subjective difficulty (1–5) and fluency (1–5) at close.*

- High fluency + low difficulty → **illusion territory** (material too easy or method too passive). Fix: increase problem difficulty, switch to interleaved practice, or extend spaced interval.
- Low difficulty + low fluency → outside ZPD. Fix: reduce scope, add orientation.

Mechanism: Learning-performance distinction (Soderstrom & Bjork, 2015, §1.1/4.1).

---

### 5.5 Daily Workflow

```
DAILY LEARNING SESSION (90 minutes)

[0:00-0:10]  Dataview query for today's review tags (#review-day1/5/14).
             Answer from memory BEFORE opening notes. (Principles 1 + 14)

[0:10-0:20]  New topic pretest. #generative scratch note: beliefs + questions. (Principle 11)

[0:20-0:45]  Attempt phase. Work the problem. No resources, no Claude. (Principle 11)

[0:45-1:15]  AI tutoring (Socratic, §5.2 template). Teach-back. Generate test questions.
             At 1:10, say "end session" → receive diagnostic. (Principle 12)

[1:15-1:30]  Close Claude. Write handoff note from memory (#completed).
             Add review tags, link existing notes. (Principles 4, 13, 14)
             Rate difficulty + fluency 1-5. (Principle 15)
```

**30-min compressed version:** retrieve due notes (10 min) → pretest one new concept (5 min) → handoff from prior session if incomplete (15 min). **Never skip retrieval of due notes** — that's where most retention work happens.

### 5.6 Weekly Review

Run weekly (30–45 min):

1. **Retrieval audit** (10 min): query notes from past 14 days; write one sentence from memory per note before opening; check gaps.
2. **Gap identification** (10 min): weak retrievals → tag `#needs-rework`, add to next week's attempt phase (re-engage productive failure cycle, not just review).
3. **Connection-making** (10 min): prompt Claude — *"Here are this week's concepts: [list]. Ask me three questions that require me to connect two or more of them. Don't tell me the connections — let me find them."* (Principles 4 + 12)
4. **Calibration check** (5 min): review week's difficulty/fluency ratings — consistently too easy/hard? Adjust scope.
5. **Schedule next week** (5 min): write problem statements for next week's new topics — pretest begins the moment you sit down.

---

## 6. Evidence Gaps

| Gap | Detail |
|---|---|
| 1. Adult self-directed LLM-tutored learners | No controlled retention studies. ITS evidence (VanLehn 2011; Nye et al. 2014) is from structured courses — extrapolation to solo Claude use is reasonable but untested. |
| 2. Productive failure research base | Almost entirely K-12/university classroom (Kapur corpus uses teacher-delivered consolidation). Solo-adult-with-Claude version is theoretically sound but empirically untested. |
| 3. AI-tutoring → PKM handoff workflow | No empirical literature. §5.3 protocol is constructed from generation-effect + provenance-preservation principles, not directly studied. |
| 4. LLM tutoring longitudinal retention | Nearly nonexistent; most studies measure immediate/short-term outcomes. 30/90-day persistence of Claude-Socratic gains unknown. |
| 5. Speed-retention tradeoff for adults | Deliberate-practice/ultralearning literature rarely engages directly with spacing/retrieval literature. Open question for time-limited adult learners. |

**Recommended response:** run a self-experiment — pick one domain, apply Principles 11–15, rate retention at 30/90 days via self-testing templates (§3.6 Template 4). Generates n=1 evidence specific to your setup.

---

## References

### Cited in body (support Principles 11-15 directly)
Kapur, M. (2008). Productive failure. *Cognition and Instruction, 26*(3), 379–424.
Kapur, M. (2011). A further study of productive failure in mathematical problem solving. *Instructional Science, 39*(4), 561–579.
Kapur, M. (2014). Productive failure in learning math. *Cognitive Science, 38*(5), 1008–1022.
Kapur, M. (2016). Examining productive failure, productive success, unproductive failure, and unproductive success in learning. *Educational Psychologist, 51*(2), 289–299.
Kapur, M., & Bielaczyc, K. (2012). Designing for productive failure. *Journal of the Learning Sciences, 21*(1), 45–83.
Schwartz, D. L., & Martin, T. (2004). Inventing to prepare for future learning. *Cognition and Instruction, 22*(2), 129–184.
Richland, L. E., Kornell, N., & Kao, L. S. (2009). The pretesting effect. *Journal of Experimental Psychology: Applied, 15*(3), 243–257.
Slamecka, N. J., & Graf, P. (1978). The generation effect. *Journal of Experimental Psychology: Human Learning and Memory, 4*(6), 592–604.
Kornell, N., & Bjork, R. A. (2008). Learning concepts and categories: Is spacing the "enemy of induction"? *Psychological Science, 19*(6), 585–592.
Loibl, K., Roll, I., & Rummel, N. (2017). Towards a theory of when and how problem solving followed by instruction supports learning. *Educational Psychology Review, 29*(4), 693–715.
VanLehn, K. (2011). The relative effectiveness of human tutoring, intelligent tutoring systems, and other tutoring systems. *Educational Psychologist, 46*(4), 197–221.
Nye, B. D., Graesser, A. C., & Hu, X. (2014). AutoTutor and family: A review of 17 years of natural language tutoring. *International Journal of Artificial Intelligence in Education, 24*(4), 427–469.
Bloom, B. S. (1984). The 2 sigma problem. *Educational Researcher, 13*(6), 4–16.
Ericsson, K. A., Krampe, R. T., & Tesch-Römer, C. (1993). The role of deliberate practice in the acquisition of expert performance. *Psychological Review, 100*(3), 363–406.
Soderstrom, N. C., & Bjork, R. A. (2015). Learning versus performance: An integrative review. *Perspectives on Psychological Science, 10*(2), 176–199.
Taylor, K., & Rohrer, D. (2010). The effects of interleaved practice. *Applied Cognitive Psychology, 24*(6), 837–848.
Rawson, K. A., & Dunlosky, J. (2011). Optimizing schedules of retrieval practice for durable and efficient learning. *Journal of Experimental Psychology: General, 140*(3), 283–302.
Macnamara, B. N., Hambrick, D. Z., & Oswald, F. L. (2014). Deliberate practice and performance: A meta-analysis. *Psychological Science, 25*(8), 1608–1618.
Young, S. H. (2019). *Ultralearning.* Harper Business. [Practitioner source]
Dunlosky, J., et al. (2013). Improving students' learning with effective learning techniques. *Psychological Science in the Public Interest, 14*(1), 4–58.
Chi, M. T. H., de Leeuw, N., Chiu, M. H., & LaVancher, C. (1994). Eliciting self-explanations improves understanding. *Cognitive Science, 18*(3), 439–477.
Chi, M. T. H., & Wylie, R. (2014). The ICAP framework. *Educational Psychologist, 49*(4), 219–243.
Fiorella, L., & Mayer, R. E. (2016). Eight ways to promote generative learning. *Educational Psychology Review, 28*(4), 717–741.
King, A. (1992). Facilitating elaborative learning through guided student-generated questioning. *Educational Psychologist, 27*(1), 111–126.
Weng, X., & Chiu, T. K. F. (2023). AI-assisted language learning: Systematic review and meta-analysis. *Computers & Education: Artificial Intelligence, 4*, Article 100117.

### Background / not cited in body (preserved from original, not load-bearing for Principles 11-15)
Zimmerman, B. J. (2000). Attaining self-regulation. In *Handbook of self-regulation* (pp. 13–39), Academic Press · Pintrich, P. R. (2004). *Educational Psychology Review, 16*(4), 385–407 · Kasneci, E., et al. (2023). ChatGPT for good? *Learning and Individual Differences, 103*, Art. 102274 · Kuhail, M. A., et al. (2023). *Education and Information Technologies, 28*(1), 973–1018 · Denny, P., Kumar, V., & Giacaman, N. (2023). *ACM SIGCSE* [Preliminary] · Pardos, Z. A., & Bhandari, S. (2023). *arXiv preprint* · Tankelevitch, L., et al. (2023). *CHI 2023* · DeCaro, M. S., & Rittle-Johnson, B. (2012). *Journal of Experimental Child Psychology, 113*(4), 552–568 · Kornell, N., Castel, A. D., Eich, T. S., & Bjork, R. A. (2010). *Psychology and Aging, 25*(2), 498–503 · Roediger, H. L., & Pyc, M. A. (2012). *Journal of Applied Research in Memory and Cognition, 1*(4), 242–248 · Pressley, M., et al. (1987). *JEP: Learning, Memory, and Cognition, 13*(2), 291–300 · Lombrozo, T. (2006). *Trends in Cognitive Sciences, 10*(10), 464–470 · Wylie, R., & Chi, M. T. H. (2014). In *Cambridge handbook of multimedia learning* (2nd ed., pp. 413–432), Cambridge University Press.

---

*Research synthesis, May 2026.*
