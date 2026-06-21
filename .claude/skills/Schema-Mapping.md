# Schema Mapping Skill

\---

## PURPOSE AND CUSTOMIZATION

This file is a standalone skill file defining the schema mapping system used
in this vault. It is read by Claude at session start when present in
.claude/skills/. It is completely self-contained — all schema mapping
behavior is defined here, not in the main skill file.

THIS FILE IS REPLACEABLE. If you want a different schema mapping system,
delete this file and replace it with your own skill file defining your node
types, relationship vocabulary, notation conventions, and how you want Claude
to assist with schema construction. The main skill file defers to whatever
system is defined here.

If this file is absent, Claude has no schema mapping system and will not
attempt to discuss or build schema maps using any particular notation.

\---

## WHAT SCHEMA MAPPING IS

Schema mapping in this system is Mode 1 thinking made visible. A schema map
is not a clean diagram produced at the end of learning. It is a living,
wrong, continuously updated structure the user thinks WITH during learning —
puzzle pieces on the table while still figuring out how they fit.

The schema map is always the user's artifact. Claude transcribes and verifies.
Claude never independently constructs or updates schema maps. This is the
generation-before-suggestion principle applied to knowledge architecture.

A schema map is built around a focus question, organized using typed nodes
and labeled relationships, and updated iteratively as understanding develops.
Cross-links between clusters — connections that cross domain or cluster
boundaries — are the highest cognitively valuable elements of any map.

\---

## THREE-LEVEL TAXONOMY

Every relationship in a schema map belongs to a three-level hierarchy:

CATEGORY — the broadest grouping, identified by line style and terminator
family. There are five categories: Structural, Causal, Quantitative,
Temporal, and Logical/Epistemic.

ARROW TYPE — the specific named arrow within a category. The relationship
is encoded in the visual form of the arrow — its line style, head type,
and any markers. A proposition is complete at the arrow type level.
Drawing a solid open chevron from A to B already makes a specific claim:
"A causes B." No text label is required.

SUB-RELATIONSHIP — optional text label written on the arrow when precision
within the arrow type matters. "Triggers" and "enables" are both sub-
relationships of the Causes arrow type. Writing the sub-relationship adds
specificity when the distinction is meaningful for the map's focus question.
When it is not, the arrow type is the complete claim.

Key principle: the arrow encodes the relationship. There are no unlabeled
arrows — every arrow makes a claim by its type. A text label adds precision;
it does not make the proposition valid where it would otherwise be incomplete.

\---

## FOCUS QUESTION

Every schema map can start with a focus question written at the top before any
nodes are placed. The focus question is a question the map is trying to
answer. Without one, the map has no natural boundary and every node seems
equally relevant.

Examples:

* "How does natural selection produce adaptation over time?"
* "What causes cortisol to rise and what are its downstream effects?"
* "How does gradient descent find a minimum?"

When helping a user start a schema map, Claude asks: "What is the focus
question for this map?" before any structure is proposed. This can be helpful,

but is not strictly required.

\---

## NODE TYPES

Five node types. Each has a shape for use in hand-drawn or digital maps.
In conversation, Claude refers to nodes by their type name rather than
describing shapes.

Node typing is a POST-CONSTRUCTION step. See the Node Typing Workflow section.

|Type|Shape|Definition|
|-|-|-|
|Entity|Circle|A thing that exists — person, object, organism, institution|
|Process|Parallelogram|An action, event, or transformation that occurs over time|
|State|Pill (full semicircles both ends)|A condition something can be in — a snapshot in time|
|Principle|Trapezoid (wide base, narrows upward)|An abstract idea, rule, or framework|
|Decision/Condition|Diamond|A threshold, fork, or branch point|

The shape reflects the concept's character: parallelograms are slanted —
things in motion. Trapezoids narrow upward — abstraction sits above instances.
Diamonds can fall either way.

\---

## GROUPING

Draw a boundary around any set of nodes to treat them as a single item.
The boundary shows categorical membership — everything inside belongs to
the same group or domain cluster. Boundaries can nest for subcategories.
An arrow can connect to the boundary itself rather than individual nodes
inside it when the connection applies to the entire group.

\---

## ARROW SYSTEM

### Category 1: Structural / Ontological

Line: solid line ending in a circle terminator. The marking inside or on
the terminator encodes the specific arrow type. All structural arrows read
as "(is) \_\_\_ of" — always directed from more specific to more general.

\---

Arrow type: Subset — smaller circle drawn inside the terminator circle

The arrow type claim: "A is a kind/part of B"

Sub-relationships (write on arrow when the specific distinction matters):

* is a type of
* is a subclass of
* is a subset of
* is a part of
* is a component of

\---

Arrow type: Instance — dot drawn inside the terminator circle

The arrow type claim: "A is a specific example of B"

Sub-relationships:

* is an instance of
* is an example of
* is a specific case of
* is a member of

\---

Arrow type: Property — dot drawn on the edge/rim of the terminator circle

The arrow type claim: "A is an attribute of B"

Sub-relationships:

* is a property of
* is an attribute of
* is a characteristic of
* is a feature of
* describes

\---

### Category 2: Causal

Line: solid line. Head type and markers distinguish arrow types.

\---

Arrow type: Causes — open chevron head ——>

The arrow type claim: "A drives or produces B (in some causal sense)"

Sub-relationships:

* causes
* leads to
* enables
* triggers
* amplifies
* produces
* is used for
* results in

\---

Arrow type: Inhibits — flat head ——⊣

The arrow type claim: "A suppresses or blocks B"

Sub-relationships:

* inhibits
* prevents
* regulates
* suppresses
* dampens
* blocks
* reduces

\---

Arrow type: Requires — closed chevron ——►

The arrow type claim: "B cannot function without A (non-temporal dependency)"

Sub-relationships:

* requires
* depends on
* is necessary for
* cannot function without
* is a prerequisite of (non-temporal — for temporal dependency, use Requires Before)

\---

### Category 3: Quantitative

Line: solid line with + or − modifier. Placement encodes symmetry:
modifier at arrowhead = asymmetric (effect lands at destination node);
modifier centered above line = symmetric (property of the relationship).

\---

Arrow type: Increases — open chevron with + at arrowhead →+

The arrow type claim: "A causes an increase in B"

Sub-relationships:

* causes an increase in
* raises
* elevates
* produces more of
* upregulates

\---

Arrow type: Decreases — open chevron with − at arrowhead →−

The arrow type claim: "A causes a decrease in B"

Sub-relationships:

* causes a decrease in
* lowers
* reduces
* downregulates
* consumes
* depletes

\---

Arrow type: Proportional — bidirectional with + centered above ↔+

The arrow type claim: "A and B rise and fall together"

Sub-relationships:

* is proportional to
* scales with
* positively correlates with
* co-varies with (same direction)

\---

Arrow type: Inversely Proportional — bidirectional with − centered above ↔−

The arrow type claim: "As A rises, B falls (and vice versa)"

Sub-relationships:

* is inversely proportional to
* decreases as X increases
* negatively correlates with
* trades off with
* co-varies with (opposite direction)

\---

### Category 4: Temporal / Sequential

Line: solid line with open or closed chevron head. The vertical bar is the
temporal marker. Open chevron = pure direction; closed chevron = dependency weight.

\---

Arrow type: Before — open chevron + vertical bar ——|>

The arrow type claim: "A comes before B in time or sequence"

Sub-relationships:

* precedes
* comes before
* leads to (in time)
* happens prior to

\---

Arrow type: Requires Before — closed chevron + vertical bar ——|►

The arrow type claim: "A must happen before B and B cannot begin without A"

Sub-relationships:

* must happen before and is required by
* is a temporal prerequisite of
* cannot begin without (temporal dependency)
* gates (A must occur before B can begin)

\---

Arrow type: Concurrent — bidirectional open chevron + bars on both sides ◄|——|>

The arrow type claim: "A and B happen simultaneously"

Sub-relationships:

* is concurrent with
* happens simultaneously with
* co-occurs with
* is synchronous with

\---

### Category 5: Logical / Epistemic

Line: dashed line. Head type mirrors the causal pair — open chevron for
positive epistemic direction, flat head for negative. Double lines (no
arrowhead) for equivalence.

\---

Arrow type: Supports — dashed open chevron ——->

The arrow type claim: "A is evidence for B (in some inferential sense)"

Sub-relationships:

* supports
* implies
* provides evidence for
* suggests
* indicates
* is consistent with
* predicts

\---

Arrow type: Contradicts — dashed flat head ——-⊣

The arrow type claim: "A is evidence against B"

Sub-relationships:

* contradicts
* provides evidence against
* is inconsistent with
* refutes
* challenges
* is in tension with

\---

Arrow type: Equals — double line, no arrowhead =

The arrow type claim: "A and B are identical or definitionally equivalent"

Sub-relationships:

* equals
* means
* is defined as
* is synonymous with
* is equivalent to
* is the same as
* is another name for

\---

Arrow type: Analogous — double-lined bidirectional ⟺

The arrow type claim: "A and B are structurally similar but distinct"

Sub-relationships:

* is analogous to
* is structurally similar to
* is a metaphor for
* functions similarly to
* mirrors
* parallels

\---

## NEGATION

Place an X through the middle of any arrow to convert it to the negative
form of that statement. Applies universally to all arrow types across all
five categories.

* ——X——> : does not cause (in any causal sense)
* ——X——⊣ : does not inhibit
* ——X——► : does not require
* ——X——|> : does not precede
* ——X——-> : does not support
* ——X= : does not equal
* ——X——○ : is not a (subset / instance / property) of

Important distinction: negation is not the same as the opposing arrow type.
"Does not cause" ≠ inhibits — inhibits means actively suppresses.
"Does not support" ≠ contradicts — contradicts means evidence against.
Use negation when the relationship is simply absent, not when the opposing
relationship is actively present.

\---

## PROPOSITION STANDARD

Every arrow makes a complete proposition at the arrow type level:
\[A] \[arrow type] \[B]

The arrow encodes the relationship. No text label is required for a
proposition to be complete. Examples of complete propositions at arrow
type level:

* Stress ——> Cortisol : "Stress causes cortisol (in some causal sense)"
* Exercise ——► Muscle : "Exercise requires muscle (as a dependency)"
* Hypothesis ——-> Data : "Hypothesis supports data (inferentially)"

A sub-relationship label adds precision within the arrow type when the
specific distinction matters for the map's focus question:

* Stress ——> Cortisol labeled "triggers" : "Stress triggers cortisol"
* Meditation ——⊣ Cortisol labeled "reduces" : "Meditation reduces cortisol"

Write a sub-relationship label when leaving it at the arrow type level
would obscure something meaningful for the map's purpose. Leave it at the
arrow type level when the general category of relationship is what the
map needs to capture.

The precision of a sub-relationship label, when used, is a direct measure
of depth of understanding of that specific relationship.

\---

## CROSS-LINKS

Cross-links are connections between nodes in different clusters or domains.
They are the most cognitively valuable connections in any schema map —
they represent synthesized understanding across domains.

Mark cross-links visually distinctly from local relationships (different
color, line weight, or annotation) so they stand out in the map.

After completing each cluster, scan the entire map: "Does anything here
connect to something in a different section?" This scanning step is where
cross-links are found.

Cross-links between domain schema maps feed into the Cross-Domain Map in
03 - Schemas/. These are documented when the Analogy Gate completes after
Review 3.

\---

## NODE TYPING WORKFLOW

Node typing is a post-construction audit phase, not a labeling step during
building. Classifying nodes while building interrupts the generative process —
attention shifts from relationships (the cognitive work) to categories.

When to type: after the map is stable — all iterative destroy-and-rebuild
cycles are complete.

How to type:

1. Scan the completed map and identify the dominant node type overall.
Label the map at the top with that type (e.g., "process map," "state map").
2. Mark outlier nodes — those that don't match the dominant type — with their
type name. Leave dominant-type nodes unmarked, or label all if detail needed.
3. Outliers are the most informative signal: they often mark where domains
intersect or where cross-link candidates live.

What map type reveals: domains have characteristic ontological signatures.
Biology maps tend to be entity-heavy. Psychological content tends toward
states. Mechanism maps tend toward processes. Theory maps tend toward
principles. Map type reflects the domain's character.

Nominalization check: English allows processes and states to be expressed
as nouns, making them appear as entities. During the audit ask: "Is this
node actually a thing, or is it a process or state dressed as a noun?"

\---

## SCHEMA MAPS IN THE VAULT

### The Mermaid Overview

Permanent schema map notes in 03 - Schemas/ contain a Mermaid mindmap block
at the top. This is a simplified depth-encoded overview — not a full typed
schema map with the relationship system above. It encodes note depth using
bracket types and provides a quick visual reference.

Mermaid bracket encoding:

* \[Concept] square brackets = foundational depth
* (Concept) round brackets = conceptual depth
* ((Concept)) double round = integrated depth or confirmed cross-domain link
* Plain text = section headers

The Mermaid block is built incrementally — one node added per new concept note.
The text outline below it is the authoritative record. Both stay in sync.

### User-Led Construction

Schema maps are the user's artifact. Claude transcribes; the user constructs.
The process during a schema walk-through:

1. User describes the structure — nodes, connections, groupings — in their
own words using either arrow type vocabulary or sub-relationship vocabulary
2. Claude identifies the arrow type from the description and transcribes
into the Mermaid block in real time
3. User watches it render in Obsidian and corrects if the diagram does not
match intent
4. After the user finishes their description: Claude verifies connections
that don't hold and suggests additions the user missed
5. User confirms. Claude updates.

Claude never independently adds nodes to a schema map between sessions.

### Domain Schema Map vs. Cross-Domain Map

Domain schema maps (one per subject): knowledge architecture within a single
domain. Node depth encoded in Mermaid. Text outline below.

Cross-Domain Map (one for the vault): structural isomorphisms across domain
schema maps. Pattern families as nodes. Domain instances as connected nodes.
Built collaboratively during monthly meetings from Analogy Gate results.

\---

## HOW CLAUDE USES THIS SYSTEM

### Accepting Verbal Descriptions

When users describe their schema map in conversation (since Claude cannot
see the actual drawing), they may use either arrow type vocabulary or
sub-relationship vocabulary. Claude maps both to the correct arrow type.

Examples of verbal descriptions and their arrow type mappings:

* "triggers," "enables," "leads to," "produces" → Causes arrow
* "prevents," "suppresses," "blocks," "dampens" → Inhibits arrow
* "depends on," "requires," "cannot function without" → Requires arrow
* "precedes," "comes before," "happens prior to" → Before arrow
* "implies," "supports," "predicts," "suggests" → Supports arrow
* "contradicts," "refutes," "challenges" → Contradicts arrow
* "is a type of," "is a subclass of," "is a part of" → Subset arrow
* "is an example of," "is an instance of" → Instance arrow
* "is analogous to," "mirrors," "parallels" → Analogous arrow

When a description is ambiguous between arrow types, Claude asks:
"Is that a causal relationship — A produces B — or a dependency — B cannot
function without A?" Use the sub-relationship lists to frame the question.

### Active Use During Schema Discussions

Ask for the focus question at the start of any schema mapping session if
none has been established: "What is the question this map is trying to answer?"

Use node type vocabulary when discussing structure: "That sounds like a
Process node — something that happens over time — rather than an Entity."

Use arrow type vocabulary as the baseline for discussing relationships.
Offer sub-relationship precision when it would meaningfully clarify the
structure: "Is that a triggers relationship or more of an enables? Both
are Causes arrows — the distinction matters if your focus question is about
mechanism vs. capacity."

Prompt cross-link scanning after each cluster is complete: "Before we move
on — does anything here connect to something in a different section of the map?"

Remind the user that node typing is post-construction if they start
classifying nodes while the map is still forming.

For Mermaid blocks in vault notes: transcribe using depth encoding rather
than the full relationship notation. The full typed map lives outside the vault.

\---

## SHORTHAND REFERENCE

Structural: sub (subset), inst (instance), prop (property)

Causal: caus (causes), inh (inhibits), req (requires)

Quantitative: inc (increases), dec (decreases), prop+ (proportional), inv (inversely proportional)

Temporal: bef (before), req-bef (requires before), conc (concurrent)

Logical/Epistemic: sup (supports), con (contradicts), eq (equals), ana (analogous)

Negation: X through any arrow

Common sub-relationships by arrow type:

* Causes: triggers, enables, leads to, produces, amplifies
* Inhibits: prevents, suppresses, dampens, regulates
* Requires: depends on, is necessary for, gates
* Supports: implies, predicts, indicates, is consistent with
* Subset: is a type of, is a part of, is a component of
* Analogous: mirrors, parallels, functions similarly to

