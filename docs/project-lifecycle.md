# Project Lifecycle

A project is an approved effort with a defined scope, public tasks, and at least one accountable maintainer.

## Stages

```text
Setup -> Research -> Design -> Prototype -> MVP -> Sustain -+-> Completed
                                                           |
                                                           +-> Merged / Paused / Archived
```

### 1. Setup

Create a public project area with a README, initial backlog, maintainers list, and basic contribution rules.

### 2. Research

Validate the problem, users, risks, existing solutions, and constraints. Capture findings in `docs/research.md` or linked notes.

### 3. Design

Document the target architecture, interfaces, governance constraints, and success criteria in `docs/architecture.md`.

### 4. Prototype

Build a small working demonstration. The prototype should answer the single riskiest technical question.

### 5. MVP

Deliver the minimum useful version real users can try. Define what “useful” means before building.

### 6. Sustain

Document maintenance needs, support model, ownership, security updates, and long-term stewardship. Add a `MAINTAINERS.md` if one does not already exist.

## Completion criteria

A project is considered complete, merged, paused, or archived when the accountable maintainer moves the issue and updates the README with the final state and outcome.

## Project roles

- Project lead
- Maintainer
- Research contributor
- Technical contributor
- Documentation contributor
- Reviewer
- User tester
- AI assistant or agent, where appropriate and disclosed

## Required files for active projects

Each active project should have at least:

- `README.md`
- `ROADMAP.md`
- `CONTRIBUTING.md`
- `MAINTAINERS.md`
- `SECURITY.md`
