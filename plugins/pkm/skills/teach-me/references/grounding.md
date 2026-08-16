# Grounding & risk mitigation

Load at the **landscape map** (classify claims before presenting) and at the
**sweep** (close verification before validating). Confidence tiers apply
claim-by-claim throughout the dialogue.

## Why this protocol exists

Documented risks of AI-based learning, treated as design inputs:

- **Accuracy / hallucination** — students' single largest reported concern
  (48.2%, Vieriu & Petrea 2025); LLMs "can generate hallucinated facts,
  invented references, and inaccurate citations" (Henriot 2025).
- **Over-trust** — people follow AI advice even when told it is broken and the
  advice is obviously wrong (Wagner et al. 2018, via US DoE 2023).
- **Illusion of competence** — AI summaries replacing the learner's own
  processing produce recognition, not retention (Stanford CTL).
- **Silent distortion** — summaries "may omit critical qualifiers, shift tone,
  or erase specificity"; named entities and dates especially failure-prone
  (Henriot 2025).

Learning-effectiveness counterparts (retrieval practice, calibration,
wheel-spinning) live in [dialogue.md](dialogue.md).

## Confidence tiers

Label claim by claim as you teach — and per concept-map item — no boilerplate
disclaimers. Carry flagged claims into the article's `source` pin and the
state's *Open verifications* list.

- **🟢 Stable** — core theory, established results, mathematics. Trust it.
- **🟡 Verify recommended** — best practices, APIs, version-specific behavior,
  org standards. State what may have changed + a search query or doc URL.
- **🔴 Volatile — verify before acting** — current tool capabilities, recent
  laws/regulations, releases, prices, fast-moving fields. Name the primary
  source; WebSearch available → search before presenting, not flag after.

## Report certainty on AI-authored claims

Tiers grade the *world* — how likely a fact moved since training. They say
nothing about recall confidence: a 🟢-stable topic can still be misremembered.
Report both axes:

- **Every load-bearing claim from model memory** (not verified this session)
  carries an explicit inline certainty, claim by claim — `high` / `medium` /
  `low`, or a rough % where that reads more honestly ("~60% sure the default
  changed in v2"). A per-claim value is information; a blanket disclaimer is
  noise.
- **Below ~70%, don't assert.** Verify first (WebSearch, primary source,
  cloned repo) — or reframe as a hypothesis or question and add it to *Open
  verifications*. A low-certainty claim in a confident tutor voice is exactly
  the over-trust trap (US DoE 2023).
- **The estimate travels into the `source` pin**: `AI-authored (Claude,
  2026-07), certainty low — verify against <primary source>`. The reader
  inherits the calibration, not just the claim.

Tutor-side mirror of the learner's calibration check (dialogue.md): the
learner rates their confidence before a gate clears, the tutor rates its own
before a claim is taught — Stanford CTL's "How will I evaluate the accuracy
of AI output?", answered before they ask.

## Claim classes that always get scrutiny

Independent of tier, four classes are disproportionately failure-prone for
LLMs (Henriot 2025). Check **before capture** — verify if search/primary
sources are available, else pin as unverified in `source`; never let one ride
into an article unmarked:

1. **Named entities** — people, orgs, product and institution names
   (transliteration and title variants mislead).
2. **Dates and version numbers.**
3. **Numbers and statistics** — thresholds, percentages, quantities.
4. **Citations and quotes** — anything citation-shaped is presumed invented
   until the cited work was actually opened (see below).

Declaring the classes up front, not judging ad hoc, is itself the practice
("establish quality criteria for LLM outputs requiring human verification",
Henriot 2025).

## Sourcing standard (journalistic)

Clear a verified claim with **two independent, trustworthy sources** that
don't derive from each other — *or* one **clearly recent and authoritative**
source (primary spec, standards body, official docs, peer-reviewed work). A
lone secondary source, or two tracing to the same origin: still unconfirmed —
flag it, don't present as settled. Record what cleared it (or what's open) in
`source` and *Open verifications*.

## Prefer primary source over memory

Standards, specs, frameworks, reference implementations: the authoritative
source is usually a repo — clone and read locally rather than trust training
data or a search snippet. A quoted line beats a recalled one. Cite the
canonical *public URL* in the article, never the local clone path
(bundle-format Portability).

## An AI paraphrase is not a source

Never present "what X says" as sourced unless X was fetched, read, or cloned
this session ("avoid using AI to reproduce secondary literature unless the
original texts are available for verification" — Henriot 2025). A recalled
summary of a paper, book, or spec is an AI-authored claim: teach it as such,
pin it `unverified`, name the work so the learner can check — don't attach
the work's name as if consulted.

## Label constructed examples

An invented illustration must be labelled — in dialogue ("a made-up case to
see the mechanics") and in `example` bodies ("Constructed example —
illustrative, not a documented case"). Unlabelled inventions are how
fabrications enter a KB looking like evidence (Henriot 2025 flags this for
teaching material specifically).

## Provenance pins

`source` pins provenance on every article. Model-produced claim → record
**model + date** and status, so a reader knows what to re-verify:

```yaml
source: AI-authored (Claude, 2026-07), certainty medium, unverified — check current pricing docs
source: teachme dialogue 2026-07-14; verified against https://spec.example.org (v1.2)
```

Disclosure of AI authorship with model and date is the shared transparency
norm (Henriot 2025; TAMU 2024).

## Over-trust guard

The tutor can be wrong; keep that live rather than performing authority:

- **Learner pushback is evidence, not noise.** Defend with sources or update —
  never smooth over a correction to keep the flow (US DoE 2023).
- **The learner's wording wins** at capture unless factually wrong — and
  "factually wrong" must itself meet the sourcing standard, not just disagree
  with model memory.
- **Human backstop for high-stakes domains.** Medical, legal, financial,
  safety: teach the concepts, but state plainly — in dialogue and affected
  articles — that decisions need a qualified professional (Stanford CTL).

## Sweep verification closure

Before running the validator at the sweep (SKILL.md §4b):

1. Resolve every *Open verifications* item — or explicitly pin it
   `unverified` in the affected article's `source`. None silently dropped.
2. Spot-check the four scrutiny classes (entities, dates, numbers, citations)
   across article bodies against what cleared them.
3. Confirm every 🟡/🔴 flag from the dialogue landed in a `source` pin.
4. Confirm constructed examples are labelled as such.

## Sources

- Henriot, C. (2025). *The AI-Augmented Research Process: A Historian's
  Perspective.* arXiv:2508.01779 — https://arxiv.org/pdf/2508.01779
- Texas A&M University (2024). *Best Practices for Generative AI in Research.*
  https://research.tamu.edu/wp-content/uploads/2025/01/Best-Practices-for-Generative-AI-in-Research-updated-02162447-APPROVED.pdf
- Vieriu, A. M., & Petrea, G. (2025). *The Impact of Artificial Intelligence
  (AI) on Students' Academic Development.* Education Sciences 15(3), 343 —
  https://www.mdpi.com/2227-7102/15/3/343
- US Department of Education, Office of Educational Technology (2023).
  *Artificial Intelligence and the Future of Teaching and Learning.*
  https://www.ed.gov/sites/ed/files/documents/ai-report/ai-report.pdf
- Stanford Center for Teaching and Learning. *AI and Your Learning: A Guide
  for Students.* https://ctl.stanford.edu/aimes/ai-learning-guide-students
