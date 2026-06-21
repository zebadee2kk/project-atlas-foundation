# Proposal Promotion Process

## Overview
This document defines how proposals move from ideas to active projects. Promotion is a deliberate community decision, not an automatic process.

## Promotion Criteria

A proposal is ready for promotion when ALL of the following are met:

1. **Problem clarity:** The problem is stated plainly, with evidence of who is affected and why it matters
2. **Research complete:** Existing solutions have been identified and their limitations documented
3. **Safety review passed:** The [Safety Agent checklist](docs/safety-agent-checklist.md) has been completed with no unresolved High-severity findings
4. **Impact scored:** The proposal has been scored using the [impact scoring model](docs/impact-scoring.md)
5. **Owner identified:** At least one person has volunteered as project lead or maintainer
6. **First tasks defined:** At least one concrete first task is listed

## Promotion Workflow

### Step 1: Nominations
Any community member can nominate a proposal for promotion by commenting:
> **Nominate for promotion:** [Brief rationale linking to criteria above]

### Step 2: Review Period
- A 7-day review period begins after nomination
- During this period, community members can raise concerns or add supporting evidence
- The proposal author can update the proposal to address feedback

### Step 3: Maintainer Decision
- At least **two maintainers** must approve the promotion
- Maintainers verify all promotion criteria are met
- If criteria are not met, maintainers provide specific feedback and the proposal returns to `needs-shaping`

### Step 4: Promotion
Upon approval:
1. Label changed from `needs-shaping` to `accepted`
2. Project lead is assigned
3. First tasks are created as child issues
4. Proposal is added to the project board in the `accepted` column
5. A promotion announcement is posted (Discussions or issue comment)

## Fast-Track Promotion
For small, low-risk proposals (documentation, research packs, minor tools):
- One maintainer approval is sufficient
- The 7-day review period is reduced to 48 hours
- Safety review may be abbreviated (no High-severity categories applicable)

## Demotion & Rejection
- If a proposal fails to gain traction within 30 days of acceptance, it may be moved to `blocked` or `wont-do`
- Proposals that receive two or more High-severity safety findings should be rejected with clear rationale
- Rejected proposals remain open with a `wont-do` label for future reference

## Governance
This process is governed by [GOVERNANCE.md](GOVERNANCE.md). Changes to promotion criteria require:
1. Discussion in GitHub Discussions (Governance category)
2. Two-maintainer approval
3. Update to this document

## Related Documents
- `docs/proposal-lifecycle.md` — full lifecycle diagram
- `docs/safety-agent-checklist.md` — safety review checklist
- `docs/impact-scoring.md` — scoring model
- `docs/project-lifecycle.md` — what happens after promotion
