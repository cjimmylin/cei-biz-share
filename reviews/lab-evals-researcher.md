# Review of the CEI Technical Brief: lab evaluations researcher

Stance: senior evaluations researcher at a frontier lab, reading as a prospective user. Reviewed against the technical brief (Oct 26, 2026) and the measurement, validation, two-products and publishing sections of the business plan.

## 1. Verdict

I would not run this today and could not cite it, because there is nothing to run: no items, no pilot numbers, no harness package, no named technical lead. The design is better than most ethics benchmarks I am sent (construct separation, refusal column, dev–test gap, capability correlation, no leaderboard), so this is "not yet", not "ignore". The one thing that decides it is a pilot on the public dev split, run through Inspect, showing human–judge agreement and per-cell intervals. Until then the brief is a promise, and my team only ingests results.

## 2. Top problems, ranked

**P1. Item counts and power per cell are unstated, and the implied cells are tiny. [JIMMY]**
Validation: "a gold subset of roughly 300–500 items per module"; Reporting: "each model's results by tradition and dimension." Only the gold subset is sized; the full dev and test sets are not. A profile cell is tradition × task × model. Normative ethics has four frameworks and five tasks, so a 400-item set gives about 20 items per cell, and a bootstrap interval on 20 items is about ±20 points, which separates no two frontier models. The say–do arithmetic (±7 at 200, ±14 at 50) shows the team can do this. Fix: a table of planned items per module × task × split; a minimum reportable cell (say 80 items or 400 scored claims); smaller cells greyed as exploratory. Also say what the public dev split is for, since labs will tune on it.

**P2. The three-rater gold protocol is undercosted and under-specified. [JIMMY]**
Validation: "At least three scholars from the tradition rate each item." Unclear whether raters (a) ratify the gold key points or (b) rate model outputs against them. Judge validation needs (b). For (a), 4 modules × 400 items × 3 raters is 4,800 expert ratings; for (b) across six models it is about 29,000. At ten minutes each that is thousands of scholar hours, with "paid stipends" and no budget line I can find [verify]. "From the tradition" also means three raters per framework for normative ethics (twelve philosophers), and the Catholic module has none recruited. Fix: separate the steps; ratify keys with three raters; validate judges on a stratified sample (e.g., 100 items × 3 models × 2 raters per module, third rater on disagreements only); pre-set an α floor (0.67 is the conventional bar [verify]) and state what happens below it (dimension becomes human-rated or is dropped). Name rater qualifications and recruitment.

**P3. "Never the same family" makes scores non-comparable across models. [TEXT]**
Validation: "Judges come from at least two vendors and never from the family of the model being scored." If strong judges come from two or three vendors [verify], Model A is judged by B+C and Model B by A+C: the instrument changes with the subject, and judge-family effects are confounded with model differences. "Family" is undefined for open-weight models distilled on vendor outputs. Fix: one fixed judge panel for every model, including an open-weight judge so the panel runs locally; report each model with and without its own-family judge as a sensitivity row; define family by declared training provenance. Set the agreement threshold per dimension and check that judge–human agreement does not vary by scored-model family; that heterogeneity is the real bias.

**P4. Representation scoring punishes correct hedges and rewards length. [TEXT]**
Constructs: "Claim-level match against key points and known errors … a view counts as fairly represented only when X's scholars agree." A model that says "the encyclical does not settle this; theologians differ" scores zero against key points unless the gold already says so. "Candor" is said to be scored both ways, but no rule is given. Claim recall also rewards verbosity; length control is mentioned only for judges. Fix: every gold item carries a label (settled / contested within / not addressed) and a rule: correct hedge = full credit; hedge on a settled point = false-balance penalty; assertion on a contested point = overclaim penalty. Report precision (no known errors) and recall (key points) separately, length-stratified.

**P5. 200 realistic agentic scenarios cannot be built by a half-time engineer who is also building everything else. [JIMMY]**
Validation: "about 200 scenarios"; business plan: the half-time engineer "builds the evaluation harness, data pipeline, evaluation server and local-run kit." Two hundred tool-use environments with matched controls is 400 scaffolds with tools, documents and an implicit stake, plus scholar-written gold actions for fidelity, plus a believed-real audit. That took lab teams. And "the model's own judgment on the abstracted case" is itself prompt-sensitive, so a say–do gap can be say–say noise. Fix: a v1 pilot of about 60 scenarios from 6–8 templates × surface variants, built in Inspect on released open scaffolds [verify which exist], pre-registered as exploratory; elicit the abstracted judgment under three framings and report its stability before any gap; the full module moves to v1.5 behind a technical co-lead.

**P6. The sycophancy probe measures the wrong thing. [TEXT]**
Constructs: "Flip rate on items where the traditions agree." Where traditions agree, the identity cue exerts no pull toward a different answer, so zero flips is uninformative and nonzero flips are cue noise, not sycophancy. Sharma et al. measure shifts toward a user's stated belief. Separating a 3% from a 6% flip rate needs on the order of 700 items per arm (independent-proportions approximation [verify]). Fix: paired design with a no-cue baseline; add false-attribution cues ("as a utilitarian I believe X is absolutely forbidden") and score whether the model affirms the misattribution; keep agreement items as the control arm; report per-item flips with a paired interval.

**P7. The private test split cannot be used where a lab most needs it: pre-release. [JIMMY]**
Data protocol: "run only through CEI's evaluation server, or sent to model providers under zero-data-retention terms." A pre-release model does not leave the lab, so running the test split on it means bringing items inside, which the protocol forbids; and ZDR usually needs an enterprise agreement a $300K nonprofit may not get [verify]. Unstated: who pays tokens (the $30K line covers CEI's runs, with no paraphrase × format × judge multiplier shown), server latency and rate limits, what the server logs, and how a six-month rotation is pinned so two reports compare. Fix: dev split runs inside labs under a hashed, canaried version ID; the test split is CEI-run on released endpoints; labs pay their own tokens; publish a dry-run cost per model with all variants; state a turnaround (e.g., ten business days) and the stable-core size.

**P8. Capability correlation across six models is not a number. [TEXT]**
Validation: "correlation with standard capability benchmarks across the evaluated models." With n=6 the interval is roughly ±0.8; Ren et al. used dozens of models [verify]. Fix: compute it on 20+ open-weight models of varied scale (cheap, local, dev split) and show the six frontier profiles separately.

**P9. Refusals need a denominator and a definition. [TEXT]**
Constructs: "Refusals are reported as their own column, never folded into a score." Then scores are on answered items only, which flatters models that refuse the hard ones. Partial answers, redirects and "I can't speak for a tradition" are refusals or not, depending on the reader. Fix: a validated refusal classifier with categories; every score reported on all items and on answered items; refusal by topic; the application task should anticipate policy refusals on sensitive advice and say how they are scored.

**P10. Prior-work table: missing and mischaracterized rows. [TEXT]**
ValueActionLens (Shen et al., EMNLP 2025), 14.8k value–action pairs across 12 cultures, is the closest prior to say–do and is absent. OvertonBench (Poole-Dayan et al., ICLR 2026) has a human-validated coverage metric that representation scoring needs; absent. Anthropic's political even-handedness framework (paired prompts) is the closest lab-adopted symmetry test and the natural template for the probe; absent. "Values in the Wild" is observational, not agentic; "In-context scheming" is goal-nudged deception, not value–action consistency; the Agentic Misalignment row claims "scenarios built to read as real" as CEI's addition, which is undemonstrated. AllFaith has no link; FaithfulBench and "the first benchmark built on" the encyclical need [verify]. Adopt BetterBench (Reuel et al., 2024) as the quality checklist.

**P11. "How to work with us" omits what a lab needs to run it. [TEXT]**
The lab row offers "embargoed previews" for "API access or credits." I need an Inspect package, a results JSON schema, a named technical contact, a turnaround, an NDA template for pre-release and a statement of what I may say about results before publication. There is no row for evaluation organizations and AISIs, though the theory of change rests on "a pre-release pilot with an evaluation organization." Say whether vendor credits count toward the 15% cap.

**P12. The open-questions list is the project. [JIMMY]**
No v1 lead, no technical co-lead, no methods committee, no IRB route, no judge thresholds, no scholarly leads, no theologians, no credits, and the "4 phases, 1 gate" timeline is an embedded object that does not render. Fix: an owner and date per item; add "item counts per split", "pre-release mechanism" and "dev-split pilot within 90 days: three open-weight models, 50 items per module, two raters"; replace the embed with a text table.

Minor [TEXT]: name the pre-registration registry; "Catholic and Reformed, or different Sunni schools" are not v1 modules, use v1 examples; add reasoning/thinking mode and tool configuration to reported model settings, since they move say–do more than temperature; state in v1 that no Kohlberg stage claims are made, because format stability does not establish construct validity on models; "mostly without an AI judge" for reasoning quality needs a stated matcher for open-ended answers.

## 3. Keep

- Describing, applying and own view kept apart, with the own view never scored against a tradition.
- Refusals as a column, no leaderboard, no single number; dev–test gap published side by side, with canaries, rotation and retirement.
- Order-randomized controls and a uniform-random baseline for every value-profile claim.
- Matched no-conflict controls and a reported evaluation-awareness rate in say–do.
- Embargo with factual-error flags only, no veto, negative results unchanged.

## 4. What would make me run it once

1. `inspect eval` on the dev split, with a results schema and a sample profile for three open-weight models.
2. Pilot numbers: α per module, judge–human agreement per dimension against a pre-set threshold, cell widths, and capability correlation on 20+ open models.
3. A named technical co-lead with published evaluation work, and say–do cut to a pre-registered pilot.
4. A fixed judge panel with a same-family sensitivity row.
5. A written pre-release path (in-lab dev split, CEI-run test split) with turnaround and cost.
6. The sycophancy probe redesigned with a baseline and a false-attribution arm.
