# Foresight Application Draft: Supercollaboration

Oct 26, 2026 · @Jimmy

**Status: not applying in the October 31, 2026 round; kept as a reference for future grants.** CEI decided there was not enough time to fill the open items below well. This draft holds reusable answers for Foresight Institute's AI for Science & Safety Nodes program (Supercollaboration & decentralized alignment track) and for similar safety and evaluation funders. Before reusing it, check the funder's current form, deadlines and character limits, and fill the bracketed items.

## Before you reuse or submit

**Decisions only you can make** (bracketed placeholders below mark each one):

- [ ] **Project lead** and their weekly hours. The form treats this person as the applicant.
- [ ] **Technical co-lead or advisor** who has published or shipped AI evaluations. This is the reviewer's biggest doubt about the application.
- [ ] **Pilot results**, if the benchmark work has any (for example, say-do results on two open models). One sentence and a figure link in field 6 would help most.
- [ ] **Two outside advisors** for the month-6 validation review.
- [ ] **One outside community** willing to author the fifth module (a scholarly society, seminary or professional group). A name makes the decentralization claim concrete.
- [ ] **Primary reference**: name, email and their OK. A Notre Dame DELTA contact or a Governance Symphony co-author would carry weight.
- [ ] **Ask**: drafted at about $48K (see the budget). Confirm or change.
- [ ] **Foresight compute**: drafted as Yes, to run open-weight models on Foresight's clusters.
- [ ] **Lightcone Commons opt-in**: drafted as Yes.
- [ ] **Fiscal sponsor**: confirm Social Good Fund's fee fits inside the 10% overhead, and that all outputs can be released openly under the sponsorship terms.
- [ ] **Facts to confirm**: the Anthropic convening (date, size, coverage) and the 5ICEAI and ICAIR paper details, marked [confirm] where they appear.
- [ ] Save a PDF copy before you press submit. Foresight can't send one afterward.

**What changed from the Muse draft**

|  | Muse draft | This draft |
| --- | --- | --- |
| Focus area | AI Insurance & Open Governance | Supercollaboration & decentralized alignment |
| Project | Insurance links, incident-reporting protocol, a lab audit | An open test of whether AI agents act on their stated values, authored by many communities |
| Fit with CEI's plan | A side project | The flagship benchmark work |
| Claims removed | "Already runs advisory engagements with labs"; "EthicsMosaic already open-source" | Only facts stated in the business plan |
| Safety link | Not stated | Stated plainly and narrowly |

## Project core (fields 12–16)

**12. Applying for:** Funding (Grant); Physical node access (Bay Area); Local compute [decide].

**13. Focus area:** 2. Supercollaboration & decentralized alignment.

**14. Project title:** Many Hands: Open, Community-Authored Tests of Whether AI Agents Act on Their Stated Values

**15. What are you trying to do? Zero jargon.** (326 of 350 characters)

> We test whether AI agents actually do what they say is right. Scholars from many moral traditions write scenarios where keeping a stated value costs the AI its goal. We check whether models keep it, and whether they change answers to please the user. All code and data are open, so no single lab defines or grades AI's values.

**16. How does your project address the RFP area? Be concrete.** (490 of 500 characters)

> Alignment oversight should not sit with one lab. Our open, AI-first say-do suite lets any community check any open-weight model against its own values on its own hardware: AI-drafted scenarios validated by 3+ scholars and cross-vendor judges checked against humans. V1 covers philosophy, psychology, the UN human rights declaration and the Vatican's 2026 AI encyclical; an outside community adds a fifth. Output: open profiles of 6+ models: do they act as they say, and as each source says?

*Counts include spaces and were checked by script. If you edit either answer, keep it under the limit.*

## Narrative (fields 17–20)

**17. Limits of today's approach, what's new, and what success looks like**

> **Limits today.** The values AI systems are aligned to are written and checked mostly inside a few labs. Public moral benchmarks mostly score a model's verdict on a dilemma, use answers written by crowdworkers or one research team, and lean on Western frameworks. Many safety benchmarks also track general capability more than safety (Ren et al., "Safetywashing," 2024). Few tests check whether an agent *acts* on the values it states once acting on them costs it something.
>
> **What's new.**
>
> 1. Say-do tests in agentic, tool-use scenarios with the moral stakes left implicit and matched no-conflict controls. Each scenario yields two scores: **consistency** (does the model's action match the judgment it gave on the same case stated abstractly?) and **fidelity** (where the source gives clear guidance, does the action match the source's gold answer?). Consistency tests the model against itself; fidelity tests it against a community's values.
> 2. Standards from four different kinds of authority (moral philosophy, empirical moral psychology, international human-rights law, and a living faith tradition's published guidance on AI), with gold answers written and validated by scholars of each. Describing a view, applying it for a user, and the model's own stance are scored separately.
> 3. A sycophancy probe: the same question with the user's stated tradition varied, reporting how often verdicts flip to please.
> 4. Correlation with capability benchmarks reported for every score.
> 5. Decentralized by design. The suite runs on open-weight models on a community's own hardware, so anyone can check any model against their own values without a lab's permission. In year 1, an outside community authors a fifth module with our toolkit, with CEI only reviewing quality.
>
> **How this differs from lab and evaluator work.** Apollo Research, Anthropic and others already test whether agents misbehave under goal pressure, against standards the evaluators set. We test against standards set by scholars of several traditions outside any lab, across many vendors' models, and publish everything openly.
>
> **Sample size.** 200 scenarios (about 50 per source) estimate each model's overall say-do gap to within about ±7 percentage points (95% interval). Per-source results (about ±14 points) are reported as exploratory, and v2 adds scenarios where gaps look large.
>
> **Success at 12 months:** the open suite and per-model profiles for at least 6 frontier and open-weight models; reported inter-rater agreement and judge validation; a fifth module authored by an outside community; a preprint submitted to a peer-reviewed ML venue; and at least one outside group running the suite.

**18. Differential safety advancement (risks)**

> **What it advances.** Independent, public evidence on whether models keep their value commitments under goal pressure: an early, measurable signal of gaps between stated alignment and agent behavior, related to recent work on in-context scheming (Meinke et al., 2024). It also helps keep the definition and checking of AI's values from concentrating in one lab, model or government. We state the link narrowly: this improves measurement and spreads oversight; it is not a direct fix for catastrophic risk.
>
> **Risks and how we handle them.**
>
> - *Capability uplift:* minimal. We train no models and build no new capabilities; the work is evaluation.
> - *Teaching to the test:* everything this grant funds is released openly, so we keep the suite fresh instead of secret: canary strings in every file, new scenarios in each version, and results reported by version. Any held-out test split would be funded separately.
> - *Dual use:* we screen out scenarios that teach persuasion or manipulation, and released data carries use terms.
> - *Misuse of results:* per-model profile reports with no leaderboard or single score, so results describe models rather than rank them.
> - *Lab pressure:* labs see their own results under a fixed embargo but cannot edit or block them; negative results are published unchanged.

**19. Start and end dates, key milestones**

> **12 months from receipt of funds (expected start February 2027). Total request about $48K** ($43.5K direct plus 10% overhead; itemized budget available).
>
> - **Month 1:** contract research engineer starts (quarter time for all 12 months); evaluation harness set up on Inspect.
> - **Month 2:** task specifications for the say-do module and sycophancy probe published for public comment.
> - **Month 4:** 200 agentic scenarios drafted with AI assistance across the four sources; a gold subset of 120 rated by at least three scholars each; AI judges validated against human ratings.
> - **Month 5:** an outside community begins authoring a fifth module with the toolkit.
> - **Month 6:** validation reviewed by two outside advisors [names]; pilot runs on three open-weight models; a kit for running the suite locally released.
> - **Month 9:** full runs on at least six frontier and open-weight models; embargoed previews sent to each lab.
> - **Month 12:** public release of all code, scenarios and profile reports, including the fifth module; preprint submitted; workshop at the Bay Area hub.

**20. Scale-up plan for 3-year impact**

> Year 1 proves the method on four sources of moral wisdom and one outside-authored module. Years 2–3: (1) CEI's Scholar Group, which convenes scholars across disciplines and moral traditions, and outside communities author new modules with the same open toolkit, toward at least five tradition modules by 2029; (2) multi-agent settings, where agents holding different value commitments must cooperate; (3) the suite contributed to open evaluation registries so evaluators and safety institutes can run it without us; (4) multi-year funding from AI-safety and philanthropic funders, with independence rules: no more than 15% of revenue from any single AI company and no funder review of results.

## About you (fields 1–11)

| Field | Draft answer |
| --- | --- |
| 1. Full name | [Project lead's name] |
| 2. Email | [Project lead's email] |
| 3. Website, CV or LinkedIn | https://ethical-intel.org [plus the lead's LinkedIn] |
| 4. Affiliated organization | Center for Ethical Intelligence (CEI) |
| 5. Applying as | Organization |
| 8. Primary region | America |
| 9. Primary country | United States |
| 10. Primary reference | [Name, email, and their permission] |
| 11. Organization type | Non-profit (US) |

**6. Track record**

> CEI is a California nonprofit, fiscally sponsored by Social Good Fund, that builds open, pluralistic tools for measuring AI values. In its first year, with an all-volunteer team, CEI:
>
> - Mapped 5,140 AI-governance statements from 3,897 organizations in 130 countries into six recurring clusters of principles (the Governance Symphony study, with co-authors at Notre Dame and Harvard). Two AI models served as a measured coding instrument: agreement 0.93 within one vendor and 0.79 across vendors, with human validation planned. Full paper in preparation for AIES or NeurIPS 2027.
> - Built a 2,368-entry catalog of moral benchmarks and datasets, a 3,254-document AI-governance database, and EthicsMosaic, 7,041 professional ethics codes from 661 organizations in machine-readable form (licensing review before release).
> - Began four benchmarks, now in active development, built on normative ethics, moral psychology, the UN Universal Declaration of Human Rights, and the Vatican's 2026 encyclical on AI (*Magnifica humanitas*). [Pilot results, if any: one sentence plus a link to a figure.]
> - Received a Notre Dame DELTA partner grant; selected as a 2027 Praxis Nonprofit Accelerator fellow; presented at the Berkeley CHAI workshop at Asilomar, the ARC conference in London and ASA 2026; invited to Anthropic's March 2026 summit of Christian leaders on AI; a paper on epiplexity accepted at two conferences (5ICEAI and ICAIR).

**7. Project participants, roles, links**

> - **[Project lead]:** [role, hours per week].
> - **[Technical co-lead or advisor]:** [name; AI-evaluation papers or tools they have shipped; role, for example co-author and harness design review].
> - **Jimmy Lin, MD, PhD:** Co-Founder and President of CEI; Chief Scientific Officer at Freenome; MA in Religion. Scientific direction and lab relationships.
> - **Rui Guo, LLM, SJD:** Co-Founder and Research Director; AI-ethics legal scholar and former Visiting Scholar at Harvard (2024–25). Methods and governance lens.
> - **Research engineer (contractor):** quarter time across all 12 months; evaluation harness, data pipeline, full runs and the local-run kit.
> - **Scholar raters (stipended):** at least three per gold item, drawn from CEI's Scholar Group across philosophy, psychology, human rights and Catholic theology.
> - **Outside community partner:** [name], authoring the fifth module with CEI's toolkit.
> - **Two outside advisors:** review validation before any model is scored [names].

## Bay Area hub (fields 23–28)

Foresight says it prioritizes projects that will be active, in-person members of a hub. This is CEI's clearest advantage, so the answers commit to real use.

| Field | Draft answer |
| --- | --- |
| 23. Which node | Bay Area |
| 24. How long, start and end | 12 months from receipt of funds (expected February 2027 to January 2028) |
| 25. Who uses the space | [Project lead], Jimmy Lin, the research engineer, and visiting Scholar Group members [confirm days per week] |
| 26. How | Co-working; events |
| 28. Open to one travel-paid workshop | Yes |

**27. How you'll build and contribute to the community**

> We will run a monthly open session at the hub on evaluating AI values: walkthroughs of the say-do harness, reading groups on pluralistic and decentralized alignment, and office hours for anyone who wants to run or extend the suite. In month 12 we will host a workshop that brings together evals researchers and scholars from CEI's Scholar Group (philosophy, psychology, human rights and theology) to critique v1 and plan new modules. Everything we present is open source and reusable by other hub projects.

## Open source, funding, compute and consent (fields 21–22, 29–37)

| Field | Draft answer | Note |
| --- | --- | --- |
| 21. Open-source commitment | Yes | All code, scenarios, data and reports funded by this grant are released openly, which meets Foresight's requirement in full |
| 29. Requesting funding | Yes |  |
| 30. Overhead | 10% | Social Good Fund's fee must fit inside this [confirm] |
| 31. Requesting compute | Yes [decide] | To run open-weight models on Foresight's clusters; supports the local, decentralized design |
| 32. Lightcone Commons | Yes [decide] | Free second chance at funding; its evaluators focus heavily on existential risk |
| 33. Share with grant advisors | Yes |  |
| 34. Confidential info | N/A |  |
| 35. How you found us | Foresight website [confirm] |  |
| 36. Seminar groups | Optional; skip or pick the AI safety group |  |
| 37. Authority checkbox | Tick only after Rui, the reference, the co-lead and the community partner agree to be named |  |

**22. Additional information and links**

> CEI website: https://ethical-intel.org. CEI is fiscally sponsored by Social Good Fund, a 501(c)(3), until it has its own tax-exempt status; funds would be received through the sponsor. Everything this grant funds (code, scenarios, data, documentation and reports) will be released under open licenses, along with a kit for running the suite locally on open-weight models. Results are published as per-model profile reports, never a leaderboard, and no funder or lab may edit them. [Add links: pilot results if any; Governance Symphony poster or preprint; technical brief if you share it.]

## Budget detail

The form has no amount field, so the total goes in field 19; Foresight asks for an itemized budget only if the application advances. The lines fund the business plan's first-tranche priorities: the research engineer and AI compute.

| Line | Amount | Basis |
| --- | --- | --- |
| Research engineer (contractor), quarter time for 12 months | $24,000 | Same cost as the plan's half-time line for six months, spread so engineering covers the full runs and release; a contractor removes hiring delay |
| AI model tokens and compute | $9,000 | One full run of 6+ models with AI judges plus pilots, assuming Foresight cluster access for open-weight models. CEI estimates $5K–$15K per full run; without cluster access, the full run covers fewer models |
| Scholar rater honoraria | $6,000 | 12 scholars at $500 each; each rates about 30 gold items, so 120 items get three ratings |
| Outside community module stipends | $2,500 | Authors of the fifth module |
| Hosting for the public release | $500 | Open data and code |
| Hub workshop and dissemination | $1,500 | Month-12 workshop, preprint costs |
| **Direct costs** | **$43,500** |  |
| Overhead (10% of direct, Foresight's cap) | $4,350 | Covers the fiscal sponsor fee [confirm] |
| **Total request** | **$47,850** |  |

Cluster access (field 31) matters: the compute line assumes it. If Foresight declines it, either the full run covers fewer models or money moves from dissemination to compute. No private test split is funded by this grant; if CEI keeps one later, other funding pays for it. The grant covers part of the plan's first tranche (about $202K); the ED and the rest of the engineer's time still need other funders.
