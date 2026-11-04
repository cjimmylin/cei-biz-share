# Review: AI evaluation and alignment researcher

*Oct 31, 2026. Stance: a NeurIPS Evaluations & Datasets reviewer who has built evaluations inside a frontier lab. Read: the technical brief, the business plan (Appendices A–C, theory of change, risks), both charters, the board brief, the Christian edition, and Budget v3's research lines. Oct 27 findings the documents now answer are not repeated; "carried over" marks those still open; "to verify" marks what I could not check.*

## 1. Verdict

As a paper this is not reviewable yet: no item, no transcript, no agreement statistic, no registration ID. As a design it is better than most values benchmarks I am sent, and the Oct 27 round fixed the obvious holes (fixed judge panel, minimum cell, precision/recall representation, false-attribution arm, pre-release path). My lab would run the development split once, in Inspect, if it arrived packaged, and would act on three artifacts: the misstatements against a tradition's reference points, the sycophancy flips, and the say–do transcripts. What decides whether the results would be trusted is the say–do module, and it is the least specified part of the brief: "costs the goal" has no definition, no cost magnitude, no rule for what counts as the action, and intervals that assume 60 independent scenarios when there are 6–8 templates. Fix that, raise the judge floor, and show one worked item per task, and this becomes something a lab would cite.

## 2. Must fix before this goes to a lab or a reviewer

**M1. Say–do: "costs the goal" is not operationalized.**
Brief, Constructs table: "Acting on a stated value when it costs the goal | Agentic scenarios with tool use; moral stakes left implicit; a matched control with no conflict." Brief, Sensitivity: "a pre-registered pilot of about 60 scenarios (6–8 templates with surface variants)... At 200, each model's overall gap is estimated to within about ±7 percentage points."
*Why.* (a) Whose goal? If it is an operator instruction, a model that completes the task is doing what every lab's specification tells it to unless harm is clear; a "fidelity failure" against a tradition may be specification-conformant, and a lab will say so. (b) Cost is a continuous design variable. PropensityBench (Scale AI, ICLR 2026, arXiv 2511.20703) showed the average propensity to take a harmful action rising from a low baseline to 46.9% under operational pressure; a design without a cost ladder reports one point on that curve. It is the closest agentic-pressure precedent and is absent from the prior-work table. (c) Surface variants of one template are not independent; an item-level bootstrap on 60 variants from 7 templates overstates precision several-fold, so "±7 at 200" holds only if 200 means templates. (d) The "say" side is elicited on "the abstracted case" without the task context, so the gap mixes a legitimate re-weighing under a concrete trade-off with akrasia.
*Fix (protocol).* State the goal source (an operator system prompt), a three-level cost ladder (inconvenience; task failure; task failure plus explicit operator penalty), and a deterministic action rule (the outcome is read from tool calls, not a judge). Elicit the "say" judgment with the full trade-off described, under three framings, before the agentic run. Cluster intervals by template and pre-register the pilot's minimum detectable gap (about 30 points at 7 templates, to verify by simulation). Add: "A fidelity failure is not a specification violation; operator-following is reported as a covariate."

**M2. Krippendorff's α of 0.67 is doing three jobs and is the "tentative" bar.**
Brief, Validation: "against a pre-set floor of 0.67; a dimension below the floor is human-rated or dropped." Partner Charter §3: "Items where the panel's agreement falls below the floor (Krippendorff's α of 0.67) are kept and labeled contested." Methods Charter §6.3: "the judge–human agreement threshold (floor: Krippendorff's α of 0.67)."
*Why.* Krippendorff's convention is α ≥ 0.800 for reliable data and 0.667–0.800 only for tentative conclusions ([summary of Krippendorff 2004](https://en.wikipedia.org/wiki/Krippendorff%27s_alpha)); a lab will not act on a dimension whose AI judge agrees with humans at 0.68. α is a corpus statistic, so an item "below α 0.67" is undefined with three raters on one item. Nothing says the judge-validation sample is held out from judge-prompt development; agreement measured on the tuning sample is inflated.
*Fix (text, Validation).* "Three rules, kept apart. Scholar panels: α is reported per module; an item is labeled settled when the panel is unanimous and contested otherwise, by vote, not by α. AI judges: a dimension is reported from an AI judge only where judge–human α ≥ 0.80 on a held-out sample never used to write judge prompts; 0.67–0.80 is reported as tentative with a 20% human audit; below 0.67 the dimension is human-rated or dropped. Ceiling: judge–human agreement must also be within 0.10 of human–human agreement on the same sample." Align both charters.

**M3. The item-drafting pipeline is undisclosed, and it creates a judge bias the sensitivity row does not catch.**
Business plan, "How we use AI in our own work": "AI tools help us scan the literature, code data and draft test items." Brief, Data protocol: "Authored by tradition scholars from the shared templates."
*Why.* Preference Leakage (ICLR 2026, [arXiv 2502.01534](https://arxiv.org/abs/2502.01534)) shows judges favor outputs from models related to the data generator (same model, inheritance, same family), and a 2026 preprint finds same-family self-preference persists even under objective rubrics ([arXiv 2604.06996](https://arxiv.org/abs/2604.06996)). If one vendor's model drafts the items and sits on the panel, that family gains an edge on every model's score; removing the judge from the scored model's family does not remove it.
*Fix.* Record the drafting model family in the item schema and datasheet; report each result with the drafting family's judge removed as a second sensitivity row; cap the AI-drafted share per module and state it; scholars rewrite, not approve, drafted items.

**M4. The compute arithmetic is one number for two cost structures, and 2027 has no slack.**
Brief, Compute: "$36K for model tokens and compute... one full frontier run (six models on five modules... at about $1,200 per model per module) plus local development runs on open-weight models." Budget v3, Assumptions: "a roughly 5,000-item module at about 2k tokens per item across development and final runs at frontier API pricing."
*Why.* 6 × 5 × $1,200 is exactly $36,000, so "plus local development runs," the 90-day pilot, judge validation, reruns after harness bugs and the thinking-mode arms are unfunded. The 20-model sweep is the hidden cost: judged by the full panel, 20 models × 5 modules × 5,000 outputs × 3 judges is about 1.5M judge calls, roughly $25K at mid-2026 frontier list prices (to verify against the team's token model), the compute line again; if the open-weight judge alone scores it, say so. An agentic say–do run (60 scenarios × 4 arms × 5 samples, multi-turn with reasoning) costs of the order of $1,000 per model and three times that at 200 scenarios, so the knowledge-module unit cost does not transfer. The 2031 driver (14 × 20 × 3 × $1,200 = $1.008M) treats scoring as a thrice-yearly census; a fixed model version is scored once, so the driver should be new versions × modules plus rotation re-scoring. The workbook assumes 5,000 items per module; the brief sizes only the 300–500-item gold subset.
*Fix.* Publish a token model per module type (items × variants × samples × tokens × price, generation and judging apart); split the line into frontier runs, GPU hours, judging and the sweep; add $8–12K of 2027 slack; change the five-year driver.

**M5. Capability correlation: the index, threshold and contamination of the sweep are unstated.**
Brief, Validation: "correlation with standard capability benchmarks computed across 20 or more open-weight models of varied size on the development split."
*Why.* Ren et al. used a capability component from PCA over many benchmarks across about 53 models (to verify), not one benchmark; without a pre-registered index and threshold, "mostly tracks capability" is decided after seeing results. A correlation across a size range is dominated by size; a lab needs to know whether the dimension still discriminates among the frontier six once capability is regressed out. Open-weight models released after the dev split is public will have trained on it, so the sweep decays with each release.
*Fix (text).* "Capability is a published composite index named in the registration; a dimension with |r| above a pre-registered threshold is reported as tracking capability; the frontier profiles are also shown as residuals from the capability regression; sweep models are dated against the dev-split release and a snapshot of the sweep is frozen at v1."

**M6. The stable core is the contamination weak point, and canaries do not protect the private split.**
Brief, Data protocol: "A stable core keeps versions comparable; other test items rotate about every six months." "Every released file carries a canary string. The private split has named custodians and access logs."
*Why.* The private split's exposure path is the vendor endpoint, not file release; each run of the core through a vendor without zero-data-retention terms is a training exposure, and after two rotations the core is the most-exposed part of the suite. The brief says nothing about what happens when a vendor declines such terms.
*Fix.* Treat the core as exposed after each run; add a leak test per rotation (each model's core-vs-fresh-items gap, plus a guided-versus-unguided completion probe); state: "Where a vendor will not give zero-data-retention terms, the model is scored and its row is marked exposed"; rotate the core on a longer cycle with linking items.

**M7. "No leaderboard" is unenforceable as written and hides what labs act on.**
Brief, Reporting: "There is no leaderboard, overall score, badge or certification, so the results describe models rather than rank them. Once the development split and code are public, anyone can rank; our own reports will not."
*Why.* Dimension-level numbers with intervals across six models are a comparison; the press will rank them within a day. The stance buys something real (no composite to Goodhart, no "most moral model," the pluralism premise intact). It costs this: a lab reads a profile to learn whether its new version regressed against its last, and the brief promises no version-delta panel; discriminant validity is itself a cross-model analysis.
*Fix (text).* "No composite score, badge or certification. Dimension-level comparison tables with intervals are published, because a measurement no one can compare is not a measurement; every profile carries a within-family change-since-last-version panel; the minimum detectable difference at the minimum cell (about 15 points at 80 items) is printed on every table, and differences below it are reported as not distinguishable."

**M8. Carried over: the brief promises the full v1 while nothing exists to show, and the budget's own conservative path is a two-module preprint.**
Brief: "v1 ships within 12 months of first-tranche funding"; "Four benchmarks, already in active development"; "Pre-registered: task specifications and validation plans are registered (Open Science Framework)," while the open-questions list still reads "Register the task specifications and validation plan." No example item, no transcript, no pilot number, no named technical co-lead, and the "[embedded content: v1 plan · 4 phases, 1 gate]" still does not render.
*Fix.* The strongest brief promises less and shows more: a "What exists today" box (items per prototype, outputs scored, human ratings; "none" where none); one worked item per task and one say–do transcript as an appendix; the plan's tiered scope (floor: two modules, the say–do pilot and the probe); "pre-registered" becomes "to be registered before scoring; the registration ID will appear here"; the timeline as a text table.

## 3. Should fix

**S1.** Validation: "about 100 items × 3 models × 2 raters per module" validates judges at the item level, but representation is scored "claim by claim." Validate at the claim level, refresh the sample at each rotation and for each new model family, and admit that 100 items per family cannot detect the family heterogeneity the brief promises to check.

**S2.** No human baseline in v1 (the workbook funds "human-baseline studies" from 2029). Without a scholar ceiling and a lay-adherent floor, a recall of 60% is uninterpretable. Add a 100-item baseline per module (panel plus five lay adherents) to v1.

**S3.** Sycophancy probe: no item count. Separating a 3% from a 6% flip rate needs about 700 items per arm (carried over); at the 80-item cell the minimum detectable difference is about 15 points. Add a second-turn pushback arm ("Are you sure? As a [tradition] I think..."), the form labs care about and the form FaithfulBench ([arXiv 2609.13634](https://arxiv.org/abs/2609.13634)) already tests as "holds or caves." Score verdicts only; a model should change its reasons with the cue.

**S4.** Encyclical module: open-book representation is reading comprehension and closed-book is training cutoff; neither measures values. Say that for post-cutoff sources the module's value lies in application, sycophancy and say–do, and that categorical items bearing on an agent's own actions may number under ten, so fidelity there is exploratory.

**S5.** Carried over: reasoning quality "mostly without an AI judge" needs a matcher for open-ended answers. Constrain items to a verdict plus justification; consistency is verdict agreement across variants, reported per variant type.

**S6.** No noise floor: specify k ≥ 3 samples per item at the vendor's default settings, report within-model variance, and treat thinking mode and tool access as factors (they move say–do more than temperature). Open-weight models: pinned inference stack and precision.

**S7.** The local-run kit can only use the open-weight judge, so local scores are not comparable to the published panel scores. Publish an "open-judge-only" row for every model, and the kit's hardware floor.

**S8.** Landscape claims an expert will challenge. Brief, Problem: "Anthropic... keeps its evaluations in-house" is wrong as stated: the political even-handedness evaluation is open source ([CC BY 4.0, Nov 2025](https://github.com/anthropics/political-neutrality-eval)) and the Petri auditing tool was open-sourced in Oct 2025 and handed to Meridian Labs in May 2026 ([Anthropic](https://anthropic.com/research/petri-open-source-auditing)); write "runs its values evaluations itself and has released some tooling; the July 2026 audit found no externally developed pluralism benchmark in use." "Few tests check whether a model acts on the values it states once acting on them costs it something": name MACHIAVELLI, Agentic Misalignment (16 models), Jakkli et al. (205 and 197 tenets) and PropensityBench, and state the real gap: none measures against tradition-stated values. Appendix B: "CAIS... built values benchmarks (ETHICS, MACHIAVELLI)": ETHICS (2020) predates CAIS (founded 2022, to verify); write "led by CAIS's director." AllFaith: the brief says 14 models; coverage of the same release reports 3,640 responses across 20 models ([Deseret](https://www.deseret.com/faith/2026/05/26/studies-find-religious-bias-in-ai-models/)); reconcile at cefe.ai. FaithfulBench ([arXiv 2609.13634](https://arxiv.org/abs/2609.13634)) scores counsel against each tradition's own texts and tests steadfastness under pressure on five models, which is the application task plus the probe; the "what CEI adds" cell should say what is left (tool-use say–do, representation kept apart from application, open data).

**S9.** Partner Charter §4 gives a partner veto over "the choice of AI judges for that module"; the brief says "One fixed judge panel... scores every model." A per-module veto breaks suite-wide comparability. Make it an objection with published dissent, not a veto.

**S10.** A dev–test gap is contamination or distribution shift. Draw test items from the same templates and difficulty strata as dev, and say so, or the gap is not attributable.

## 4. Nits

- Brief, benchmarks table: "reasoning-stage estimates compared with human data" sits beside "v1 makes no developmental-stage claims"; Appendix A still says "the maturity of their moral reasoning." Pick one.
- Theory of change: "legitimacy (reviewers can speak for their traditions) demand" needs a comma; "tests the third" should name demand.
- Threats table: "misbehavior several times more often when a model judged a scenario real" rests on one model, one scenario, 500 samples (55.1% vs 6.5%, [Anthropic](https://www.anthropic.com/research/agentic-misalignment)); say so.
- The refusal classifier is a judge and needs its own agreement number.
- Governance Symphony's ICC (0.93, 0.79) is agreement between two AI coders, not validity; it should not stand as evidence of rigor under "Prior work."
- NeurIPS renamed the track "Evaluations & Datasets" for 2026 ([call](https://neurips.cc/Conferences/2026/CallForEvaluationsDatasets)); the documents are right. ICLR 2028 needs v1 done by about month nine.
- Say–do should ship as Inspect sandbox tasks and the knowledge modules as plain tasks with a swappable scorer; Inspect Evals moved community submissions to a register folder in May 2026 (to verify).
- Zero-data-retention terms appear only in Appendix D of the plan; put them in the brief's data protocol.

## 5. What is strong

- The describe/apply/own-view separation, the own view never scored against a tradition, and representation as precision and recall over settled/contested/not-addressed reference points with the OvertonBench coverage rule.
- One fixed judge panel from two vendors plus an open-weight judge, the own-family sensitivity row, family by declared provenance, and the check that judge–human agreement does not vary by scored family.
- The pre-release path (dev split in-lab under a hashed, canaried version; test split run by CEI on a public endpoint; labs pay their own tokens) and the embargo with factual-error flags only.
- Refusals on all and on answered items; dev–test gap side by side; capability correlation on open models, not six frontier ones; discriminant validity stated as a falsifiable bet.
- The candor: "labs ask for dialogue, not tests," and the admission that the knowledge modules may behave like ETHICS.

## 6. Questions only the founder can answer

1. Which model family drafts items today, and what share of the four prototypes is AI-drafted?
2. In "six models on five modules," is the fifth module say–do, and is the sycophancy probe inside each module or its own?
3. Where will the 20-model sweep run: rented GPUs, a partner cluster, or vendor-hosted endpoints? Is there a budget line for it?
4. Will the say–do goal be an operator instruction, and is CEI prepared to publish that specification-conformant operator-following counts as a fidelity failure against a tradition?
5. Has any vendor agreed to zero-data-retention terms for the test split, and which will not?
6. What exists in the prototypes now: items per module, outputs scored, any human ratings?
7. Carried over: who is the technical co-lead, and who holds the private split today?
