# Impact Scoring

Project Atlas should prioritise useful work, not just popular work. This scoring model is intentionally simple for the founding phase.

## Proposed score categories

Each category can be scored from 0 to 5 during review.

| Category | Question |
|---|---|
| Human benefit | How many people could this help, and how meaningfully? |
| Urgency | Does this address a timely or worsening problem? |
| Feasibility | Can a small open community realistically make progress? |
| Reusability | Can the output be reused by others? |
| Neglectedness | Is this under-served by existing projects or markets? |
| Contributor fit | Does the community have the skills to help? |
| Safety | Can the project be delivered without unacceptable risk? |

## Draft formula

```text
Priority = Human benefit + Urgency + Feasibility + Reusability + Neglectedness + Contributor fit - Safety risk penalty
```

This is not final. It should be improved through usage.

## Important caution

Scoring should support judgement, not replace it. Some high-impact ideas may score poorly on feasibility and should be broken into smaller proposals. Some popular ideas may score poorly on public benefit and should not dominate the roadmap.

## Signals to collect

- Community votes
- Number of contributors interested
- Research quality
- Existing related projects
- Estimated maintenance burden
- Safety concerns
- Potential users or beneficiaries

## Ranking outputs

The platform should eventually show:

- Top emerging problems
- Top candidate proposals
- Active projects needing contributors
- Projects blocked by missing skills
- Delivered outcomes
