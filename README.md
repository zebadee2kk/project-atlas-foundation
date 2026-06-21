# Project Atlas Foundation

> Working codename: Project Atlas. Final public name to be selected after proper availability and trademark checks.

Project Atlas Foundation is an open coordination project for people using human effort and AI-assisted development to identify, prioritise, plan, and build useful public-good projects.

The long-term vision is simple:

> Create an open coordination layer for collective progress.

This repository is the temporary public home for the foundation, governance model, proposal process, project lifecycle, and early community operating system.

## Why this exists

AI has made it much easier for individuals to build software, agents, tools, automations, research systems, and prototypes. That is powerful, but it also creates a new problem: thousands of people are now spending time, tokens, money, and attention rebuilding similar things in isolation.

Project Atlas exists to reduce duplication and help builders coordinate around the work that matters.

## What this is

Project Atlas is not just a forum. It is intended to become a structured, open process for moving from problem to outcome:

```
Problem -> Proposal -> Community review -> Project -> Contributors -> Outcome
```

The first version deliberately uses existing free tools: GitHub issues, discussions, projects, static documentation, and public repositories.

## Core principles

- Open by default
- Public-good first
- Transparent decision making
- Human-led, AI-assisted
- Contribution over status
- Build before endless debate
- No corporate capture of the roadmap

See [CHARTER.md](CHARTER.md) for the full charter.

## Repository map

| Document | Description |
|----------|-------------|
| [CHARTER.md](CHARTER.md) | mission, principles, and non-negotiables |
| [GOVERNANCE.md](GOVERNANCE.md) | initial governance model |
| [CONTRIBUTING.md](CONTRIBUTING.md) | how to contribute |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | community standards |
| [docs/vision.md](docs/vision.md) | long-term vision |
| [docs/operating-model.md](docs/operating-model.md) | how the community works |
| [docs/proposal-lifecycle.md](docs/proposal-lifecycle.md) | how ideas become projects |
| [docs/project-lifecycle.md](docs/project-lifecycle.md) | how projects are run |
| [docs/impact-scoring.md](docs/impact-scoring.md) | scoring and prioritisation model |
| [docs/proposer-quickstart.md](docs/proposer-quickstart.md) | 1-page proposer quickstart |
| [docs/scoring-example.md](docs/scoring-example.md) | walkthrough of scoring a sample proposal |
| [docs/discussions-setup.md](docs/discussions-setup.md) | setup plan for proposal debate and voting |
| [docs/project-board-plan.md](docs/project-board-plan.md) | Project board lifecycle plan for proposals |
| [docs/ai-assistant-policy.md](docs/ai-assistant-policy.md) | rules for human and AI collaboration |
| [docs/new-project-checklist.md](docs/new-project-checklist.md) | checklist after a proposal is approved |
|| [docs/agentic-support-model.md](docs/agentic-support-model.md) | future AI agent support model |
|| [docs/safety-agent-checklist.md](docs/safety-agent-checklist.md) | safety review checklist for proposals |
|| [docs/research-agent-workflow.md](docs/research-agent-workflow.md) | research agent workflow (Phase 1) |
|| [docs/proposal-promotion-process.md](docs/proposal-promotion-process.md) | how proposals become projects |
|| [docs/launch-checklist.md](docs/launch-checklist.md) | launch readiness checklist |
|| [docs/naming-process.md](docs/naming-process.md) | naming process |
|| [backlog/seed-ideas.md](backlog/seed-ideas.md) | initial seed backlog |
|| [website/index.html](website/index.html) | lightweight landing page starter |

## Immediate next steps

1. Finalise the charter.
2. Enable GitHub Discussions.
3. Add initial proposal issues.
4. Recruit founding contributors.
5. Choose a permanent name after proper availability checks.
6. Launch a simple public landing page.

## Current status

Foundation repo is set up with charter, governance, contribution guidelines, code of conduct, proposal/task templates, issue templates, launch checklist, and lifecycle labels created. Landing page source exists in `website/index.html` and is copied to repo root for later GitHub Pages enablement.

## Owner action required

The following setup still needs an account with Maintainer/Owner rights on this repository:

- Enable GitHub Discussions.
- Enable GitHub Pages from the `main` branch root.
- Create the GitHub Projects board using `docs/project-board-plan.md` columns and automations.

## Proposer quick-start (3 steps)

1. Read docs/proposer-quickstart.md.
2. Score your idea using docs/impact-scoring.md and docs/scoring-example.md.
3. Open an issue using one of the built-in templates:
  - [Proposal template](.github/ISSUE_TEMPLATE/proposal.yml)
  - [Task template](.github/ISSUE_TEMPLATE/task.yml)
  - [Bug report](.github/ISSUE_TEMPLATE/bug_report.yml)
  - [Feature request](.github/ISSUE_TEMPLATE/feature_request.yml)

For infrastructure setup, see docs/discussions-setup.md and docs/project-board-plan.md.

## Cost philosophy

The project should remain free or as close to free as possible for as long as possible. Initial infrastructure should use:

- GitHub public repositories
- GitHub Issues and Discussions
- GitHub Pages or Cloudflare Pages
- Optional free community chat

No paid infrastructure should be introduced until the community has real traction.

## Licence

Documentation and community process materials are released under CC BY-SA 4.0 unless replaced by a later community-approved licence. Code should use an OSI-approved open-source licence, normally MIT or Apache-2.0 depending on the project.
