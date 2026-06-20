# Proposer Quickstart

Use this guide to turn an idea into a reviewed proposal in Project Atlas. It is intentionally short: fill the template, open an issue, and let the community help you refine it.

## Purpose

Proposals are how the community decides what to build next. Every active project starts as a proposal. Submitting one does not mean you have to lead it — it means you have identified a problem worth solving and are willing to help the community reach clarity.

## Who should propose

Anyone who has used or built something public-good related and noticed a gap, duplication, or missed opportunity. You do not need to know how to solve the whole problem. You only need a clear problem statement and enough context for others to assess whether it is worth coordinated effort.

## Required inputs

The proposal issue template (`.github/ISSUE_TEMPLATE/proposal.yml`) asks for the following fields. Treat every field as required unless you genuinely do not yet have an answer; in that case write `Unknown` so reviewers know what is still open.

- **One-line summary** — a single sentence naming the proposal.
- **Problem** — what is the gap or harm this would address?
- **Who benefits?** — who is affected and how?
- **Proposed solution** — what work is proposed (build, research, coordinate, specify)?
- **Existing solutions** — what already exists? Include links.
- **Components needed** — skills, integrations, datasets, or documents required.
- **Risks and safety concerns** — privacy, security, abuse, legal, or maintenance risks.
- **Estimated human benefit** — choose Low / Medium / High / Very high (or Unknown).
- **Estimated feasibility** — choose Low / Medium / High / Very high (or Unknown).
- **First useful tasks** — what could a contributor do immediately?

Keep the initial body to five lines or fewer when possible. Use a linked detail file or pinned comment for longer research.

## How to score with impact-scoring.md

Use the impact score as a review input, not a verdict.

| Category | What to assess |
|---|---|
| Human benefit | How many people could this help, and how meaningfully? |
| Urgency | Is this a timely or worsening problem? |
| Feasibility | Can an open community realistically make progress? |
| Reusability | Can the output be reused by others? |
| Neglectedness | Is this under-served by existing projects? |
| Contributor fit | Does this community have relevant skills? |
| Safety | Can this be delivered without unacceptable risk? |

Read `docs/impact-scoring.md` for the draft formula and cautions. Scores are 0–5 per category; reviewers discuss them rather than voting blindly. A proposal that scores well on public benefit but poorly on feasibility may be best split into smaller, more tractable proposals.

## Submission checklist

- [ ] Problem is stated plainly and affects a real group of people.
- [ ] One-line summary is specific enough to distinguish it from duplicates.
- [ ] Existing solutions are listed, or it is explained why none could be adapted.
- [ ] Safety, privacy, and maintenance risks are acknowledged at a high level.
- [ ] At least one first task is listed so contributors can start immediately.
- [ ] You are willing to participate in discussion, even if you are not leading delivery.

## Where it goes next

1. **Issue queue** — the proposal issue becomes the canonical source of truth with status updated through: Draft -> Researching -> Scoring -> Candidate Project -> Active Project (see `docs/proposal-lifecycle.md`).
2. **Community Discussion** — once GitHub Discussions is enabled, debate moves there so proposals can be refined before formal review.
3. **Project board** — once GitHub Projects is enabled, promoted proposals migrate to the board with tasks, maintainers, and a roadmap.

Until Discussions and Projects are enabled, use the issue thread itself for discussion. Keep the issue title updated if the scope changes materially.
