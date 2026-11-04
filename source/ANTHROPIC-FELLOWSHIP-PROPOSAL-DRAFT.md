# Anthropic Conceptual Reasoning Fellowship: proposal draft

**Deadline: October 28, 2026.** Posting: https://job-boards.greenhouse.io/anthropic/jobs/5447080008

- **Who applies:** each person applies individually, not CEI as an organization.
- **Requirements:**
  - A PhD in philosophy, cognitive science, economics, policy or law, or equivalent research experience.
  - US work authorization; no visa sponsorship.
  - Hands-on Claude Code experience.
- **The fellowship:** four months, January 12 to May 8, 2027, paying $100K–$167K for the term. It is based in San Francisco, with remote work within the US in some cases, and a one-week orientation in person.
- **The application asks for:**
  - a CV
  - a proposal of about 200 words with one or two ideas
  - 150 words on Claude Code experience
  - optional ML experience (about 150 words)
  - two references

Adapt the draft to your own field and voice, and keep it to about 200 words. Each CEI applicant should propose a different angle; suggested variants are below.

## Draft (about 200 words)

> **Do models act on the values they state, and do they represent moral traditions faithfully?** I propose an evaluation suite in two parts. First, hard cases with gold answers written by scholars of specific traditions (normative ethics, human rights, Catholic social teaching in *Magnifica humanitas*). Each case is scored on whether Claude represents each tradition faithfully, without ranking the traditions. Second, a say–do test: Claude states its view on a value, then acts in a multi-step agentic environment where keeping that value is costly. I score consistency (does the action match the statement?) and fidelity (does the statement match the tradition?).
>
> To separate stable dispositions from prompt artifacts, every item is paraphrased and reordered. Each score is reported alongside its correlation with general capability, and scenarios are built to read as real rather than as tests.
>
> Deliverables:
> - an evaluation that runs in Inspect
> - an RL environment that rewards value-consistent action
> - a short paper
>
> The work builds on four open benchmarks I help lead at the Center for Ethical Intelligence, developed with scholars across traditions.

## Variants by applicant

- **Philosophy or theology PhD:** lead with the tradition-faithful hard cases and with describing disagreement rather than ruling on it.
- **Law or governance PhD:** propose an evaluation of whether Claude applies the principles in public AI-governance documents consistently. It would draw on the Governance Symphony corpus of 5,140 statements from 130 countries.
- **Cognitive science or psychology PhD:** propose a validity study of value measurement in LLMs, covering Moral Foundations, Schwartz values and Kohlberg-style tasks. It would test how stable the measures are across wording and format, and whether stated values predict agentic behavior.

## Note

The posting names philosophy, cognitive science, economics, policy and law, but not theology. A theology applicant should present the work as ethics and evaluation design.
