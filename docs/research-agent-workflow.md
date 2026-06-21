# Research Agent Workflow (Phase 1)

## Purpose
The Research Agent collects background information to help the community evaluate proposals. It answers: *What exists? What is missing? What are the constraints?*

## Agent Role
- **Name:** Research Agent
- **Model:** qwen2.5:7b (general purpose, 128K context)
- **Input:** Proposal issue + any linked references
- **Output:** Research pack (markdown document)

## Workflow

### Step 1: Scope Definition
The Research Agent reads the proposal and identifies research questions:
- What problem does this address?
- Who are the beneficiaries?
- What existing solutions exist?
- What are the technical constraints?
- What data or datasets are relevant?

### Step 2: Information Gathering
For each research question, the agent:
1. Searches for existing projects, tools, and research
2. Identifies comparable solutions and their limitations
3. Collects relevant statistics, reports, or academic references
4. Notes open questions that require human expertise

### Step 3: Synthesis
The agent produces a structured research pack:

```markdown
# Research Pack: [Proposal Title]

**Generated:** [YYYY-MM-DD]
**Research Agent:** [Model/version]

## Problem Context
[2-3 paragraphs summarising the problem space]

## Existing Solutions
| Solution | Type | Limitations | Relevance |
|----------|------|-------------|-----------|
| [Name] | [Tool/Project/Research] | [Key limitations] | [High/Medium/Low] |

## Key Constraints
- [Constraint 1: e.g., data availability, regulatory, technical]
- [Constraint 2]

## Relevant Data & Datasets
- [Dataset 1: source, licence, access]
- [Dataset 2]

## Open Questions
- [Question that requires human expertise]
- [Question that requires domain expert input]

## Feasibility Signals
- **Technical feasibility:** [Low/Medium/High — rationale]
- **Community fit:** [Low/Medium/High — rationale]
- **Data availability:** [Low/Medium/High — rationale]

## Sources
- [URL 1]
- [URL 2]
```

### Step 4: Human Review
The research pack is posted as a comment on the proposal issue. Humans:
- Verify accuracy of claims and links
- Add domain expertise the agent may have missed
- Flag any safety or legal concerns
- Vote on whether the research is sufficient to proceed

### Step 5: Integration
If the research pack is approved:
- Link it from the proposal issue as a pinned comment
- Update the proposal with findings
- Move the proposal to `accepted` or `needs-shaping` based on findings

## Phase 1 Constraints (MVP)
During Phase 1, the Research Agent operates in **assisted mode**:
- A human triggers the research request (comments `/research` on an issue)
- The agent produces a draft research pack
- A human reviews and approves before it is linked to the proposal
- The agent does not autonomously search or post without human approval

## Future Phases
- **Phase 2:** Automated research on new proposal creation (agent triggers itself)
- **Phase 3:** Continuous monitoring of proposal space for new relevant research
- **Phase 4:** Cross-proposal research (identifying synergies between proposals)

## Related Documents
- `docs/agentic-support-model.md` — full agent architecture
- `docs/ai-assistant-policy.md` — rules for AI-assisted work
- `docs/safety-agent-checklist.md` — safety review checklist
- `docs/impact-scoring.md` — scoring model (research informs scoring)
