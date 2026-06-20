# Agentic Support Model

Project Atlas should eventually use AI agents to reduce coordination overhead. This should be done carefully: AI should support human contributors, not replace community governance.

## Future project agents

### Research Agent

Collects background information, existing projects, comparable tools, datasets, constraints, and open questions.

### Project Manager Agent

Turns proposals into milestones, tasks, dependency maps, and delivery plans.

### Architecture Agent

Drafts technical options, trade-offs, diagrams, and implementation approaches.

### Documentation Agent

Maintains README files, decision logs, onboarding guides, and user documentation.

### Review Agent

Reviews pull requests, checks consistency with project goals, and flags missing tests or documentation.

### Safety Agent

Checks proposals for dual-use risk, privacy concerns, security issues, and governance concerns.

## Human control requirements

- Agents must not approve projects alone.
- Agents must not make governance decisions.
- Agent output should be labelled as AI-assisted.
- Sensitive or safety-relevant recommendations require human review.
- Agents should work from public project context where possible.

## Low-cost implementation path

During the MVP phase, avoid building custom agent infrastructure. Use manual AI-assisted workflows first:

1. Human opens a proposal.
2. Human asks an AI assistant to produce research notes.
3. Notes are reviewed before being committed.
4. Maintainers decide whether the material is useful.

Only build automated agents once the manual workflow is proven.

## Long-term opportunity

If successful, Project Atlas could become a natural home for reusable open agent teams that help public-good projects move faster:

```text
Proposal -> Research Pack -> Architecture Pack -> Roadmap -> Issues -> MVP
```
