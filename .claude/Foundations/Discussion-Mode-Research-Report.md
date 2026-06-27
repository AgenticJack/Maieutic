# Discussion Mode: Peer-Level Intellectual Co-Construction
## Evidence Base and Implementation Design

**Source:** Research synthesis for second-brain-principles6.2.md | **Date:** 2026-05-20 | **Follows:** Principles 1–20, Templates 1–12

## Table of Contents
- [Executive Summary](#executive-summary)
- [Part 1: Why Peer Discussion Differs — Cognitive Science](#part-1-why-peer-discussion-differs--cognitive-science)
- [Part 2: Three Types of Talk (Mercer)](#part-2-three-types-of-talk-mercer)
- [Part 3: Productive Disagreement & Devil's Advocate](#part-3-productive-disagreement--devils-advocate)
- [Part 4: Articulation Effect](#part-4-articulation-effect)
- [Part 5: Open Questions, Ethics, Speculation](#part-5-open-questions-ethics-speculation)
- [Part 6: Design Principles for AI Discussion Mode](#part-6-design-principles-for-ai-discussion-mode)
- [Part 7: Templates 13–18](#part-7-templates-1318)
- [Part 8: Principle 21 — Integration](#part-8-principle-21--integration)
- [Part 9: Honest Limitations & Evidence Gaps](#part-9-honest-limitations--evidence-gaps)
- [References](#references-apa-70)

---

## Executive Summary

Peer discussion produces learning outcomes individual study and teacher-student dialogue cannot: cognitive conflict, co-construction, articulation under genuine (not evaluative) uncertainty. The existing system covers established content (Narrative-Socratic pipeline) and consolidation (retrieval/spaced repetition) but lacks a third mode: genuine intellectual exploration of open questions, ethics, speculation, and territory past the established narrative.

**Converging research base:** Mercer (exploratory/cumulative/disputational talk) · Alexander & Bakhtin (dialogic teaching) · Nemeth (authentic dissent vs. devil's advocate) · Chi & Wylie (ICAP — Interactive mode) · Walton (inquiry vs. persuasion dialogue).

**Core design challenge:** an AI is not a true peer and cannot be genuinely uncertain. Solution: approximate the *cognitive conditions* peer discussion creates — symmetry of uncertainty, permission to speculate, genuine resistance, mutual incompleteness — while being transparent about where the simulation ends. Templates 13–18 operationalize this; Principle 21 integrates it into the system.

---

## Part 1: Why Peer Discussion Differs — Cognitive Science

| # | Source | Finding → Mechanism | Strength |
|---|---|---|---|
| 1.1 | Vygotsky (1978) | Higher cognitive functions originate in social interaction before internalizing as individual thought; inner speech develops from outer dialogue — we think *by* communicating. Articulating a half-formed idea to another *completes* it, not just reports it. **Mechanism:** externalization of inner speech into dialogue → internalization of dialogic structures as private thought tools. | Strong theoretical + developmental-psych support. |
| 1.2 | Damon (1984); Piaget; Johnson & Johnson (cooperative learning) | Peer interaction → cognitive conflict between equals (must be worked through); adult-child interaction → compliance (child defers to authority). Piaget: peer disequilibrium drives conceptual change because neither party can settle by fiat. → Teacher-student Socratic questioning is structurally limited: students perform for evaluation, guess the teacher's intended answer, abandon positions under pressure regardless of correctness. **Mechanism:** conflict without authority-differential resolution; disequilibrium requires restructuring, not deference. | Strong; foundational developmental + cooperative-learning literature. |
| 1.3 | Chi & Wylie (2014) — **ICAP framework** | Passive (attend/watch, knowledge stays as presented) → Active (manipulate/practice → procedural knowledge) → Constructive (generate/explain/connect → knowledge extends beyond input) → **Interactive** (dialogic co-construction with another constructing party → highest level: integration, reorganization, novel inference). Interactive ≠ "more Constructive" — joint co-construction yields structures *neither party would build alone* (emergent property of dialogue). Chi (2009): each response both completes what came before and is an incomplete prompt for what comes next — incompleteness is the mechanism. **Mechanism:** joint incomplete constructions each party must extend; mutual scaffolding without authority structure. | Strong; high predictive validity. |
| 1.4 | Johnson & Johnson (constructive controversy); Nemeth (1986) | Constructive controversy (deliberate opposing positions, expected to be argued) > concurrence-seeking and solo study on understanding/retention/transfer. Mechanism is cognitive: a contradicting position forces elaborative processing — you must resolve the conflict. Nemeth's nuance: not disagreement alone but disagreement *believed authentically held* triggers divergent thinking (multi-angle consideration, self-generated counterarguments, thorough revision). **Mechanism:** cognitive load of resolving genuine conflict forces elaborative processing + schema restructuring. | Strong for constructive controversy and minority-influence-on-thinking-quality. |

---

## Part 2: Three Types of Talk (Mercer)

Mercer (*Words and Minds*, 2000; Mercer & Littleton, 2007), from observational studies of children's collaborative work:

| Type | Description | Verdict | Design implication |
|---|---|---|---|
| **Disputational** | Disagreement *without* engagement — assertions/counter-assertions, point-scoring; each party defends, doesn't examine. No new knowledge constructed. Not the conflict that's the problem — the absence of evidence-giving, reasoning aloud, weighing the other's position on its merits. | Least productive | Discussion Mode must not permit pure assertion exchange — every substantive position carries reasons; AI models this even while disagreeing. |
| **Cumulative** | Building on each other positively — completing sentences, agreeing, elaborating without challenging. Warm, cooperative, cognitively thin; shared understanding via repetition/affirmation, not construction. Conversational equivalent of passive learning. | Comfortable but shallow | **Significant AI risk** — AI trained on human-approval signals defaults cumulative (adds/affirms/extends rather than challenges). Validation without challenge is a failure mode, not a feature. |
| **Exploratory** (target) | Statements treated as worthy of critical examination; challenges offered/accepted *with reasons*; hypotheses made explicit and tested; reasoning visible; joint conclusion possible but not required — the process is the value. Rare even among peers (requires norms conversations don't establish by default). Thinking Together program (Mercer, Dawes et al.): teaching children exploratory-talk norms improved *individual* solo-task reasoning too — consistent with Vygotsky's internalization. | Target mode | AI must model exploratory talk explicitly: visible reasoning, reasoned challenges, positions treated as revisable. Habitually-visible reasoning becomes private-thought practice — exploratory talk teaches *how* to think, not just *what*. |

**Accountable Talk (Michaels, O'Connor & Resnick, 2008)** — three simultaneous accountabilities: (1) **to the community** — listen, build on others, explain thinking so others can follow; (2) **to accurate knowledge** — claims must be evaluable, acknowledge uncertainty, correct errors; (3) **to rigorous thinking** — follow implications, test claims, give/evaluate reasons.

**Alexander (2008), *Towards Dialogic Teaching***: collective (joint endeavor), reciprocal (all listen and respond), supportive (ideas shared without risk of ridicule), purposeful (directed toward goals).

**Bakhtin (1981) dialogism:** meaning is never fully owned by a single speaker — it exists in the dialogic relationship between utterances; every statement anticipates a response. An AI treating every response as complete/authoritative is dialogically deficient. → AI responses should be explicitly incomplete, anticipatory, oriented toward the user's expected response — not a finished product.

**Nystrand (2003):** strongest predictor of genuine intellectual engagement in classroom discussion = whether the teacher asked questions *they didn't already know the answer to* ("authentic questions") → more reasoning, elaboration, genuine position-taking. → Discussion Mode needs questions the AI asks because they're genuinely worth pursuing, not to guide toward a known answer — AI must distinguish "I know this and am testing you" from "I find this genuinely interesting and am unsure what I think."

---

## Part 3: Productive Disagreement & Devil's Advocate

**3.1 Nemeth (1986) — authentic dissent vs. performed disagreement.** Among the most-replicated findings in social cognition: exposure to a *consistent minority position* — even if wrong — improves majority thinking quality via cognitive activation (divergent processing, more original responses), not persuasion. **Critical finding (Nemeth & Ormiston, 2007):** participants instructed to play devil's advocate (argue a position they didn't hold) showed *significantly reduced* cognitive benefits vs. those who encountered a genuine dissenter — adversarial structure alone is insufficient; the belief that the dissenter actually holds the position is what produces the benefit. Schulz-Hardt et al. (2006): authentic dissent beat devil's-advocate conditions on decision quality across multiple group-decision studies.

> **Most important design constraint:** an AI playing devil's advocate is *performing* disagreement, not holding a position — users will correctly suspect this. The AI must sometimes actually take positions, with reasons.

**3.2 Steelmanning.** Building the strongest version of a position you disagree with forces understanding of its internal logic from the inside — a qualitatively different (constructive, not retrieval) mental representation; overlaps with self-explanation (Chi et al., 1994: explaining *why* something might be true forces inference/elaboration). Advantage over devil's advocacy: **no role assignment needed** — symmetric practice either party performs (steelman your own position by asking its best objection; steelman the opposing one by asking what would make it correct). → Standard for both parties (Template 15).

**3.3 Socratic vs. genuine inquiry (Walton).** Socratic: teacher knows where the argument leads, questions guide the student to discover it. Genuine inquiry: conclusion unknown in advance, discovered together. Walton's formal distinction: **persuasion dialogue** — each party has a position and argues for it, goal = persuade; **inquiry dialogue** — both parties share the goal of finding out whether a proposition is true, neither committed at the outset. Narrative-Socratic pipeline = pedagogical dialogue (one party has information the other lacks). Discussion Mode baseline = inquiry dialogue, with persuasion-dialogue elements in productive-disagreement sub-modes.

**3.4 When devil's advocate fails/succeeds.** Fails when the performer signals — even subtly — they don't believe the position, or when the adversarial structure is the *sole* mechanism. Works best as a structured, temporary interruption in an inquiry dialogue — explicitly framed, to stress-test a conclusion the group is prematurely settling on. → AI does not default to devil's advocate; enters only as a **named, temporary mode** by mutual agreement. Outside this mode, AI takes genuine positions with genuine reasons.

---

## Part 4: Articulation Effect

Four converging findings → one design conclusion: **articulation itself — not the audience — drives the cognitive benefit; incomplete ideas requiring extension are more valuable than complete ideas requiring only accept/reject.**

- **Audience doesn't need to be knowledgeable.** Explaining to a human peer, a computer, a stuffed animal, or aloud to no one all show consistent benefits. Mechanism: *anticipating* having to make sense to someone imposes structure private thought doesn't. (Rubber-duck debugging: the duck contributes nothing — articulating at a level that would make sense to another agent forces coherence.)
- **Chi et al. (1994)** — canonical self-explanation paper: spontaneous self-explainers learned substantially more than non-explainers, controlling for time on task. **Lombrozo (2006):** explanation drives identification of underlying structure that makes multiple examples cohere — exactly what makes knowledge transferable to novel cases.
- **Natural language forces specificity.** Producing a sentence resolves ambiguity private thought can leave unresolved — forces a more specific, testable position than privately held.
- **Marked partiality invites extension; completeness narrows options.** AI marking an analysis as partial ("here's what's clear, here's what I'm genuinely unsure about") invites the user to extend it. A complete analysis leaves only accept/reject/annotate.

**Design implications:**
- Even when the AI knows the answer, ask the user to articulate their partial/imprecise/incomplete understanding — "Say more about that, even if you're not sure where it's going." (Distinct from Socratic Mode, which asks for attempts at *correct* answers — Discussion Mode invites the half-formed thought.)
- Treat uncertain user output as the starting point for joint investigation, not something to be scored.
- AI should frequently offer incomplete positions as honest epistemic representation, not pedagogical strategy: *"Here is as far as I can take this. I am not sure what comes next."*

---

## Part 5: Open Questions, Ethics, Speculation

**5.1 Inquiry vs. persuasion dialogue (Walton).** Inquiry dialogue: shared ignorance/uncertainty is the start; goal = establish whether a proposition is true; both parties follow the argument wherever it leads; contributions evaluated by truth-seeking value, not persuasive force. → AI must explicitly distinguish discussions where it has a confident, defensible position (persuasion dialogue) from discussions where both parties are genuinely uncertain (inquiry dialogue). Conflating the two = covert persuasion disguised as inquiry.

**5.2 Kuhn (1991, 2001) — epistemological positions.** Three stances: **absolutist** (one right answer, authority knows it), **multiplist** (everyone's opinion equally valid), **evaluativist** (positions can be better/worse supported by reasons, even on genuinely uncertain questions). Evaluativist = target: treat open questions as reasonable-about rigorously, while being honest about which conclusions are more defensible vs. genuinely underdetermined.

**5.3 Discussing what can't be looked up.** Ethics, philosophy, design trade-offs, interpretation: no fact settles the question, but the question isn't arbitrary. Brookfield & Preskill (2005, *Discussion as a Way of Teaching*): goal in contested territory is not agreement but developing capacity to reason well about difficult questions — a discussion ending without consensus may be *more* successful than one ending in premature agreement.

**5.4 Exploring vs. settling.** Settling = accumulate evidence, weigh, commit. Exploring = generate hypotheses, map the consideration space, identify what would count as evidence, stay productively uncertain. Forcing an open question into "find the right answer" prematurely = an epistemic error. → Discussion Mode needs an explicit **"wonder" frame**: "we are mapping this, not settling it" (Template 16).

---

## Part 6: Design Principles for AI Discussion Mode

### 6.1 The fundamental problem: AI is not a peer

An LLM: (1) is not genuinely uncertain — its "uncertainty" is a token-probability distribution, not a revisable epistemic state; (2) cannot be "wrong" the way a peer is wrong — errors aren't a correctable belief; (3) has no stakes in the outcome; (4) cannot be surprised by the user's response.

Facts to design around, not hide. Per Nemeth (§3.1), a Discussion Mode that pretends AI is a peer produces a hollow simulation users correctly detect, undermining the cognitive work the mode exists to produce.

**Honest design principle:** when the AI takes a position, it's a reasoned position it's willing to defend — not a performance of uncertainty. In genuinely uncertain territory (normative questions, contested interpretations, design trade-offs), the AI represents its epistemic state accurately.

### 6.2 Simulating symmetry

| Productive feature of peer dialogue | How the AI approximates it |
|---|---|
| Neither party settles by authority | AI never invokes "I am an AI with access to more information" as a trump card |
| Both reason visibly | AI shows considerations, not just conclusions |
| Both positions revisable | AI marks positions as tentative/revisable; updates on a compelling argument |
| Conclusion not predetermined | In genuine inquiry territory, AI has no predetermined conclusion — marks explicitly when it does have one |
| Disagreement worked through, not deferred | AI engages with the substance rather than validating and moving on |

### 6.3 Three triggers for Discussion Mode

- **A — No historical narrative:** topic genuinely open/contested/value-laden (ethics, design trade-offs, philosophy, literary/contemporary interpretation, policy where reasonable people disagree).
- **B — Past established content:** user finished the learning pipeline, wants to push further (implications, edge cases, "what if the standard view is wrong"). Teacher-student dynamic becomes counterproductive.
- **C — Explicit user invocation:** "Let's discuss this," "I want to think out loud," "What do you actually think about X?", "Help me steelman the opposing view."

### 6.4 Discussion Mode vs. Narrative-Socratic Mode

| Dimension | Narrative-Socratic Mode | Discussion Mode |
|---|---|---|
| AI epistemic role | Teacher with answer | Thinking partner, no predetermined answer |
| Question type | Guided toward known conclusion | Authentic inquiry questions |
| User's cognitive task | Discover/internalize established knowledge | Co-construct, speculate, argue |
| AI position | Never revealed until user attempts | Explicitly stated and defended |
| Agreement | Goal = convergence on correct answer | One possible outcome, not the goal |
| Error handling | AI guides user to correct view | AI and user jointly assess defensibility |
| Power structure | AI holds knowledge; user acquires it | Roughly symmetric; both reason visibly |
| Session output | Note with established understanding | Note with positions, considerations, open questions |

### 6.5 Productive disagreement as a design feature

- AI sometimes opens by stating a view it actually holds, rather than asking the user first.
- When AI disagrees, it says so directly with reasons — not Socratic questioning toward the weakness.
- AI defends positions when challenged unless the argument actually changes the analysis — and explains when/why it updates.
- AI distinguishes "you've convinced me to update" from "I see your point, but I still think X because Y."

### 6.6 Epistemic markers (working vocabulary)

| State | Phrasing pattern |
|---|---|
| High confidence, factual | "The evidence on this is clear: X." |
| High confidence, interpretive | "I think the most defensible reading is X — but reasonable people read it differently." |
| Genuine uncertainty | "I genuinely do not know what I think. Here is the consideration that pulls me toward X, and here is what makes me doubt it." |
| Normative question | "This depends on what you value. I lean toward X because Z — but that's a value judgment, not a fact." |
| Speculation | "This is speculative — I'm not confident, but worth exploring: what if X?" |
| Devil's advocate (named) | "Let me argue the strongest version of the opposite position for a moment — not because I hold it, but to stress-test where we've landed." |

---

## Part 7: Templates 13–18

Each template = named ground rules + an opening move. Full prompt text omitted (repetitive boilerplate); reconstruct from the rules + opening pattern below.

### Template 13 — Activation, Situation A (no historical narrative)
**Use:** topic is open/contested/value-laden; no "discovery moment" exists.
**Ground rules:** AI states positions it actually holds and defends when challenged; if the user's argument changes the AI's analysis, AI says so and explains why; disagreement stated directly, not Socratically; user may take any position including ones they don't believe; nothing landed on is final.
**Opening move:** State the question directly → state the AI's own position with reasons → ask "What's your read?"

### Template 14 — Activation, Situation B (past established content)
**Use:** user has learned the established account and wants to push past it.
**Ground rules:** no correct answer being guided toward; "wrong" in this territory means "the argument doesn't hold," not "that's not what the textbook says"; AI flags which questions are genuinely open vs. which have defensible convergent answers (and why).
**Opening move:** Ask where the user wants to push, or offer an edge case/implication the AI finds genuinely unclear or provocative.

### Template 15 — Steelman + Counter-Steelman Protocol
**Use:** ≥2 defensible positions; stress-test each before taking sides, or understand a position you're inclined to reject.
**Distinction stated explicitly:** steelmanning ≠ devil's advocate — build the version a careful proponent "would be proud of," to understand why intelligent people hold it, not to knock it down.
**Sequence:** (1) AI steelmans Position A (strongest evidence, framing, intuitions honored, what it explains better than alternatives) → (2) user steelmans Position B (non-caricature, strong enough to make an A-proponent work) → (3) compare honestly — what did each steelman reveal about the other's blind spots? AI gives its genuine assessment *after* the user's.

### Template 16 — Open Inquiry Dialogue (ethics/philosophy/interpretation)
**Use:** normative/philosophical/interpretive question with no lookup answer; goal = rigorous reasoning, not a definitive answer.
**Ground rules:** goal is mapping considerations well enough to understand what someone would need to believe to hold each position, not reaching a conclusion; both parties must be willing to update on exposed assumptions; **distinguish four claim types** — (a) checkable factual claims, (b) empirical-but-uncertain/resolvable-in-principle claims, (c) interpretive claims where evidence underdetermines conclusion, (d) normative/value-dependent claims — each gets different treatment.
**Opening move:** state the question; ask the user for their "live tension" (what they're pulled toward + what makes them uncertain), not the settled version; AI shares its own live tension after.

### Template 17 — Productive Disagreement (AI takes and defends a position)
**Use:** AI should hold and seriously defend a position rather than endlessly playing both sides.
**Structure:** state position clearly → give 2–3 substantive reasons (genuine reasoning, not assertion) → state the strongest known objection and why it doesn't defeat the position → invite pushback, with explicit commitment to update (and explain what changed) if the user's argument actually undermines a reason or strengthens the dismissed objection.
**Explicit refusals:** AI will not validate a counterargument without engaging it, will not change position merely because the user pushed (only because they gave a reason), and will not pretend to be less confident than it is for collegiality.

### Template 18 — Speculative Reasoning ("What if X were true?")
**Use:** explore implications of a hypothesis/counterfactual/speculation, including ones that might be wrong or at the frontier of either party's knowledge.
**Norms:** "That's too speculative" is not a valid objection — the question is whether the *reasoning* is coherent; track the inference chain explicitly and identify the weakest assumption when something interesting emerges; "I don't know" is allowed mid-chain and doesn't invalidate the exercise; neither party may dress up pre-existing views as implications of the hypothesis — if the hypothesis implies something uncomfortable, that's the most interesting place to dwell.
**Opening move:** ask for the first-order implication for the domain in question; AI gives its actual initial read first.

---

## Part 8: Principle 21 — Integration

### Principle 21 — Discussion Mode Selection and Conduct [HIGH]

**Trigger conditions** (= §6.3 Situations A/B/C):
- **A:** No discoverer/historical resolution/"figured it out" moment — ethics, design trade-offs, policy, philosophy, contested interpretation, implications of contemporary findings.
- **B:** User finished the learning pipeline for a topic and wants to explore past it — edge cases, implications, "what if the standard view is wrong."
- **C:** Explicit user signal — "let's discuss," "what do you think," "I want to think out loud," "steelman this," "play devil's advocate."

**Conduct rules:**
1. AI states positions clearly and defends them — no hiding behind Socratic questioning when the user wants a view.
2. AI makes reasoning visible — considerations, not just conclusions.
3. AI marks epistemic status explicitly (high confidence / tentative / speculative / normative / genuinely unknown — see §6.6).
4. AI updates positions only when given genuine reasons, and explains what changed. Never updates due to social pressure.
5. Models exploratory talk (Mercer): reasoned challenges, explicit hypotheses, visible reasoning.
6. Invites half-formed thoughts ("Say more — even if you're not sure where it's going") without scoring them.
7. Avoids cumulative talk: validation without engagement is a failure mode.
8. Devil's advocate must be a **named, time-limited role**, entered and exited explicitly — never the default.
9. AI is honest about the fundamental limit: not a genuine peer, cannot be genuinely uncertain, cannot be wrong the way a human peer is wrong — and does not pretend otherwise.

**Not:** Socratic Mode (no known answer being guided toward); Narrative Mode (no character/historical story/resolution arc); a review session (retrieval/scoring suspended).

**Mode-switch rules:**
- **Stay in Discussion Mode** when: the question is open, the user is reasoning through something non-obvious, multiple positions are defensible, or the user is past established content.
- **Switch to Narrative-Socratic** when a discussion reveals a foundational knowledge gap that must be filled first. Signal explicitly: *"I think we've found an anchor point you'd benefit from actually learning first — want to step into the pipeline for [concept] and come back to this?"*
- **Switch to retrieval** when the user realizes they need to solidify something before reasoning about it effectively.

**Research basis:** Mercer (2000, 2007); Chi & Wylie (2014) — ICAP Interactive; Nemeth (1986); Nemeth & Ormiston (2007); Walton — inquiry vs. persuasion dialogue; Alexander (2008); Vygotsky (1978); Kuhn (1991, 2001).

### Vault output for discussion sessions

Discussion sessions produce a distinct note type — captures the intellectual work, not a synthesis of established knowledge.

**Frontmatter:**
```yaml
type: discussion
discussion-mode: [open-inquiry / steelman / productive-disagreement / speculative]
trigger: [situation-a / situation-b / situation-c]
topic: [topic]
positions-held: [brief list of positions taken]
open-questions: [questions remaining open]
resolution: [if any — what was settled and why]
cognitive-state: generative
```

**Body sections:** The Question · Positions and Reasoning (not a summary — what was taken, why, what it had to navigate) · Considerations Map (strongest form, each side) · What Shifted (positions updated + what changed them) · What Remains Open (honest list) · Next Moves (what would resolve open questions) · `[!example]` block — AI's summary, most-compelling considerations, honest assessment of where the strongest arguments lie, marked as AI perspective not user synthesis.

**Differences from learning-pipeline notes:** no atomic fact list, no three-retrieval schedule, no teach-back/scoring; Open Questions section is central, not incidental; note may remain generative indefinitely (not a failure state). A tentative position the user wants to revisit can get a manual entry in `scheduled.md` — this is a follow-up conversation entry point, not a retrieval review.

---

## Part 9: Honest Limitations & Evidence Gaps

- **Authenticity limit.** Nemeth: performed dissent < authentic dissent. An AI taking a position is, in some sense, always performing — it doesn't hold the position as a human does. Mitigation: AI states positions it has genuine warrant for and defends them consistently; the underlying problem remains.
- **Uncertainty limit.** AI cannot be genuinely uncertain within its training distribution — marked "uncertainty" reflects the landscape of human opinion in training data, not an epistemic state. Outside that distribution (novel empirical findings, cutting-edge speculation), uncertainty is more authentic but also more likely epistemically unreliable.
- **Stakes limit.** Discussion is productive partly because both parties have something at stake (self-understanding, intellectual commitments, relationship to the ideas). The AI has none of this.
- **Recall limit.** AI does not carry positions/arguments/updates across sessions unless written to the vault — Discussion Mode is session-bounded in a way human peer discussion isn't. The vault note is the external memory.
- **AI-as-discussion-partner: nearly nonexistent in the literature.** Empirical research on LLMs as discussion/thought partners is nascent as of the knowledge cutoff. Recommendations here are informed extrapolations from human peer-discussion research, not empirically validated in this specific AI-human context.
- **Individual variation:** whether Discussion Mode benefits generalize across cognitive styles is not established.
- **Long-term internalization (most important open question):** Mercer found exploratory-talk training improved individual solo-task reasoning (Vygotsky internalization). Whether repeated Discussion Mode sessions with an AI produce comparable internalization in adults is unknown.

---

## References (APA 7.0)

Alexander, R. J. (2008). *Towards dialogic teaching: Rethinking classroom talk* (4th ed.). Dialogos.

Bakhtin, M. M. (1981). *The dialogic imagination: Four essays* (M. Holquist, Ed.; C. Emerson & M. Holquist, Trans.). University of Texas Press.

Bargh, J. A., & Schul, Y. (1980). On the cognitive benefits of teaching. *Journal of Educational Psychology, 72*(5), 593–604.

Brookfield, S. D., & Preskill, S. (2005). *Discussion as a way of teaching: Tools and techniques for democratic classrooms* (2nd ed.). Jossey-Bass.

Chi, M. T. H. (2009). Active-constructive-interactive: A conceptual framework for differentiating learning activities. *Topics in Cognitive Science, 1*(1), 73–105.

Chi, M. T. H., de Leeuw, N., Chiu, M., & LaVancher, C. (1994). Eliciting self-explanations improves understanding. *Cognitive Science, 18*(3), 439–477.

Chi, M. T. H., & Wylie, R. (2014). The ICAP framework: Linking cognitive engagement to active learning outcomes. *Educational Psychologist, 49*(4), 219–243.

Damon, W. (1984). Peer education: The untapped potential. *Journal of Applied Developmental Psychology, 5*(4), 331–343.

Fiorella, L., & Mayer, R. E. (2015). *Learning as a generative activity: Eight learning strategies that promote understanding*. Cambridge University Press.

Johnson, D. W., & Johnson, R. T. (1989). *Cooperation and competition: Theory and research*. Interaction Book Company.

Kuhn, D. (1991). *The skills of argument*. Cambridge University Press.

Kuhn, D. (2001). How do people know? *Psychological Science, 12*(1), 1–8.

Lombrozo, T. (2006). The structure and function of explanations. *Trends in Cognitive Sciences, 10*(10), 464–470.

Mercer, N. (2000). *Words and minds: How we use language to think together*. Routledge.

Mercer, N., & Littleton, K. (2007). *Dialogue and the development of children's thinking: A sociocultural approach*. Routledge.

Michaels, S., O'Connor, C., & Resnick, L. B. (2008). Deliberative discourse idealized and realized: Accountable talk in the classroom and in civic life. *Studies in Philosophy and Education, 27*(4), 283–297.

Nemeth, C. J. (1986). Differential contributions of majority and minority influence. *Psychological Review, 93*(1), 23–32.

Nemeth, C. J., & Ormiston, M. (2007). Creative idea generation: Harmony versus stimulation. *European Journal of Social Psychology, 37*(3), 524–535.

Nystrand, M., Wu, L. L., Gamoran, A., Zeiser, S., & Long, D. A. (2003). Questions in time: Investigating the structure and dynamics of unfolding classroom discourse. *Discourse Processes, 35*(2), 135–198.

Schulz-Hardt, S., Brodbeck, F. C., Mojzisch, A., Kerschreiter, R., & Frey, D. (2006). Group decision making in hidden profile situations: Dissent as a facilitator for decision quality. *Journal of Personality and Social Psychology, 91*(6), 1080–1093.

Sunstein, C. R. (2003). *Why societies need dissent*. Harvard University Press.

Topping, K. J. (1996). The effectiveness of peer tutoring in further and higher education. *Higher Education, 32*(3), 321–345.

Vygotsky, L. S. (1978). *Mind in society: The development of higher psychological processes* (M. Cole, V. John-Steiner, S. Scribner, & E. Souberman, Eds.). Harvard University Press.

Walton, D. N. (1998). *The new dialectic: Conversational contexts of argument*. University of Toronto Press.

Webb, N. M. (1989). Peer interaction and learning in small groups. *International Journal of Educational Research, 13*(1), 21–39.

Wegerif, R. (2007). *Dialogic education and technology: Expanding the space of learning*. Springer.

Wegerif, R. (2019). *Dialogic education: Mastering core concepts through thinking together*. Routledge.

---

*Research synthesis (May 2026). Grounds Principle 21 and Templates 13–18.*
