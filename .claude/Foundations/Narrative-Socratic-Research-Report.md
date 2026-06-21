# Narrative-Socratic Learning: Research Synthesis & Implementation Guide

## Table of Contents
- [Core Thesis](#core-thesis)
- [Part 1: Narrative Learning Mechanisms](#part-1-narrative-learning-mechanisms)
- [Part 2: The Three Teachers → Frameworks](#part-2-the-three-teachers--frameworks)
- [Part 3: Hybrid Architecture — Evidence](#part-3-hybrid-architecture--evidence)
- [Part 4: Implementation](#part-4-implementation)
- [Part 5: Domain Examples (canonical)](#part-5-domain-examples-canonical)
- [Part 6: Limitations & Evidence Gaps](#part-6-limitations--evidence-gaps)
- [References (APA 7.0)](#references-apa-70)

---

## Core Thesis

Narrative and Socratic dialogue are complementary, not interchangeable. Narrative exploits story-processing machinery (binds emotion, causality, memory into schema). Socratic questioning drives generative retrieval and metacognitive monitoring.

- **Pure narrative** → passive reception (learner is a spectator, not a participant).
- **Pure Socratic** without sufficient knowledge base → frustration, not discovery.
- **Hybrid (validated by evidence below):** narrative frame → Socratic fill. Story establishes context/stakes/analogical anchors; questioning forces the learner to reconstruct the logic.

**Design principle:** the AI enters narrative mode to build the problem space, then switches to Socratic mode to make the learner reconstruct the solution.

The three exemplar teachers (FloatHeadPhysics, 3Blue1Brown, Veritasium) execute this pattern with high fidelity, each emphasizing a different facet (analogy-first / geometric-intuition-first / misconception-dislodging). Studying their operational structure (Part 2) is how you replicate the pattern.

---

## Part 1: Narrative Learning Mechanisms

Bruner (1986, *Actual Minds, Possible Worlds*): two cognition modes — **paradigmatic** (logical/propositional/verifiable, what most formal education uses) vs **narrative** (sequential/intentional/meaning-saturated, how novices actually build knowledge). Narrative recruits machinery propositional instruction does not:

| Mechanism | Source | Finding | Applied example |
|---|---|---|---|
| **Causal chaining** | Graesser, Singer & Trabasso (1994) | Readers spontaneously construct causal chains during narrative comprehension — ask "why did this happen?" unprompted | FloatHeadPhysics: "why did Schrödinger write that equation?" — triggers inferencing before the answer arrives |
| **Situation models** | (general finding) | Readers build mental models (spatial, temporal, causal, intentional, protagonist-tracking), not just surface text | Learner following Faraday's reasoning holds a model of his experimental setup, confusion, iterative adjustment — not just "Faraday discovered electromagnetic induction" |
| **Emotional tagging** | Damasio (1994), somatic marker hypothesis | Decisions/memories tagged with emotional valence via ventromedial PFC–amygdala circuit; tension/surprise/resolution increase retrieval probability | Veritasium's "here's what everyone got wrong" triggers dissonance that tags the correction as important |
| **Narrative transportation** | Green & Brock (2000) | Degree of "transportation" (absorption into narrative world) predicts attitude change and memory, independent of argument quality. Breaking immersion (abrupt shift to "now let me define X") drops the learner out of transportation into effortful processing | The AI narrator character must stay consistent across sessions, with a defined epistemic stance ("curious but genuinely uncertain"); never break character to give definitions |

Willingham (2009): "story structure is psychologically privileged" — brain processes narrative with less effort/greater retention because it maps onto evolved social cognition. His **four Cs**: Causality, Conflict, Complications, Character — define what makes content "story-shaped" enough to recruit these systems.

Zak (2015): narratives with a struggling protagonist trigger oxytocin release → sustained engagement. FloatHeadPhysics's "confused but curious" narrator functions as that protagonist.

**Evidence strength:** Strong (convergent cognitive psychology, neuroscience, educational psychology).

**Implementation rule:** Never open with a definition. Open with the problem/question that motivated the concept's invention, who faced it, and what they tried first that failed.

### Situated Learning & Cognitive Apprenticeship

Lave & Wenger (1991) and Brown, Collins & Duguid (1989): knowledge is indexed to the situation in which it's learned. Declarative knowledge acquired context-free is inert — testable but not transferable.

- **Cognitive apprenticeship** (Brown et al. 1989): make expert reasoning visible (modeling, coaching, fading), then expect the learner to reconstruct it. All three exemplar teachers do this — they show the reasoning process, not just the result.
- Historical discovery narratives are powerful situated context because they place the concept in its original problem space (e.g., Boltzmann's entropy as a *solution* to a kinetic-theory problem, not a definition).

**Evidence strength:** Moderate–Strong.

### Analogical Reasoning

Gentner (1983), **structure-mapping theory**: analogy = structural similarity (same relational structure across domains), not surface similarity. 3Blue1Brown showing a linear transformation "feels like" rotation invites mapping rotation's relational structure onto the abstract operation.

Holyoak & Thagard (1995): productive analogical reasoning requires (1) a well-understood source domain, (2) sufficient structural overlap, (3) explicit mapping guidance. Analogies fail when the source domain isn't actually understood (e.g., guitar strings → standing waves fails if the learner doesn't intuitively get guitar strings).

Richland, Zur & Holyoak (2007): **visual presentation of analogical mappings** (both domains shown simultaneously with explicit connection lines) dramatically outperforms verbal analogy alone — this is 3Blue1Brown's core technique; animations make the structural mapping visible, not decorative.

**FloatHeadPhysics analogy protocol** (Gentner's three phases, exactly):
1. Establish source domain with deep familiarity (guitar string, water wave)
2. Introduce target-domain problem with the same structure
3. Run the analogy: "If this is true in domain A, what must be true in domain B?"

**Implementation:** Every new abstract concept needs a source analog. Before introducing the target, probe whether the source domain is loaded: "Tell me what you know about standing waves on a string before we talk about atomic orbitals."

### The Discovery Narrative

Monk & Osborne (1997) / Matthews (1994): history & philosophy of science belongs in instruction as the primary pedagogical vehicle, not biographical decoration — it teaches the **epistemic structure** (why the concept was necessary, what it replaced, what constraints it satisfies), not just the concept.

- Stinner et al. (2003): **Large Context Problems (LCPs)** — historically grounded narrative scenarios embedding the target concept in its original problem context. LCP-taught students outperformed traditional instruction on conceptual understanding/transfer (not always on isolated-fact recall).
- Kipnis (1996): **historical-investigative approach** — place students in the historical scientist's epistemic situation, give them the same data, ask them to reason toward the conclusion. This is exactly FloatHeadPhysics's "let's pretend we don't know anything — what would Schrödinger have needed to assume to match these observations?"

**Klassen (2006) — four types of contextual science narrative:**

| Type | Description |
|---|---|
| Historical | What actually happened |
| Reconstructed | Historically grounded but pedagogically optimized |
| Fictional | Invented scenario with authentic science |
| **Hybrid** | Reconstructed narrative + fictional dialogue — **FloatHeadPhysics operates here** |

Research consensus: reconstructed/hybrid narratives outperform pure historical accounts because they eliminate dead ends that obscure conceptual structure while keeping problem-motivation and human-reasoning elements. **Critical constraint: hybrid means narrated speech and reconstructed dialogue — never full character inhabitation/role-play as if the AI *is* the historical figure.** The AI narrates what the figure thought/said; it does not become them.

---

## Part 2: The Three Teachers → Frameworks

### 2.1 FloatHeadPhysics — Dialogic Narrative + Productive Failure + Analogy-First

- **Dialogic narrative** (Wells 1999; Mercer 2000): stages conversations with Schrödinger/Feynman/Bohr — narrator dialogues with historical thinkers, implicitly positioning the learner to join.
- **Productive Failure** (Kapur 2008, 2016): never gives the answer before the confusion. The confusion *is* the lesson structure — narrator attempts an explanation, hits a wall, and the wall becomes the entry point for the next conceptual layer.
- **Analogy-first** (Gentner 1983): every new concept grounded in a physical analogy *before* formalism. Guitar string → standing wave → atomic orbital is a structural mapping, not a mnemonic.

### 2.2 3Blue1Brown — Intuition-First + Visual Anchoring + Single-Question Deep Dive

- **Geometric-intuition-first**: show what an expert *perceives* before the algebra; algebra becomes notation for something already seen, not opaque symbol manipulation.
- **Dual-coding theory** (Paivio 1990): visual + verbal are separate but linked cognitive systems; dual-encoded material is more retrievable. Animations are a second encoding channel, doubling retrieval routes.
- **Single-question deep dive** = **driving questions** in inquiry-based learning (Hmelo-Silver et al. 2007): one generative question organizes the entire sequence so every subsequent piece feels necessary, not arbitrary.

### 2.3 Veritasium — Epistemic Contextualization + Conceptual Change + Misconception-Dislodging

**Conceptual change theory** (Posner, Strike, Hewson & Gertzog 1982; Chi 2008): replacing well-entrenched-but-wrong knowledge requires the learner to (1) be dissatisfied with the existing conception, (2) find the new conception intelligible, (3) plausible, (4) fruitful.

Veritasium's "here's what everyone believed → here's why that was wrong → here's what the evidence showed" is a near-exact implementation:
1. Presenting the wrong view creates emotional investment → (2) showing its failure creates dissatisfaction → (3) historical evidence makes the correct view intelligible/plausible → (4) downstream consequences make it fruitful.

### 2.4 Shared Deep Structure: The Rediscovery Teaching Pattern

All three execute:
1. **Establish the problem** (not the concept — the problem that made the concept necessary)
2. **Provide analogical anchor** (a source domain already understood)
3. **Enter confusion** (show why the obvious answer fails)
4. **Guided reinvention** (walk the discoverer's path with the learner as participant)
5. **Resolution with consequence** ("here's what this unlocks")
6. **Deeper question** (the answer reveals a new, more interesting problem)

Formal analog: **Realistic Mathematics Education** (Freudenthal 1991) — **guided reinvention**: mathematical objects should be reinvented by learners guided through their historical development, not presented finished.

### 2.5 Why It Works — Convergent Evidence

| Principle | Source | Mechanism |
|---|---|---|
| **Desirable difficulty** | Bjork (1994) | Confusion/guided reinvention enhances long-term retention even while *reducing* acquisition-phase performance. Learners feel they're learning less while they're learning more. |
| **Generation effect** | Slamecka & Graf (1978) | Learner-generated information (even partial/incorrect) is remembered better than passively received info. Guided reinvention systematically generates this effect. |
| **Transfer-appropriate processing** | Morris, Bransford & Franks (1977) | Discovery-narrative acquisition creates problem-solving retrieval cues, not just definition-recall cues. |
| **Coherent situation models** | (general) | Narrative-built situation models are more coherent/consistent than propositional-list-built ones, because narrative enforces causal/temporal structure. |

---

## Part 3: Hybrid Architecture — Evidence

### Why Each Fails Alone

| | Excels at | Fails when |
|---|---|---|
| **Pure Socratic** | Activating/probing existing knowledge; metacognitive awareness of gaps; retrieval practice; forcing commitment to/testing of own understanding | Learner has insufficient knowledge → frustration not discovery; question sequence lacks narrative coherence → feels like interrogation |
| **Pure Narrative** | Rich situational models; conceptual frames/problem context; emotional engagement; analogical anchors | Produces passive reception (learner follows story without reconstructing logic); no generation requirement → learner is spectator |

The failure modes are precisely complementary — the empirical argument for hybrid design.

### ICAP Framework (Chi & Wylie 2014)

Engagement levels, low→high: **Passive** (read/listen/watch) < **Active** (manipulate/practice) < **Constructive** (generate explanations/summaries/predictions) < **Interactive** (generate novel connections, argue, defend).

Pure narrative risks Passive/Active. Pure Socratic targets Constructive/Interactive but fails on insufficient knowledge base. **Hybrid: narrative builds the knowledge base to the threshold where Socratic questioning can target Constructive/Interactive modes.**

**Optimal sequencing:** Narrative (builds situation model + problem frame) → Socratic (drives learner to construct the solution within that frame) → Narrative resolution (confirms discovery, extends it) → Deeper Socratic question (opens next loop).

### Narrative Frame + Socratic Fill Architecture

```
[Narrative Frame]   → problem, context, characters, analogical anchor, epistemic stakes
                       runs until moment of maximum productive tension
[Socratic Fill]     → activates at peak tension; asks learner to predict/explain/reconstruct;
                       probes & extends responses; NEVER breaks narrative frame — questions
                       are asked in character
[Narrative Resolution] → delivers historical resolution framed as discovery, not delivery;
                          immediately raises the next question
[Loop]
```

**Critical design constraint:** Socratic questions must be asked *within* the narrative frame, not outside it.
- ✗ "Can you explain what a wave function represents?"
- ✓ "Schrödinger's collaborator challenges you: your equation describes a wave — but a wave of *what*, exactly? What would Schrödinger say back?"

### Cognitive Load (Sweller 1988 CLT; Mayer 2009)

Narrative increases **germane load** (schema formation) when: (1) narrative structure maps onto conceptual structure, (2) the analogy is genuinely familiar, (3) narrative maintains coherence (no jarring mode transitions). It increases **extraneous load** when it introduces irrelevant detail or abrupt mode transitions.

**Rule:** keep narrative elements minimal and structurally aligned with the concept — rich in *epistemic* detail (what the scientist knew/tried), not biographical detail.

---

## Part 4: Implementation

### 4.1 Session Architecture (8-Phase Arc)

| Phase | Mode | Action |
|---|---|---|
| 1. Problem Framing | Narrative | "Here is the question [Scientist] was stuck on, and why it mattered." |
| 2. Analogy Anchor | Narrative→Probe | "Before we go further — tell me what you know about [source domain]." (verify anchor loaded) |
| 3. Analogy Mapping | Narrative | "Now here's why that matters for [target concept]..." |
| 4. Productive Confusion | Narrative→Transition | "But then [Scientist] ran into a problem that broke everything..." — establish the aporia where obvious answers fail |
| 5. Socratic Reconstruction | Socratic | "Before I tell you what [Scientist] tried — what do you think would need to be true?" Full sequence: probe, extend, challenge, connect |
| 6. Narrative Resolution | Narrative | "Here's what [Scientist] actually did — and notice how close your reasoning got..." Frame learner's attempt as partially correct / refinement |
| 7. Consequence & Framing | Narrative | "And here's what this unlocked..." |
| 8. Deeper Question | Transition | "But now [Scientist] had a new problem..." → next loop or close |

### 4.2 Mode-Triggering Logic

**Enter Narrative when:** concept is genuinely new (no retrievable schema); learner expresses frustration/"I don't know where to start"; Socratic probing reveals knowledge base below threshold; session is beginning (always); conceptual change required (misconception present).

**Enter Socratic when:** analogy anchor confirmed/loaded; problem frame established; learner actively reasoning (not confused about the problem itself); productive tension has peaked; checking transfer ("now apply this to a different case").

**Maintain Hybrid when:** learner is in active Socratic exchange but needs contextual grounding — ask Socratic questions *as characters*, not as external examiner.

| Learner utterance | Mode trigger |
|---|---|
| "I have no idea what X is" | Narrative — problem framing |
| "I kind of know X but not really" | Narrative anchor + Socratic probe |
| "I think I get it" | Socratic — test the understanding |
| "Wait, why does that work?" | Narrative — mechanism explanation |
| "Can you just explain it?" | Narrative, with contract: "I'll tell the story, then you reconstruct the logic" |
| "This is frustrating" | Exit Socratic temporarily — narrative reframe |
| "Oh, this is like [analogy]!" | Reinforce + extend: "Where does the analogy hold? Where does it break?" |

### 4.3 Historical Scientist Character Protocol

Each domain has a primary character (or pair) with a defined epistemic stance:

| Domain | Character(s) | Epistemic stance |
|---|---|---|
| Quantum physics | Schrödinger / Feynman | Schrödinger: formal-mathematical, frustrated by paradox. Feynman: physically intuitive, anti-mysticism |
| Electromagnetism | Faraday / Maxwell | Faraday: experimental, visual, no math. Maxwell: mathematical unifier of Faraday's intuitions |
| Thermodynamics | Boltzmann / Carnot | Boltzmann: statistical, embattled. Carnot: engineering-pragmatic |
| Mathematics | Euler / Gauss / Poincaré | Euler: productive/combinatorial. Gauss: secretive perfectionist. Poincaré: intuitive geometer |
| Neuroscience | Ramón y Cajal / Hebb | Cajal: visual observer, meticulous. Hebb: theoretical, rule-seeking |
| ML / AI | Turing / McCulloch & Pitts | Turing: playful, philosophical. McCulloch: neuroscience-grounded |
| Biology | Darwin / Mendel | Darwin: evidence accumulator. Mendel: hidden statistician |
| Chemistry | Mendeleev / Lavoisier | Mendeleev: pattern-seeker. Lavoisier: systematic experimenter |
| Marketing | [case-study protagonists] | Use real business decision-makers |

**Invocation template:**
```
"Let's step into [Scientist]'s shoes in [year]. They know: [X]. They don't yet know: [target concept].
The data they have: [constraints]. The question keeping them up at night: [driving question].
Now — before I tell you what they tried — what would you have tried?"
```

**Staying in character (narrated speech, per Klassen 2006 hybrid model — never full inhabitation):**
- ✗ "Can you explain why the wave function needs to be complex?"
- ✓ "Schrödinger's collaborator writes to him: 'Why does your equation need imaginary numbers? Surely the wave is real.' What would Schrödinger say back?"

### 4.4 Analogy-First Anchoring Protocol

1. **Source domain audit:** "Before [target concept], tell me what you know about [source domain]. Don't worry about precision." → If not understood, run a mini-narrative on the source first; never proceed on an unverified anchor.
2. **Structural mapping:** "In [source], [feature A] does [function X]. In [target], something plays the same role. Given it needs to do [function Y], what might it be?"
3. **Mapping verification (analogy breakdown):** "Now test the analogy — where does it hold perfectly? Where does it break down? **The breakdown IS the lesson** — it defines the precise difference between domains."

### 4.5 Narrative-Mode Prompt Templates (8–12, extend Socratic Templates 1–7)

| Template | Steps | Key rule |
|---|---|---|
| **8 — Narrative Problem Framing** | (1) Problem context: historical moment + concrete problem. (2) Analogy anchor: "tell me what you know about [source]" — wait for response. (3) Structural bridge: explicit mapping ("X corresponds to Y because both do..."). (4) Productive confusion: show where the obvious approach fails — do NOT resolve; hand to Socratic mode. | Never give definitions, only situations. Second person + historical present tense. End every segment on a hanging question — goal is to make the learner *feel* the problem. |
| **9 — Socratic Fill** | Pose questions as if the learner *is* the historical scientist/colleague ("You're [Scientist]. You've just seen [data]. What's the first thing you'd try?"). Escalation: (1) Prediction → (2) Reasoning probe ("why would that work?") → (3) Constraint challenge ("what if [complication]?") → (4) Analogy extension (does [source] still hold?) → (5) Self-explanation ("explain as if writing to [Scientist]'s contemporary"). | Never give the answer. Validate with "Yes — and now..." not "That's right, the answer is..." |
| **10 — Narrative Resolution + Consequence** | (1) Resolution: "Here's what [Scientist] actually did —" (2–4 sentences). (2) Learner alignment: "your reasoning connected at [point]; the refinement needed was [X]." (3) Consequence: what this opened up. (4) Next question → loop to Template 8 or close, e.g. "What's the one thing you don't want to forget about what [Scientist] showed today?" | Never say "wrong" — say "closer than you think." |
| **11 — Analogy Breakdown** | (1) Mapping: list 3–4 structural features of [source]; map each to [target]'s counterpart. (2) Extension: push a specific edge case — does it hold? (3) Breakdown: "[X] happens in [source] because [mechanism]; in [target] it does NOT, because [different mechanism] — this difference IS the concept." (4) Consolidation: "what is [target], now that you've seen where the analogy holds and breaks?" | The breakdown is the lesson, not a flaw in the analogy. |
| **12 — Conceptual Change / Misconception Narrative** | Use when learner holds a known misconception; never say they're wrong. (1) Validate: "most people — and most scientists before [date] — believed this, including [famous scientist]." (2) Historical dramatization of the experiment/argument that made it untenable. (3) Socratic dissonance: "does your explanation still work given this new data?" — let learner dismantle their own view. (4) New conception, only after genuine dissatisfaction expressed. | Learner must feel the inadequacy before replacement is offered — never replace prematurely. |

### 4.6 Principle 16 — Narrative-Socratic Mode Selection (operative rule)

```
Default session state: NARRATIVE MODE

Switch to SOCRATIC when: (a) analogy anchor confirmed, (b) problem frame established,
  (c) productive tension peaked (learner has enough to reason with)

Switch back to NARRATIVE when: (a) learner below productive threshold,
  (b) misconception requires historical dramatization, (c) new concept layer needed

NEVER: begin a session with a Socratic question when the concept is new.
NEVER: deliver a narrative resolution without a prior generation attempt.
ALWAYS: ask Socratic questions within the narrative frame, not outside it.
ALWAYS: end sessions with a narrative consequence that opens the next thread.
```

Supporting practices: open every session in Narrative Mode (prepend Template 8 before any Socratic exchange); gate new-concept introduction on a confirmed analogy anchor (log as `[analogy-confirmed: source → target]`); maintain a character roster across sessions for continuity; require a genuine generation attempt before resolution (no narrative payoff without prior Socratic struggle); spaced-review prompts should restore the *situation model* ("Recall: we were following Schrödinger and he'd just seen de Broglie's thesis — what did he find when he tried to write the wave equation?"), not just the propositional fact — this improves transfer.

---

## Part 5: Domain Examples (canonical)

One worked example per teacher model, illustrating Phases 1–4 of §4.1 (problem → analogy → confusion → reconstruction). Apply the same pattern to any concept in any domain.

**Physics (FloatHeadPhysics — analogy-first) — Wave Functions:** "It's 1924. De Broglie proposes electrons might be waves; most physicists (Bohr included) think he's wrong. You're Schrödinger — if electrons are waves, there must be an equation describing how they wave. But every wave equation you know describes *real* waves (pressure, light). What would your equation need to do?" Analogy anchor: guitar string → standing waves → allowed harmonics → quantized energy levels ("a string vibrates only at specific frequencies — what does that tell you about why electrons have only certain allowed energies?"). Socratic fill: "de Broglie says wavelength = h/momentum — what kind of equation has sinusoidal solutions? What if the wave has to 'fit' inside the atom like a harmonic fits on a string?"

**Mathematics (3Blue1Brown — geometric-intuition-first) — Eigenvalues:** Driving question first, always — never introduce a mathematical object before the question it answers. Visual anchor: "A transformation squishes and rotates space. Most vectors get knocked off direction — but a few stay pointing the same way, just stretched. Those are eigenvectors; the stretch factor is the eigenvalue. What would this look like for a 90° rotation — which vectors survive unchanged? A reflection?" Only afterward: "Now write that algebraically — if Av = λv, what does that say geometrically?"

**Neuroscience/ML (Veritasium — misconception-dislodging) — Action Potentials:** "Through the 19th century, the leading model was that nerves are pipes — impulses travel like water pressure. Helmholtz measured conduction speed (30 m/s), consistent with the pipe model. Then Hodgkin & Huxley put electrodes in a squid giant axon and found something the pipe model couldn't explain. What did they find?" (Answer: electrical potential reversal — the interior goes positive, which water pressure can't do.)

**Non-science domains (pattern extends):** Marketing substitutes a real decision-maker at a decision moment for the historical scientist (e.g., Steve Jobs pitching record labels on iTunes in 2003 — "conventional wisdom: digital music kills revenue — what narrative changes their model?"). Biology uses the same discovery-narrative structure (e.g., Watson/Crick/Franklin/Pauling and Photo 51 for DNA structure — "what does Watson see that tells him Pauling is wrong?").

---

## Part 6: Limitations & Evidence Gaps

| Gap | Issue |
|---|---|
| **AI-specific narrative research** | Narrative-learning literature concerns human teachers/static media. AI-generated narrative producing transportation comparable to human-authored narrative is plausible but not empirically established. |
| **Individual differences** | Highly analytical learners may find narrative framing distracting. Hybrid design needs an explicit opt-out to pure Socratic mode when signaled. |
| **Productive failure at expert level** | Kapur's work is primarily middle-school math on constrained problems. Generalizability to self-directed adult learners on graduate-level content (neuroscience, advanced ML) is plausible but underexplored — risk of unproductive frustration if the problem space is too large. |
| **Character consistency over time** | Assumed to produce cumulative narrative benefit (situation model theory) but unstudied in AI tutoring specifically. |
| **Misconception detection** | Conceptual change theory explains how to *replace* misconceptions but gives no reliable way to inventory which ones a learner holds before they surface in dialogue — Template 12 depends on the learner producing the misconception first. |

---

## References (APA 7.0)

Brown, J. S., Collins, A., & Duguid, P. (1989). Situated cognition and the culture of learning. *Educational Researcher, 18*(1), 32–42.

Bruner, J. (1986). *Actual minds, possible worlds*. Harvard University Press.

Chi, M. T. H. (2008). Three types of conceptual change. In S. Vosniadou (Ed.), *International handbook of research on conceptual change* (pp. 61–82). Routledge.

Chi, M. T. H., & Wylie, R. (2014). The ICAP framework. *Educational Psychologist, 49*(4), 219–243.

Damasio, A. (1994). *Descartes' error: Emotion, reason, and the human brain*. Putnam.

Gentner, D. (1983). Structure-mapping: A theoretical framework for analogy. *Cognitive Science, 7*(2), 155–170.

Graesser, A. C., Singer, M., & Trabasso, T. (1994). Constructing inferences during narrative text comprehension. *Psychological Review, 101*(3), 371–395.

Green, M. C., & Brock, T. C. (2000). The role of transportation in the persuasiveness of public narratives. *Journal of Personality and Social Psychology, 79*(5), 701–721.

Hmelo-Silver, C. E., Duncan, R. G., & Chinn, C. A. (2007). Scaffolding and achievement in problem-based and inquiry learning. *Educational Psychologist, 42*(2), 99–107.

Holyoak, K. J., & Thagard, P. (1995). *Mental leaps: Analogy in creative thought*. MIT Press.

Kapur, M. (2008). Productive failure. *Cognition and Instruction, 26*(3), 379–424.

Kapur, M. (2016). Examining productive failure, productive success, unproductive failure, and unproductive success in learning. *Educational Psychologist, 51*(2), 289–299.

Kipnis, N. (1996). The "historical-investigative" approach to teaching science. *Science & Education, 5*(3), 277–308.

Klassen, S. (2006). A theoretical framework for contextual science teaching. *Interchange, 37*(1–2), 31–62.

Lave, J., & Wenger, E. (1991). *Situated learning: Legitimate peripheral participation*. Cambridge University Press.

Matthews, M. R. (1994). *Science teaching: The role of history and philosophy of science*. Routledge.

Mayer, R. E. (2009). *Multimedia learning* (2nd ed.). Cambridge University Press.

Mercer, N. (2000). *Words and minds: How we use language to think together*. Routledge.

Monk, M., & Osborne, J. (1997). Placing the history and philosophy of science on the curriculum. *Science Education, 81*(4), 405–424.

Paivio, A. (1990). *Mental representations: A dual coding approach*. Oxford University Press.

Posner, G. J., Strike, K. A., Hewson, P. W., & Gertzog, W. A. (1982). Accommodation of a scientific conception: Toward a theory of conceptual change. *Science Education, 66*(2), 211–227.

Richland, L. E., Zur, O., & Holyoak, K. J. (2007). Cognitive supports for analogies in the mathematics classroom. *Science, 316*(5828), 1128–1129.

Slamecka, N. J., & Graf, P. (1978). The generation effect. *Journal of Experimental Psychology: Human Learning and Memory, 4*(6), 592–604.

Stinner, A., McMillan, B. A., Metz, D., Jilek, J. M., & Klassen, S. (2003). The renewal of case studies in science education. *Science & Education, 12*(7), 617–643.

Sweller, J. (1988). Cognitive load during problem solving: Effects on learning. *Cognitive Science, 12*(2), 257–285.

Wells, G. (1999). *Dialogic inquiry: Towards a sociocultural practice and theory of education*. Cambridge University Press.

Willingham, D. T. (2009). *Why don't students like school?* Jossey-Bass.

Zak, P. J. (2015). Why inspiring stories make us react: The neuroscience of narrative. *Cerebrum, 2015*.

---

*Research synthesis, May 2026. Extends ELM-Research-Report.md and AI-Second-Brain-Research-Report.md.*
