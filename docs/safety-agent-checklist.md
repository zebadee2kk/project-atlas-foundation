# Safety Agent Review Checklist

## Purpose
The Safety Agent reviews proposals for risks that could cause harm to individuals, communities, or the project itself. This checklist ensures consistent, thorough safety reviews before a proposal is accepted.

## When to use
- Every proposal must pass a Safety Agent review before promotion from `needs-shaping` to `accepted`
- Re-review if the proposal scope changes significantly during implementation
- Ad-hoc review if a community member raises a safety concern

## Checklist

### 1. Dual-Use Risk
- [ ] Could the proposed tool or output be repurposed for harm (surveillance, manipulation, exploitation)?
- [ ] If yes, are there mitigations (access controls, usage policies, technical limitations)?
- [ ] Is the dual-use risk proportional to the public benefit?

### 2. Privacy & Data Protection
- [ ] Does the proposal involve collecting, processing, or storing personal data?
- [ ] If yes, is there a data minimisation plan (only collect what is needed)?
- [ ] Are data retention and deletion policies defined?
- [ ] Does the proposal comply with GDPR, CCPA, or equivalent frameworks where applicable?
- [ ] Are users informed about what data is collected and how it is used?

### 3. Security
- [ ] Does the proposal involve network services, APIs, or user authentication?
- [ ] If yes, are there known attack surfaces identified?
- [ ] Is there a plan for handling secrets, credentials, and API keys?
- [ ] Is there a vulnerability disclosure process (see SECURITY.md)?

### 4. Accessibility & Inclusion
- [ ] Could the proposal exclude or disadvantage any group (disability, language, geography, economic)?
- [ ] If yes, are there plans to address accessibility (WCAG, multilingual, low-bandwidth)?
- [ ] Is the proposed solution usable by people with limited technical skills?

### 5. Legal & Regulatory
- [ ] Does the proposal operate in a regulated domain (health, finance, education, legal)?
- [ ] If yes, has legal advice been sought or flagged as a prerequisite?
- [ ] Are there export control, sanctions, or jurisdiction concerns?

### 6. Maintenance & Abandonment Risk
- [ ] What happens if the maintainers abandon the project?
- [ ] Is the project structured so others can take over (documentation, open governance)?
- [ ] Are there dependencies on paid services that could become unavailable?

### 7. Community Impact
- [ ] Could the proposal create conflict within the community (naming, scope overlap, governance)?
- [ ] Is the proposal aligned with the charter principles (open by default, public-good first)?
- [ ] Are there moderation or dispute resolution needs?

### 8. AI-Specific Risks
- [ ] Does the proposal involve AI/ML models or automated decision-making?
- [ ] If yes, are there bias, fairness, or transparency concerns?
- [ ] Is there human oversight for consequential decisions?
- [ ] Are AI-generated outputs clearly labelled?

## Review Output Format

```markdown
## Safety Review: [Proposal Title]

**Reviewer:** [Name or Agent ID]
**Date:** [YYYY-MM-DD]
**Verdict:** ✅ Pass / ⚠️ Pass with conditions / ❌ Block

### Findings
- [ ] Dual-use risk: [None / Low / Medium / High — details]
- [ ] Privacy: [None / Low / Medium / High — details]
- [ ] Security: [None / Low / Medium / High — details]
- [ ] Accessibility: [None / Low / Medium / High — details]
- [ ] Legal: [None / Low / Medium / High — details]
- [ ] Maintenance: [None / Low / Medium / High — details]
- [ ] Community: [None / Low / Medium / High — details]
- [ ] AI-specific: [None / Low / Medium / High — details]

### Conditions (if applicable)
1. [Condition that must be met before acceptance]

### Recommendation
[Accept / Accept with conditions / Reject with rationale]
```

## Escalation
- Any `High` severity finding in categories 1-5 must be escalated to a human maintainer before acceptance
- Disagreements between the Safety Agent and the proposer should be resolved through GitHub Discussions
- The Safety Agent may recommend splitting a proposal into safer sub-proposals

## Integration with Proposal Lifecycle
This checklist maps to the `needs-shaping` phase of the proposal lifecycle. The Safety Agent review is one of the required artefacts before promotion to `acceptance` (see `docs/proposal-lifecycle.md`).

## Related Documents
- `docs/proposal-lifecycle.md` — full lifecycle
- `docs/ai-assistant-policy.md` — rules for AI-assisted review
- `docs/impact-scoring.md` — scoring model (safety is a category)
- `SECURITY.md` — vulnerability disclosure process
