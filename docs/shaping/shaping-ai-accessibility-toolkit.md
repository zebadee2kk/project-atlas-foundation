# Shaping Document: AI Accessibility Toolkit (#11)

**Created:** 2026-06-21
**Score:** 21/30 — Accept
**Shaping Agent:** Team B (Hermes Agent)

---

## Refined Scope

### In Scope
Build an open toolkit that helps developers make AI-generated code accessible by default. The toolkit has three components:

1. **Prompt Templates** — A collection of system and user prompt templates that instruct LLMs to generate accessible HTML, CSS, and JavaScript. Organized by component type (forms, navigation, tables, modals, etc.).

2. **ESLint Plugin** — Custom ESLint rules that catch common accessibility failures in AI-generated code:
   - Missing `alt` attributes on images
   - Missing `label` associations on form inputs
   - Insufficient color contrast (basic check)
   - Missing ARIA roles on interactive elements
   - Missing `lang` attribute on `<html>`

3. **CI/CD Integration Guide** — Step-by-step guide for integrating accessibility checks into common CI/CD pipelines (GitHub Actions, GitLab CI) using axe-core.

### Explicitly Out of Scope (v1)
- Full WCAG compliance automation (impossible; ~70% of issues require human judgment)
- React/Vue/Angular-specific linting (vanilla JS/HTML/CSS only for v1)
- Screen reader testing automation
- Component library (v2; too large for v1)
- Training materials (v2; partner with disability organizations)

### Success Metrics
- ESLint plugin catches ≥80% of common accessibility failures in a test suite of AI-generated code
- Prompt templates measurably improve accessibility scores (measured by axe-core) vs. baseline prompts
- ≥5 projects adopt the toolkit within first 2 months
- Zero false sense of security: documentation clearly states limitations

---

## Key Research Questions

1. **What are the most common accessibility failures in AI-generated code?** Audit 50+ AI-generated code samples (from Copilot, Claude, GPT-4) for WCAG violations.
2. **Which prompt strategies most effectively improve AI accessibility output?** A/B test 5 prompt strategies against a baseline.
3. **What is the performance-cost tradeoff of running axe-core in CI?** Measure build time impact.
4. **How do we communicate limitations without discouraging use?** Research effective "automation disclaimer" patterns.

---

## Suggested Approach

### Phase 1 — Research (Week 1-2)
- Generate 50 code samples using popular AI coding tools (Copilot, Claude, GPT-4) for common UI patterns
- Audit each sample with axe-core and manual review to build a failure taxonomy
- Survey 5-10 accessibility experts on highest-impact automated checks
- Draft prompt template strategy based on findings

### Phase 2 — Build (Week 3-5)
- Develop ESLint plugin with 10-15 rules covering the most common failures
- Write 10-15 prompt templates organized by component type
- Create GitHub Actions workflow for CI/CD integration
- Write comprehensive README with limitations section

### Phase 3 — Validate (Week 6-7)
- Test ESLint plugin against the 50-sample dataset; measure precision/recall
- A/B test prompt templates: generate code with and without templates, compare accessibility scores
- Partner with 1-2 disability advocacy groups for review
- Fix issues found during validation

### Phase 4 — Publish & Promote (Week 8)
- Publish ESLint plugin to npm
- Publish prompt templates as GitHub repository
- Write announcement blog post targeting AI developer community
- Submit to accessibility and AI tooling directories

---

## Dependencies & Open Questions

- **Dependency:** Requires npm publishing account for ESLint plugin
- **Dependency:** Needs review from disability advocacy group (reach out to G3ict, WebAIM, or local organizations)
- **Open Question:** Should the ESLint plugin be framework-agnostic or should we ship separate packages for React, Vue, etc.?
- **Open Question:** How do we handle false positives in the ESLint rules? Need configurable severity levels.

---

## Risks
| Risk | Mitigation |
|------|------------|
| False sense of security ("I ran the linter, so my app is accessible") | Prominent documentation stating ~30% automation ceiling; require manual audit disclaimer |
| ESLint rules have high false-positive rate | Extensive testing against real AI-generated code; configurable rule severity |
| Prompt templates become outdated as models improve | Version templates; include "last tested with" date; community maintenance |
| Low adoption by AI developers | Partner with AI tooling communities; demonstrate clear ROI (fewer accessibility bugs) |
| Accessibility community skepticism | Involve disability advocates from day one; don't overclaim |

---

## Related Documents
- `docs/research-agent-workflow.md` — research phase process
- `docs/seed-proposal-scores.md` — scoring details
- `docs/safety-agent-checklist.md` — safety review checklist
- `docs/proposal-promotion-process.md` — promotion criteria
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [axe-core GitHub](https://github.com/dequelabs/axe-core)
