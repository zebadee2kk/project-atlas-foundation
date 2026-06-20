# AI Assistant Policy

## Purpose
This document sets operational rules for human and AI collaboration on proposal reviews, issue handling, documentation, and PRs within **project-atlas-foundation** and any projects promoted from it.

## Core principles
- **Assist, do not substitute.** AI is used to draft, summarise, and format content. Final authority, approval, and accountability remain with humans.
- **No fabricated metrics or commitments.** Do not invent dates, budgets, or capability claims.
- **Transparency by default.** When AI materially drafts content, note it in the PR/issue description. Do not obscure authorship.
- **Safety and scope.** AI workflows must not process secrets, credentials, or production target data.

## Workflow rules

### Proposals and issues
1. AI may generate initial proposal drafts from user-supplied ideas, but the submitting user must review, amend, and submit.
2. Issue templates in `.github/ISSUE_TEMPLATE/` may be expanded by AI, but every new template requires a human review before merging.
3. Issue titles and labels must remain human-authored. AI may suggest labels based on `docs/proposal-lifecycle.md` and `docs/naming-process.md`, but suggestion does not apply label.

### Documentation changes
1. README and `docs/*` may be updated by AI drafting, followed by human approval.
2. Numeric scoring (`docs/impact-scoring.md`) must use the repo’s published formula. AI may propose candidate scores but must display evidence and rationale for each score.

### Pull requests
1. AI-generated commits must use one Conventional Commit type: `docs`, `fix`, `chore`, `refactor`.
2. Each PR must include:
   - Summary of change.
   - Files modified.
   - Risks or backward-compatibility notes.
   - Whether the change was AI-assisted.

### Review and approval
1. At least one human review is required for governance-related changes: `CHARTER.md`, `GOVERNANCE.md`, `docs/impact-scoring.md`, docs related to voting or membership.
2. Non-governance docs may be merged after one reviewer check.

## Prohibited actions by AI
- Merge any PR without explicit human approval.
- Create or assign GitHub Projects or Discussions content that bypasses human review.
- Access secrets, tokens, or `.env` files.
- Execute destructive git commands (force push, branch deletion, history rewrite) without a specific human instruction in the same task context.

## Enforcement
Human maintainers may reject AI work that violates this policy. Repeated violation requires repositoring or restricting assistant access on a per-issue basis.

## Policy lifecycle
This policy is itself governed by `GOVERNANCE.md`. Amendments require discussion in GitHub Discussions under the category `Governance`, formalised through the proposal lifecycle, and a two-maintainer approval.
