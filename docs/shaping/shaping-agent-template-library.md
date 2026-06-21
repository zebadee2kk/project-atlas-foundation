# Shaping Document: Public-Good Agent Template Library (#4)

**Created:** 2026-06-21
**Score:** 22/30 — Accept
**Shaping Agent:** Team B (Hermes Agent)

---

## Refined Scope

### In Scope
Create a curated, open library of agent templates specifically designed for public-good and coordination work. The library is format-agnostic (works with any LLM framework) and distributed as Markdown + JSON schemas in a GitHub repository.

**MVP Template Collection (6 templates):**
1. **Research Agent** — Literature review, competitive analysis, evidence synthesis
2. **Documentation Agent** — README generation, decision logs, changelog drafting
3. **Project Management Agent** — Task breakdown, milestone planning, status reporting
4. **Code Review Agent** — PR review, security scanning suggestions, style checking
5. **Governance Agent** — Proposal scoring, impact assessment, safety review
6. **Operations Agent** — Issue triage, status reporting, contributor onboarding

Each template includes:
- System prompt (with placeholders for customization)
- Input/output JSON schema
- 2-3 example conversations
- Known limitations and failure modes
- Recommended model and temperature settings

### Explicitly Out of Scope (v1)
- Executable code (Python/TypeScript implementations are v2)
- Integration with specific agent frameworks (LangGraph, CrewAI, etc.)
- Automated testing of templates (manual review only for v1)
- Templates for commercial/marketing use cases

### Success Metrics
- 6 templates published with complete documentation
- ≥3 external contributors submit new templates within first month
- Templates used in ≥2 real projects (including Project Atlas itself)
- Community rates template quality ≥4/5 in feedback survey

---

## Key Research Questions

1. **What is the optimal template format?** Should templates follow a common schema (YAML frontmatter + Markdown) or be framework-specific? What metadata is essential?
2. **What existing agent patterns are most valuable for public-good work?** Survey nonprofits, civic tech projects, and open-source communities.
3. **How do we ensure template quality without a formal testing framework?** What review criteria should maintainers use?
4. **What licensing approach encourages reuse while preventing misuse?** MIT for maximum reuse, or a custom license with ethical use clause?

---

## Suggested Approach

### Phase 1 — Research (Week 1-2)
- Survey 10-15 people building agentic systems for public-good (nonprofits, civic tech, open-source)
- Audit existing template collections (LangGraph, AutoGPT, blog posts) for gaps
- Define the template schema (YAML frontmatter + Markdown body)
- Draft review criteria for template quality

### Phase 2 — Authoring (Week 3-4)
- Write 6 MVP templates following the schema
- Each template reviewed by at least one domain expert
- Create contribution guide and template submission template
- Set up repository structure: `/templates/{category}/{template-name}/`

### Phase 3 — Community Review (Week 5-6)
- Publish as a draft release on GitHub
- Request feedback via GitHub Discussions
- Run a "template jam" — invite community to submit templates
- Iterate based on feedback

### Phase 4 — Publish & Promote (Week 7-8)
- Publish v1.0 release
- Write announcement blog post
- Submit to relevant awesome-lists and directories
- Present at a community call or meetup

---

## Dependencies & Open Questions

- **Dependency:** Need 2-3 domain experts to review templates (research, code review, governance)
- **Open Question:** Should we include model-specific variants (e.g., one prompt for Claude, one for GPT-4) or aim for model-agnostic prompts?
- **Open Question:** How do we handle template versioning as models change? Templates may need updates every 6-12 months.

---

## Risks
| Risk | Mitigation |
|------|------------|
| Templates become outdated as models evolve | Version templates; include "last tested" date; community maintenance model |
| Quality control with open contributions | Require peer review before merge; maintain quality rubric |
| Templates misused for spam/manipulation | Include ethical use guidelines; MIT license with clear documentation of intended use |
| Low initial adoption | Seed with Project Atlas use cases; demonstrate value through internal usage |

---

## Related Documents
- `docs/research-agent-workflow.md` — research phase process
- `docs/seed-proposal-scores.md` — scoring details
- `docs/safety-agent-checklist.md` — safety review checklist
- `docs/proposal-promotion-process.md` — promotion criteria
